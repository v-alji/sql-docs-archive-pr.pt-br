---
title: Função Multilookup (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 1fec079e-33b3-4e4d-92b3-6b4d06a49a77
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 2f2aff7a2a39e1a072cf4b05f0a04e12ced529af
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573711"
---
# <a name="multilookup-function-report-builder-and-ssrs"></a><span data-ttu-id="10c78-102">Função Multilookup (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="10c78-102">Multilookup Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="10c78-103">Retorna o conjunto de primeiros valores correspondentes para o conjunto de nomes especificado de um conjunto de dados que contém pares de nome/valor.</span><span class="sxs-lookup"><span data-stu-id="10c78-103">Returns the set of first-match values for the specified set of names from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="10c78-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="10c78-104">Syntax</span></span>  
  
```  
  
Multilookup(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="10c78-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="10c78-105">Parameters</span></span>  
 <span data-ttu-id="10c78-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="10c78-106">*source_expression*</span></span>  
 <span data-ttu-id="10c78-107">(`VariantArray`) Uma expressão que é avaliada no escopo atual e que especifica o conjunto de nomes ou chaves para procurar.</span><span class="sxs-lookup"><span data-stu-id="10c78-107">(`VariantArray`) An expression that is evaluated in the current scope and that specifies the set of names or keys to look up.</span></span> <span data-ttu-id="10c78-108">Por exemplo, para um parâmetro de vários valores, `=Parameters!IDs.value`.</span><span class="sxs-lookup"><span data-stu-id="10c78-108">For example, for a multivalue parameter, `=Parameters!IDs.value`.</span></span>  
  
 <span data-ttu-id="10c78-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="10c78-109">*destination_expression*</span></span>  
 <span data-ttu-id="10c78-110">(`Variant`) Uma expressão que é avaliada para cada linha em um conjunto de dados e que especifica o nome ou a chave para correspondência.</span><span class="sxs-lookup"><span data-stu-id="10c78-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="10c78-111">Por exemplo, `=Fields!ID.Value`.</span><span class="sxs-lookup"><span data-stu-id="10c78-111">For example, `=Fields!ID.Value`.</span></span>  
  
 <span data-ttu-id="10c78-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="10c78-112">*result_expression*</span></span>  
 <span data-ttu-id="10c78-113">( `Variant` ) Uma expressão que é avaliada para a linha no conjunto de linhas em que *source_expression*  =  *destination_expression*e que especifica o valor a ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="10c78-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="10c78-114">Por exemplo, `=Fields!Name.Value`.</span><span class="sxs-lookup"><span data-stu-id="10c78-114">For example, `=Fields!Name.Value`.</span></span>  
  
 <span data-ttu-id="10c78-115">*conjunto de dados*</span><span class="sxs-lookup"><span data-stu-id="10c78-115">*dataset*</span></span>  
 <span data-ttu-id="10c78-116">Uma constante que especifica o nome do conjunto de dados no relatório.</span><span class="sxs-lookup"><span data-stu-id="10c78-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="10c78-117">Por exemplo, "Cores".</span><span class="sxs-lookup"><span data-stu-id="10c78-117">For example, "Colors".</span></span>  
  
## <a name="return"></a><span data-ttu-id="10c78-118">Retorno</span><span class="sxs-lookup"><span data-stu-id="10c78-118">Return</span></span>  
 <span data-ttu-id="10c78-119">Retorna `VariantArray` ou `Nothing` se não houver correspondência.</span><span class="sxs-lookup"><span data-stu-id="10c78-119">Returns a `VariantArray`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="10c78-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="10c78-120">Remarks</span></span>  
 <span data-ttu-id="10c78-121">Use `Multilookup` para recuperar um conjunto de valores de um conjunto de dados para os pares nome/valor em que cada par tem uma relação de 1 para 1.</span><span class="sxs-lookup"><span data-stu-id="10c78-121">Use `Multilookup` to retrieve a set of values from a dataset for name-value pairs where each pair has a 1-to-1 relationship.</span></span> <span data-ttu-id="10c78-122">`MultiLookup` é o equivalente a chamar `Lookup` para um conjunto de nomes ou chaves.</span><span class="sxs-lookup"><span data-stu-id="10c78-122">`MultiLookup` is the equivalent of calling `Lookup` for a set of names or keys.</span></span> <span data-ttu-id="10c78-123">Por exemplo, para um parâmetro de vários valores que é baseado em identificadores de chave primária, você pode usar `Multilookup` em uma expressão em uma caixa de texto de uma tabela para recuperar valores associados de um conjunto de dados que não está associado ao parâmetro ou à tabela.</span><span class="sxs-lookup"><span data-stu-id="10c78-123">For example, for a multivalue parameter that is based on primary key identifiers, you can use `Multilookup` in an expression in a text box in a table to retrieve associated values from a dataset that is not bound to the parameter or to the table.</span></span>  
  
 <span data-ttu-id="10c78-124">`Multilookup` faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="10c78-124">`Multilookup` does the following:</span></span>  
  
-   <span data-ttu-id="10c78-125">Avalia a expressão de origem no escopo atual e gera uma matriz de objetos variantes.</span><span class="sxs-lookup"><span data-stu-id="10c78-125">Evaluates the source expression in the current scope and generates an array of variant objects.</span></span>  
  
-   <span data-ttu-id="10c78-126">Para cada objeto na matriz, chama [Função Lookup &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-lookup-function.md) e adiciona o resultado à matriz de retorno.</span><span class="sxs-lookup"><span data-stu-id="10c78-126">For each object in the array, calls [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md) and adds the result to the return array.</span></span>  
  
-   <span data-ttu-id="10c78-127">Retorna o conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="10c78-127">Returns the set of results.</span></span>  
  
 <span data-ttu-id="10c78-128">Para recuperar um único valor de um conjunto de dados com pares nome-valor de um nome especificado em que existe uma relação um-para-um, use [Função Lookup &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="10c78-128">To retrieve a single value from a dataset with name-value pairs for a specified name where there is a 1-to-1 relationship, use [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span> <span data-ttu-id="10c78-129">Para recuperar vários valores de um conjunto de dados com pares nome-valor de um nome em que existe uma relação um para muitos, use [Função LookupSet &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-lookupset-function.md).</span><span class="sxs-lookup"><span data-stu-id="10c78-129">To retrieve multiple values from a dataset with name-value pairs for a name where there is a 1-to-many relationship, use [LookupSet Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookupset-function.md).</span></span>  
  
 <span data-ttu-id="10c78-130">As restrições a seguir se aplicam:</span><span class="sxs-lookup"><span data-stu-id="10c78-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="10c78-131">`Multilookup` é avaliado depois que todas as expressões de filtro são aplicadas</span><span class="sxs-lookup"><span data-stu-id="10c78-131">`Multilookup` is evaluated after all filter expressions are applied</span></span>  
  
-   <span data-ttu-id="10c78-132">Só há suporte para um nível de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="10c78-132">Only one level of look-up is supported.</span></span> <span data-ttu-id="10c78-133">Uma expressão de origem, destino ou resultado não pode incluir uma referência a uma função de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="10c78-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="10c78-134">Expressões de origem e destino devem ser avaliadas como o mesmo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="10c78-134">Source and destination expressions must evaluate to the same data type.</span></span>  
  
-   <span data-ttu-id="10c78-135">Expressões de origem, destino e resultado não podem incluir referências a variáveis de relatório ou grupo.</span><span class="sxs-lookup"><span data-stu-id="10c78-135">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="10c78-136">`Multilookup` não pode ser usado como uma expressão para os seguintes itens de relatório:</span><span class="sxs-lookup"><span data-stu-id="10c78-136">`Multilookup` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="10c78-137">Cadeias de conexão dinâmicas para uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="10c78-137">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="10c78-138">Campos calculados em um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="10c78-138">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="10c78-139">Parâmetros de consulta em um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="10c78-139">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="10c78-140">Filtros em um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="10c78-140">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="10c78-141">Parâmetros de relatório.</span><span class="sxs-lookup"><span data-stu-id="10c78-141">Report parameters.</span></span>  
  
    -   <span data-ttu-id="10c78-142">A propriedade Report.Language.</span><span class="sxs-lookup"><span data-stu-id="10c78-142">The Report.Language property.</span></span>  
  
 <span data-ttu-id="10c78-143">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="10c78-143">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="10c78-144">Exemplo</span><span class="sxs-lookup"><span data-stu-id="10c78-144">Example</span></span>  
 <span data-ttu-id="10c78-145">Suponha que um conjunto de dados denominado "Category" contenha o campo CategoryList, que é um campo que contém uma lista separada por vírgulas de identificadores de categoria, por exemplo, "2, 4, 2, 1".</span><span class="sxs-lookup"><span data-stu-id="10c78-145">Assume a dataset called "Category" contains the field CategoryList, which is a field that contains a comma-separated list of category identifers, for example, "2, 4, 2, 1".</span></span>  
  
 <span data-ttu-id="10c78-146">O conjunto de dados CategoryNames contém o identificador de categoria e o nome da categoria, como mostra a tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="10c78-146">The dataset CategoryNames contains the category identifier and category name, as shown in the following table.</span></span>  
  
|<span data-ttu-id="10c78-147">ID</span><span class="sxs-lookup"><span data-stu-id="10c78-147">ID</span></span>|<span data-ttu-id="10c78-148">Nome</span><span class="sxs-lookup"><span data-stu-id="10c78-148">Name</span></span>|  
|--------|----------|  
|<span data-ttu-id="10c78-149">1</span><span class="sxs-lookup"><span data-stu-id="10c78-149">1</span></span>|<span data-ttu-id="10c78-150">Acessórios</span><span class="sxs-lookup"><span data-stu-id="10c78-150">Accessories</span></span>|  
|<span data-ttu-id="10c78-151">2</span><span class="sxs-lookup"><span data-stu-id="10c78-151">2</span></span>|<span data-ttu-id="10c78-152">Bikes</span><span class="sxs-lookup"><span data-stu-id="10c78-152">Bikes</span></span>|  
|<span data-ttu-id="10c78-153">3</span><span class="sxs-lookup"><span data-stu-id="10c78-153">3</span></span>|<span data-ttu-id="10c78-154">Clothing</span><span class="sxs-lookup"><span data-stu-id="10c78-154">Clothing</span></span>|  
|<span data-ttu-id="10c78-155">4</span><span class="sxs-lookup"><span data-stu-id="10c78-155">4</span></span>|<span data-ttu-id="10c78-156">Componentes</span><span class="sxs-lookup"><span data-stu-id="10c78-156">Components</span></span>|  
  
 <span data-ttu-id="10c78-157">Para procurar os nomes que correspondem à lista de identificadores, use `Multilookup`.</span><span class="sxs-lookup"><span data-stu-id="10c78-157">To look up the names that correspond to the list of  identifiers, use `Multilookup`.</span></span> <span data-ttu-id="10c78-158">Você primeiro deve dividir a lista em uma matriz de cadeia de caracteres, chamar `Multilookup` para recuperar os nomes de categoria e concatenar os resultados em uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="10c78-158">You must first split the list into a string array, call `Multilookup` to retrieve the category names, and concatenate the results into a string.</span></span>  
  
 <span data-ttu-id="10c78-159">A seguinte expressão, quando colocada em uma caixa de texto em uma região de dados associada ao conjunto de dados Category, exibe "Bikes, Components, Bikes, Accessories":</span><span class="sxs-lookup"><span data-stu-id="10c78-159">The following expression, when placed in a text box in a data region bound to the Category dataset, displays "Bikes, Components, Bikes, Accessories":</span></span>  
  
```  
=Join(MultiLookup(Split(Fields!CategoryList.Value,","),  
   Fields!CategoryID.Value,Fields!CategoryName.Value,"Category")),  
   ", ")  
```  
  
## <a name="example"></a><span data-ttu-id="10c78-160">Exemplo</span><span class="sxs-lookup"><span data-stu-id="10c78-160">Example</span></span>  
 <span data-ttu-id="10c78-161">Suponha que um conjunto de dados ProductColors contenha um campo identificador de cor ColorID e um campo de valor de cor Color, como mostra a tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="10c78-161">Assume a dataset ProductColors contains a color identifier field ColorID and a color value field Color, as shown in the following table.</span></span>  
  
|<span data-ttu-id="10c78-162">ColorID</span><span class="sxs-lookup"><span data-stu-id="10c78-162">ColorID</span></span>|<span data-ttu-id="10c78-163">Color</span><span class="sxs-lookup"><span data-stu-id="10c78-163">Color</span></span>|  
|-------------|-----------|  
|<span data-ttu-id="10c78-164">1</span><span class="sxs-lookup"><span data-stu-id="10c78-164">1</span></span>|<span data-ttu-id="10c78-165">Vermelho</span><span class="sxs-lookup"><span data-stu-id="10c78-165">Red</span></span>|  
|<span data-ttu-id="10c78-166">2</span><span class="sxs-lookup"><span data-stu-id="10c78-166">2</span></span>|<span data-ttu-id="10c78-167">Azul</span><span class="sxs-lookup"><span data-stu-id="10c78-167">Blue</span></span>|  
|<span data-ttu-id="10c78-168">3</span><span class="sxs-lookup"><span data-stu-id="10c78-168">3</span></span>|<span data-ttu-id="10c78-169">Verde</span><span class="sxs-lookup"><span data-stu-id="10c78-169">Green</span></span>|  
  
 <span data-ttu-id="10c78-170">Suponha que o parâmetro de vários valores *MyColors* não esteja associado a um conjunto de dados para obter seus valores disponíveis.</span><span class="sxs-lookup"><span data-stu-id="10c78-170">Assume the multivalue parameter *MyColors* is not bound to a dataset for its available values.</span></span> <span data-ttu-id="10c78-171">Os valores padrão para o parâmetro estão definidos como 2 e 3.</span><span class="sxs-lookup"><span data-stu-id="10c78-171">The default values for the parameter are set to 2 and 3.</span></span> <span data-ttu-id="10c78-172">A expressão a seguir, quando colocada em uma caixa de texto em uma tabela, concatena os vários valores selecionados para o parâmetro em uma lista separada por vírgulas e exibe "Blue, Green".</span><span class="sxs-lookup"><span data-stu-id="10c78-172">The following expression, when placed in a text box in a table, concatenates the multiple selected values for the parameter into a comma-separated list and displays "Blue, Green".</span></span>  
  
```  
=Join(MultiLookup(Parameters!MyColors.Value,Fields!ColorID.Value,Fields!Color.Value,"ProductColors"),", ")  
```  
  
## <a name="see-also"></a><span data-ttu-id="10c78-173">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="10c78-173">See Also</span></span>  
 <span data-ttu-id="10c78-174">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10c78-174">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="10c78-175">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10c78-175">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="10c78-176">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="10c78-176">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="10c78-177">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="10c78-177">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
