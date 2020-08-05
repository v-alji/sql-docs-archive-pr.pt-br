---
title: Função Lookup (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: e60e5bab-b286-4897-9685-9ff12703517d
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 053fefff51e4b4e338e262664bd7570280c92540
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573713"
---
# <a name="lookup-function-report-builder-and-ssrs"></a><span data-ttu-id="375e7-102">Função Lookup (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="375e7-102">Lookup Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="375e7-103">Retorna o primeiro valor correspondente para o nome especificado de um conjunto de dados que contém pares de nome/valor.</span><span class="sxs-lookup"><span data-stu-id="375e7-103">Returns the first matching value for the specified name from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="375e7-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="375e7-104">Syntax</span></span>  
  
```  
  
Lookup(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="375e7-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="375e7-105">Parameters</span></span>  
 <span data-ttu-id="375e7-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="375e7-106">*source_expression*</span></span>  
 <span data-ttu-id="375e7-107">(`Variant`) Uma expressão que é avaliada no escopo atual e que especifica o nome ou chave para procurar.</span><span class="sxs-lookup"><span data-stu-id="375e7-107">(`Variant`) An expression that is evaluated in the current scope and that specifies the name or key to look up.</span></span> <span data-ttu-id="375e7-108">Por exemplo, `=Fields!ProdID.Value`.</span><span class="sxs-lookup"><span data-stu-id="375e7-108">For example, `=Fields!ProdID.Value`.</span></span>  
  
 <span data-ttu-id="375e7-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="375e7-109">*destination_expression*</span></span>  
 <span data-ttu-id="375e7-110">(`Variant`) Uma expressão que é avaliada para cada linha em um conjunto de dados e que especifica o nome ou a chave para correspondência.</span><span class="sxs-lookup"><span data-stu-id="375e7-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="375e7-111">Por exemplo, `=Fields!ProductID.Value`.</span><span class="sxs-lookup"><span data-stu-id="375e7-111">For example, `=Fields!ProductID.Value`.</span></span>  
  
 <span data-ttu-id="375e7-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="375e7-112">*result_expression*</span></span>  
 <span data-ttu-id="375e7-113">( `Variant` ) Uma expressão que é avaliada para a linha no conjunto de linhas em que *source_expression*  =  *destination_expression*e que especifica o valor a ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="375e7-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="375e7-114">Por exemplo, `=Fields!ProductName.Value`.</span><span class="sxs-lookup"><span data-stu-id="375e7-114">For example, `=Fields!ProductName.Value`.</span></span>  
  
 <span data-ttu-id="375e7-115">*conjunto de dados*</span><span class="sxs-lookup"><span data-stu-id="375e7-115">*dataset*</span></span>  
 <span data-ttu-id="375e7-116">Uma constante que especifica o nome do conjunto de dados no relatório.</span><span class="sxs-lookup"><span data-stu-id="375e7-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="375e7-117">Por exemplo, "Produtos".</span><span class="sxs-lookup"><span data-stu-id="375e7-117">For example, "Products".</span></span>  
  
## <a name="return"></a><span data-ttu-id="375e7-118">Retorno</span><span class="sxs-lookup"><span data-stu-id="375e7-118">Return</span></span>  
 <span data-ttu-id="375e7-119">Retorna `Variant` ou `Nothing` se não houver correspondência.</span><span class="sxs-lookup"><span data-stu-id="375e7-119">Returns a `Variant`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="375e7-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="375e7-120">Remarks</span></span>  
 <span data-ttu-id="375e7-121">Use `Lookup` para recuperar o valor do conjunto de dados especificado para um par de nome/valor onde há uma relação de 1 para 1.</span><span class="sxs-lookup"><span data-stu-id="375e7-121">Use `Lookup` to retrieve the value from the specified dataset for a name/value pair where there is a 1-to-1 relationship.</span></span> <span data-ttu-id="375e7-122">Por exemplo, para um campo de ID em uma tabela, você pode usar `Lookup` para recuperar todos os números de telefone associados àquele cliente de um conjunto de dados que não esteja associado à região de dados.</span><span class="sxs-lookup"><span data-stu-id="375e7-122">For example, for an ID field in a table, you can use `Lookup` to retrieve the corresponding Name field from a dataset that is not bound to the data region.</span></span>  
  
 <span data-ttu-id="375e7-123">`Lookup` faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="375e7-123">`Lookup` does the following:</span></span>  
  
-   <span data-ttu-id="375e7-124">Avalia a expressão de origem no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="375e7-124">Evaluates the source expression in the current scope.</span></span>  
  
-   <span data-ttu-id="375e7-125">Avalia a expressão de destino para cada linha do conjunto de dados especificado depois que foram aplicados filtros, com base na ordenação do conjunto de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="375e7-125">Evaluates the destination expression for each row of the specified dataset after filters have been applied, based on the collation of the specified dataset.</span></span>  
  
-   <span data-ttu-id="375e7-126">Na primeira correspondência da expressão de origem e destino, avalia a expressão resultante para aquela linha no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="375e7-126">On the first match of source expression and destination expression, evaluates the result expression for that row in the dataset.</span></span>  
  
-   <span data-ttu-id="375e7-127">Retorna o valor da expressão resultante.</span><span class="sxs-lookup"><span data-stu-id="375e7-127">Returns the result expression value.</span></span>  
  
 <span data-ttu-id="375e7-128">Para recuperar diversos valores para um único nome ou campo de chave em que há uma relação um para muitos, use [Função LookupSet &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-lookupset-function.md).</span><span class="sxs-lookup"><span data-stu-id="375e7-128">To retrieve multiple values for a single name or key field where there is a 1-to-many relationship, use [LookupSet Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookupset-function.md).</span></span> <span data-ttu-id="375e7-129">Para chamar `Lookup` um conjunto de valores, use a [função multilookup &#40;Construtor de relatórios e o SSRS&#41;](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="375e7-129">To call `Lookup` for a set of values, use [Multilookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span>  
  
 <span data-ttu-id="375e7-130">As restrições a seguir se aplicam:</span><span class="sxs-lookup"><span data-stu-id="375e7-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="375e7-131">`Lookup` é avaliado depois que todas as expressões de filtro são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="375e7-131">`Lookup` is evaluated after all filter expressions are applied.</span></span>  
  
-   <span data-ttu-id="375e7-132">Só um nível de pesquisa tem suporte.</span><span class="sxs-lookup"><span data-stu-id="375e7-132">Only one level of lookup is supported.</span></span> <span data-ttu-id="375e7-133">Uma expressão de origem, destino ou resultado não pode incluir uma referência a uma função de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="375e7-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="375e7-134">Expressões de origem e destino devem ser avaliadas como o mesmo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="375e7-134">Source and destination expressions must evaluate to the same data type.</span></span> <span data-ttu-id="375e7-135">O tipo de retorno é o mesmo que o tipo de dados da expressão resultante avaliada.</span><span class="sxs-lookup"><span data-stu-id="375e7-135">The return type is the same as the data type of the evaluated result expression.</span></span>  
  
-   <span data-ttu-id="375e7-136">Expressões de origem, destino e resultado não podem incluir referências a variáveis de relatório ou grupo.</span><span class="sxs-lookup"><span data-stu-id="375e7-136">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="375e7-137">`Lookup` não pode ser usado como uma expressão para os seguintes itens de relatório:</span><span class="sxs-lookup"><span data-stu-id="375e7-137">`Lookup` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="375e7-138">Cadeias de conexão dinâmicas para uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="375e7-138">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="375e7-139">Campos calculados em um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="375e7-139">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="375e7-140">Parâmetros de consulta em um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="375e7-140">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="375e7-141">Filtros em um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="375e7-141">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="375e7-142">Parâmetros de relatório.</span><span class="sxs-lookup"><span data-stu-id="375e7-142">Report parameters.</span></span>  
  
    -   <span data-ttu-id="375e7-143">A propriedade Report.Language.</span><span class="sxs-lookup"><span data-stu-id="375e7-143">The Report.Language property.</span></span>  
  
 <span data-ttu-id="375e7-144">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="375e7-144">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="375e7-145">Exemplo</span><span class="sxs-lookup"><span data-stu-id="375e7-145">Example</span></span>  
 <span data-ttu-id="375e7-146">No exemplo seguinte, suponha que a tabela esteja associada a um conjunto de dados que inclui um campo para o identificador de produto ProductID.</span><span class="sxs-lookup"><span data-stu-id="375e7-146">In the following example, assume that a table is bound to a dataset that includes a field for the product identifier ProductID.</span></span> <span data-ttu-id="375e7-147">Um conjunto de dados separado chamado "Produto" contém a ID do identificador de produto correspondente e o nome de produto Nome.</span><span class="sxs-lookup"><span data-stu-id="375e7-147">A separate dataset called "Product" contains the corresponding product identifier ID and the product name Name.</span></span>  
  
 <span data-ttu-id="375e7-148">Na expressão seguinte, `Lookup` compara o valor de ProductID com a ID em cada linha do conjunto de dados chamado "Produto" e, quando uma correspondência é localizada, retorna o valor do campo Nome para aquela linha.</span><span class="sxs-lookup"><span data-stu-id="375e7-148">In the following expression, `Lookup` compares the value of ProductID to ID in each row of the dataset called "Product" and, when a match is found, returns the value of the Name field for that row.</span></span>  
  
```  
=Lookup(Fields!ProductID.Value, Fields!ID.Value, Fields!Name.Value, "Product")  
```  
  
## <a name="see-also"></a><span data-ttu-id="375e7-149">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="375e7-149">See Also</span></span>  
 <span data-ttu-id="375e7-150">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="375e7-150">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="375e7-151">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="375e7-151">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="375e7-152">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="375e7-152">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="375e7-153">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="375e7-153">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
