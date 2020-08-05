---
title: Função LookupSet (Construtor de Relatórios e SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
ms.assetid: 7685acfd-1c8d-420c-993c-903236fbe1ff
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: 4edc7a17f2aa3813e8aa73e538594b5df3aeabc1
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573716"
---
# <a name="lookupset-function-report-builder-and-ssrs"></a><span data-ttu-id="28c15-102">Função LookupSet (Construtor de Relatórios e SSRS)</span><span class="sxs-lookup"><span data-stu-id="28c15-102">LookupSet Function (Report Builder and SSRS)</span></span>
  <span data-ttu-id="28c15-103">Retorna o conjunto de valores correspondentes para o nome especificado de um conjunto de dados que contém pares de nome/valor.</span><span class="sxs-lookup"><span data-stu-id="28c15-103">Returns the set of matching values for the specified name from a dataset that contains name/value pairs.</span></span>  
  
> [!NOTE]  
>  [!INCLUDE[ssRBRDDup](../../includes/ssrbrddup-md.md)]  
  
## <a name="syntax"></a><span data-ttu-id="28c15-104">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="28c15-104">Syntax</span></span>  
  
```  
  
LookupSet(source_expression, destination_expression, result_expression, dataset)  
```  
  
#### <a name="parameters"></a><span data-ttu-id="28c15-105">parâmetros</span><span class="sxs-lookup"><span data-stu-id="28c15-105">Parameters</span></span>  
 <span data-ttu-id="28c15-106">*source_expression*</span><span class="sxs-lookup"><span data-stu-id="28c15-106">*source_expression*</span></span>  
 <span data-ttu-id="28c15-107">(`Variant`) Uma expressão que é avaliada no escopo atual e que especifica o nome ou chave para procurar.</span><span class="sxs-lookup"><span data-stu-id="28c15-107">(`Variant`) An expression that is evaluated in the current scope and that specifies the name or key to look up.</span></span> <span data-ttu-id="28c15-108">Por exemplo, `=Fields!ID.Value`.</span><span class="sxs-lookup"><span data-stu-id="28c15-108">For example, `=Fields!ID.Value`.</span></span>  
  
 <span data-ttu-id="28c15-109">*destination_expression*</span><span class="sxs-lookup"><span data-stu-id="28c15-109">*destination_expression*</span></span>  
 <span data-ttu-id="28c15-110">(`Variant`) Uma expressão que é avaliada para cada linha em um conjunto de dados e que especifica o nome ou a chave para correspondência.</span><span class="sxs-lookup"><span data-stu-id="28c15-110">(`Variant`) An expression that is evaluated for each row in a dataset and that specifies the name or key to match on.</span></span> <span data-ttu-id="28c15-111">Por exemplo, `=Fields!CustomerID.Value`.</span><span class="sxs-lookup"><span data-stu-id="28c15-111">For example, `=Fields!CustomerID.Value`.</span></span>  
  
 <span data-ttu-id="28c15-112">*result_expression*</span><span class="sxs-lookup"><span data-stu-id="28c15-112">*result_expression*</span></span>  
 <span data-ttu-id="28c15-113">( `Variant` ) Uma expressão que é avaliada para a linha no conjunto de linhas em que *source_expression*  =  *destination_expression*e que especifica o valor a ser recuperado.</span><span class="sxs-lookup"><span data-stu-id="28c15-113">(`Variant`) An expression that is evaluated for the row in the dataset where *source_expression* = *destination_expression*, and that specifies the value to retrieve.</span></span> <span data-ttu-id="28c15-114">Por exemplo, `=Fields!PhoneNumber.Value`.</span><span class="sxs-lookup"><span data-stu-id="28c15-114">For example, `=Fields!PhoneNumber.Value`.</span></span>  
  
 <span data-ttu-id="28c15-115">*conjunto de dados*</span><span class="sxs-lookup"><span data-stu-id="28c15-115">*dataset*</span></span>  
 <span data-ttu-id="28c15-116">Uma constante que especifica o nome do conjunto de dados no relatório.</span><span class="sxs-lookup"><span data-stu-id="28c15-116">A constant that specifies the name of a dataset in the report.</span></span> <span data-ttu-id="28c15-117">Por exemplo, "ContactInformation".</span><span class="sxs-lookup"><span data-stu-id="28c15-117">For example, "ContactInformation".</span></span>  
  
## <a name="return"></a><span data-ttu-id="28c15-118">Retorno</span><span class="sxs-lookup"><span data-stu-id="28c15-118">Return</span></span>  
 <span data-ttu-id="28c15-119">Retorna `VariantArray` ou `Nothing` se não houver correspondência.</span><span class="sxs-lookup"><span data-stu-id="28c15-119">Returns a `VariantArray`, or `Nothing` if there is no match.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="28c15-120">Comentários</span><span class="sxs-lookup"><span data-stu-id="28c15-120">Remarks</span></span>  
 <span data-ttu-id="28c15-121">Use `LookupSet` para recuperar um conjunto de valores do conjunto de dados especificado para um par de nome/valor onde há uma relação de 1 para muitos.</span><span class="sxs-lookup"><span data-stu-id="28c15-121">Use `LookupSet` to retrieve a set of values from the specified dataset for a name/value pair where there is a 1-to-many relationship.</span></span> <span data-ttu-id="28c15-122">Por exemplo, para um identificador de cliente em uma tabela, você pode usar `LookupSet` para recuperar todos os números de telefone associados àquele cliente de um conjunto de dados que não esteja associado à região de dados.</span><span class="sxs-lookup"><span data-stu-id="28c15-122">For example, for a customer identifier in a table, you can use `LookupSet` to retrieve all the associated phone numbers for that customer from a dataset that is not bound to the data region.</span></span>  
  
 <span data-ttu-id="28c15-123">`LookupSet` faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="28c15-123">`LookupSet` does the following:</span></span>  
  
-   <span data-ttu-id="28c15-124">Avalia a expressão de origem no escopo atual.</span><span class="sxs-lookup"><span data-stu-id="28c15-124">Evaluates the source expression in the current scope.</span></span>  
  
-   <span data-ttu-id="28c15-125">Avalia a expressão de destino para cada linha do conjunto de dados especificado depois que foram aplicados filtros, com base na ordenação do conjunto de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="28c15-125">Evaluates the destination expression for each row of the specified dataset after filters have been applied, based on the collation of the specified dataset.</span></span>  
  
-   <span data-ttu-id="28c15-126">Para cada correspondência da expressão de origem e destino, avalia a expressão resultante para aquela linha no conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="28c15-126">For each match of source expression and destination expression, evaluates the result expression for that row in the dataset.</span></span>  
  
-   <span data-ttu-id="28c15-127">Retorna o conjunto de valores de expressão resultante.</span><span class="sxs-lookup"><span data-stu-id="28c15-127">Returns the set of result expression values.</span></span>  
  
 <span data-ttu-id="28c15-128">Para recuperar um único valor de um conjunto de dados com pares nome/valor de um nome especificado em que existe uma relação um-para-um, use [Função Lookup &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-lookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="28c15-128">To retrieve a single value from a dataset with name/value pairs for a specified name where there is a 1-to-1 relationship, use [Lookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-lookup-function.md).</span></span> <span data-ttu-id="28c15-129">Para chamar `Lookup` um conjunto de valores, use a [função multilookup &#40;Construtor de relatórios e o SSRS&#41;](report-builder-functions-multilookup-function.md).</span><span class="sxs-lookup"><span data-stu-id="28c15-129">To call `Lookup` for a set of values, use [Multilookup Function &#40;Report Builder and SSRS&#41;](report-builder-functions-multilookup-function.md).</span></span>  
  
 <span data-ttu-id="28c15-130">As restrições a seguir se aplicam:</span><span class="sxs-lookup"><span data-stu-id="28c15-130">The following restrictions apply:</span></span>  
  
-   <span data-ttu-id="28c15-131">`LookupSet` é avaliado depois que todas as expressões de filtro são aplicadas.</span><span class="sxs-lookup"><span data-stu-id="28c15-131">`LookupSet` is evaluated after all filter expressions are applied.</span></span>  
  
-   <span data-ttu-id="28c15-132">Só um nível de pesquisa tem suporte.</span><span class="sxs-lookup"><span data-stu-id="28c15-132">Only one level of lookup is supported.</span></span> <span data-ttu-id="28c15-133">Uma expressão de origem, destino ou resultado não pode incluir uma referência a uma função de pesquisa.</span><span class="sxs-lookup"><span data-stu-id="28c15-133">A source, destination, or result expression cannot include a reference to a lookup function.</span></span>  
  
-   <span data-ttu-id="28c15-134">Expressões de origem e destino devem ser avaliadas como o mesmo tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="28c15-134">Source and destination expressions must evaluate to the same data type.</span></span>  
  
-   <span data-ttu-id="28c15-135">Expressões de origem, destino e resultado não podem incluir referências a variáveis de relatório ou grupo.</span><span class="sxs-lookup"><span data-stu-id="28c15-135">Source, destination, and result expressions cannot include references to report or group variables.</span></span>  
  
-   <span data-ttu-id="28c15-136">`LookupSet` não pode ser usado como uma expressão para os seguintes itens de relatório:</span><span class="sxs-lookup"><span data-stu-id="28c15-136">`LookupSet` cannot be used as an expression for the following report items:</span></span>  
  
    -   <span data-ttu-id="28c15-137">Cadeias de conexão dinâmicas para uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="28c15-137">Dynamic connection strings for a data source.</span></span>  
  
    -   <span data-ttu-id="28c15-138">Campos calculados em um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="28c15-138">Calculated fields in a dataset.</span></span>  
  
    -   <span data-ttu-id="28c15-139">Parâmetros de consulta em um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="28c15-139">Query parameters in a dataset.</span></span>  
  
    -   <span data-ttu-id="28c15-140">Filtros em um conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="28c15-140">Filters in a dataset.</span></span>  
  
    -   <span data-ttu-id="28c15-141">Parâmetros de relatório.</span><span class="sxs-lookup"><span data-stu-id="28c15-141">Report parameters.</span></span>  
  
    -   <span data-ttu-id="28c15-142">A propriedade Report.Language.</span><span class="sxs-lookup"><span data-stu-id="28c15-142">The Report.Language property.</span></span>  
  
 <span data-ttu-id="28c15-143">Para obter mais informações, consulte [Referência de funções de agregação &#40;Construtor de Relatórios e SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) e [Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span><span class="sxs-lookup"><span data-stu-id="28c15-143">For more information, see [Aggregate Functions Reference &#40;Report Builder and SSRS&#41;](report-builder-functions-aggregate-functions-reference.md) and [Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;](expression-scope-for-totals-aggregates-and-built-in-collections.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="28c15-144">Exemplo</span><span class="sxs-lookup"><span data-stu-id="28c15-144">Example</span></span>  
 <span data-ttu-id="28c15-145">No exemplo seguinte, suponha que a tabela esteja associada a um conjunto de dados que inclui um identificador de território de vendas TerritoryGroupID.</span><span class="sxs-lookup"><span data-stu-id="28c15-145">In the following example, assume the table is bound to a dataset that includes a sales territory identifier TerritoryGroupID.</span></span> <span data-ttu-id="28c15-146">Um conjunto de dados separado chamado "Repositórios" contém a lista de todos os repositórios em um território e inclui o identificador ID de território e o nome do repositório StoreName.</span><span class="sxs-lookup"><span data-stu-id="28c15-146">A separate dataset called "Stores" contains the list of all stores in a territory and includes the territory identifier ID and the name of the store StoreName.</span></span>  
  
 <span data-ttu-id="28c15-147">A expressão `LookupSet` compara o valor TerritoryGroupID à ID de cada linha no conjunto de dados chamado "Repositórios".</span><span class="sxs-lookup"><span data-stu-id="28c15-147">In the following expression, `LookupSet` compares the value TerritoryGroupID to ID for each row in the dataset called "Stores".</span></span> <span data-ttu-id="28c15-148">Para cada correspondência, o valor do campo StoreName para aquela linha é acrescentado ao conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="28c15-148">For each match, the value of the StoreName field for that row is added to the result set.</span></span>  
  
```  
=LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores")  
```  
  
## <a name="example"></a><span data-ttu-id="28c15-149">Exemplo</span><span class="sxs-lookup"><span data-stu-id="28c15-149">Example</span></span>  
 <span data-ttu-id="28c15-150">Como `LookupSet` retorna uma coleção de objetos, você não pode exibir a expressão de resultado diretamente em uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="28c15-150">Because `LookupSet` returns a collection of objects, you cannot display the result expression directly in a text box.</span></span> <span data-ttu-id="28c15-151">Você pode concatenar o valor de cada objeto na coleção como uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="28c15-151">You can concatenate the value of each object in the collection as a string.</span></span>  
  
 <span data-ttu-id="28c15-152">Use a função `Join` do [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] e crie uma cadeia delimitada a partir de um conjunto de objetos.</span><span class="sxs-lookup"><span data-stu-id="28c15-152">Use the [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] function `Join` create a delimited string from a set of objects.</span></span> <span data-ttu-id="28c15-153">Use vírgula como separador combinar os objetos em uma única linha.</span><span class="sxs-lookup"><span data-stu-id="28c15-153">Use a comma as a separator to combine the objects in a single line.</span></span> <span data-ttu-id="28c15-154">Em alguns renderizadores, você pode usar uma alimentação de linha ( [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] ) do`vbCrLF`como um separador para listar cada valor em uma nova linha.</span><span class="sxs-lookup"><span data-stu-id="28c15-154">In some renderers, you might use a [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] line feed (`vbCrLF`) as a separator to list each value on a new line.</span></span>  
  
 <span data-ttu-id="28c15-155">A expressão a seguir, quando usada como a propriedade Value para uma caixa de texto, usa `Join` para criar uma lista.</span><span class="sxs-lookup"><span data-stu-id="28c15-155">The following expression, when it is used as the Value property for a text box, uses `Join` to create a list.</span></span>  
  
```  
=Join(LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores"),",")  
```  
  
## <a name="example"></a><span data-ttu-id="28c15-156">Exemplo</span><span class="sxs-lookup"><span data-stu-id="28c15-156">Example</span></span>  
 <span data-ttu-id="28c15-157">Para caixas de texto que só renderizam algumas vezes, você pode escolher adicionar código personalizado para gerar HTML para exibir valores em uma caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="28c15-157">For text boxes that only render a few times, you might choose to add custom code to generate HTML to display values in a text box.</span></span> <span data-ttu-id="28c15-158">O HTML em uma caixa de texto requer processamento extra; portanto, não é uma boa escolha para uma caixa de texto que é renderizada milhares de vezes.</span><span class="sxs-lookup"><span data-stu-id="28c15-158">HTML in a text box requires extra processing, so this would not be a good choice for a text box that is rendered thousands of times.</span></span>  
  
 <span data-ttu-id="28c15-159">Copiar as seguintes funções do [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] para um bloco Code em uma definição de relatório.</span><span class="sxs-lookup"><span data-stu-id="28c15-159">Copy the following [!INCLUDE[vbprvb](../../includes/vbprvb-md.md)] functions to a Code block in a report definition.</span></span> <span data-ttu-id="28c15-160">**MakeList** considera a matriz de objetos que é retornada em *result_expression* e compila uma lista não ordenada usando marcas HTML.</span><span class="sxs-lookup"><span data-stu-id="28c15-160">**MakeList** takes the object array that is returned in *result_expression* and builds an unordered list by using HTML tags.</span></span> <span data-ttu-id="28c15-161">**Length** retorna o número de itens em uma matriz de objetos.</span><span class="sxs-lookup"><span data-stu-id="28c15-161">**Length** returns the number of items in the object array.</span></span>  
  
```  
Function MakeList(ByVal items As Object()) As String  
   If items Is Nothing Then  
      Return Nothing  
   End If  
  
   Dim builder As System.Text.StringBuilder =   
      New System.Text.StringBuilder()  
   builder.Append("<ul>")  
  
   For Each item As Object In items  
      builder.Append("<li>")  
      builder.Append(item)  
   Next  
   builder.Append("</ul>")  
  
   Return builder.ToString()  
End Function  
  
Function Length(ByVal items as Object()) as Integer  
   If items is Nothing Then  
      Return 0  
   End If  
   Return items.Length  
End Function  
```  
  
## <a name="example"></a><span data-ttu-id="28c15-162">Exemplo</span><span class="sxs-lookup"><span data-stu-id="28c15-162">Example</span></span>  
 <span data-ttu-id="28c15-163">Para gerar o HTML, você deve chamar a função.</span><span class="sxs-lookup"><span data-stu-id="28c15-163">To generate the HTML, you must call the function.</span></span> <span data-ttu-id="28c15-164">Cole a expressão seguinte na propriedade Value para a caixa de texto e defina o tipo de marcação para texto como HTML.</span><span class="sxs-lookup"><span data-stu-id="28c15-164">Paste the following expression in the Value property for the text box and set the markup type for text to HTML.</span></span> <span data-ttu-id="28c15-165">Para obter mais informações, consulte [Adicionar HTML a um relatório &#40;Construtor de Relatórios e SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="28c15-165">For more information, see [Add HTML into a Report &#40;Report Builder and SSRS&#41;](add-html-into-a-report-report-builder-and-ssrs.md).</span></span>  
  
```  
=Code.MakeList(LookupSet(Fields!TerritoryGroupID.Value, Fields!ID.Value, Fields!StoreName.Value, "Stores"))  
```  
  
## <a name="see-also"></a><span data-ttu-id="28c15-166">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="28c15-166">See Also</span></span>  
 <span data-ttu-id="28c15-167">[Usos de expressões em relatórios &#40;Construtor de Relatórios e SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28c15-167">[Expression Uses in Reports &#40;Report Builder and SSRS&#41;](expression-uses-in-reports-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="28c15-168">[Exemplos de expressões &#40;Construtor de Relatórios e SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28c15-168">[Expression Examples &#40;Report Builder and SSRS&#41;](expression-examples-report-builder-and-ssrs.md) </span></span>  
 <span data-ttu-id="28c15-169">[Tipos de dados em expressões &#40;Construtor de Relatórios e SSRS&#41;](expressions-report-builder-and-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="28c15-169">[Data Types in Expressions &#40;Report Builder and SSRS&#41;](expressions-report-builder-and-ssrs.md) </span></span>  
 [<span data-ttu-id="28c15-170">Escopo das expressões para totais, agregações e coleções internas &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="28c15-170">Expression Scope for Totals, Aggregates, and Built-in Collections &#40;Report Builder and SSRS&#41;</span></span>](expression-scope-for-totals-aggregates-and-built-in-collections.md)  
  
  
