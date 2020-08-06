---
title: Sintaxe básica da cláusula FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- BINARY BASE64 directive
- ROOT directive
- FOR XML clause, BINARY BASE64 directive
- FOR XML clause, syntax
- FOR XML clause, ROOT directive
ms.assetid: df19ecbf-d28e-4e9c-aaa3-700f8bbd3be4
author: rothja
ms.author: jroth
ms.openlocfilehash: dc0410e7a54674673f64442d8a3cf9476d250033
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569251"
---
# <a name="basic-syntax-of-the-for-xml-clause"></a><span data-ttu-id="12f25-102">Sintaxe básica da cláusula FOR XML</span><span class="sxs-lookup"><span data-stu-id="12f25-102">Basic Syntax of the FOR XML Clause</span></span>
  <span data-ttu-id="12f25-103">O modo FOR XML pode ser RAW, AUTO, EXPLICIT ou PATH.</span><span class="sxs-lookup"><span data-stu-id="12f25-103">The FOR XML mode can be RAW, AUTO, EXPLICIT, or PATH.</span></span> <span data-ttu-id="12f25-104">Ele determina a forma do XML resultante.</span><span class="sxs-lookup"><span data-stu-id="12f25-104">It determines the shape of the resulting XML.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="12f25-105">A diretiva XMLDATA para a opção FOR XML foi preterida.</span><span class="sxs-lookup"><span data-stu-id="12f25-105">The XMLDATA directive to the FOR XML option is deprecated.</span></span> <span data-ttu-id="12f25-106">Use geração de XSD no caso dos modos RAW e AUTO.</span><span class="sxs-lookup"><span data-stu-id="12f25-106">Use XSD generation in the case of RAW and AUTO modes.</span></span> <span data-ttu-id="12f25-107">Não há substituição para a diretiva XMLDATA no modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="12f25-107">There is no replacement for the XMLDATA directive in EXPLICT mode.</span></span> [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)]  
  
 <span data-ttu-id="12f25-108">Veja a seguir a sintaxe básica que é descrita na [cláusula for (Transact-SQL)](/sql/t-sql/queries/select-for-clause-transact-sql):</span><span class="sxs-lookup"><span data-stu-id="12f25-108">Following is the basic syntax that is described in [FOR Clause (Transact-SQL)](/sql/t-sql/queries/select-for-clause-transact-sql):</span></span>  
  
```  
[ FOR { BROWSE | <XML> } ]  
<XML> ::=  
XML   
    {   
      { RAW [ ('ElementName') ] | AUTO }   
        [   
           <CommonDirectives>   
           [ , { XMLDATA | XMLSCHEMA [ ('TargetNameSpaceURI') ]} ]   
           [ , ELEMENTS [ XSINIL | ABSENT ]   
        ]  
      | EXPLICIT   
        [   
           <CommonDirectives>   
           [ , XMLDATA ]   
        ]  
      | PATH [ ('ElementName') ]   
        [   
           <CommonDirectives>   
           [ , ELEMENTS [ XSINIL | ABSENT ] ]  
        ]  
     }   
  
 <CommonDirectives> ::=   
   [ , BINARY BASE64 ]  
   [ , TYPE ]  
   [ , ROOT [ ('RootName') ] ]  
```  
  
## <a name="arguments"></a><span data-ttu-id="12f25-109">Argumentos</span><span class="sxs-lookup"><span data-stu-id="12f25-109">Arguments</span></span>  
 <span data-ttu-id="12f25-110">RAW[('*ElementName*')]</span><span class="sxs-lookup"><span data-stu-id="12f25-110">RAW[('*ElementName*')]</span></span>  
 <span data-ttu-id="12f25-111">Pega o resultado da consulta e transforma cada linha no conjunto de resultados em um elemento XML com um identificador genérico, \<row />, como a marca do elemento.</span><span class="sxs-lookup"><span data-stu-id="12f25-111">Takes the query result and transforms each row in the result set into an XML element that has a generic identifier, \<row />, as the element tag.</span></span> <span data-ttu-id="12f25-112">Opcionalmente, é possível especificar um nome para o elemento de linha ao usar esta diretiva.</span><span class="sxs-lookup"><span data-stu-id="12f25-112">You can optionally specify a name for the row element when you use this directive.</span></span> <span data-ttu-id="12f25-113">O XML resultante usará o *ElementName* especificado como o elemento de linha gerado para cada linha.</span><span class="sxs-lookup"><span data-stu-id="12f25-113">The resulting XML will use the specified *ElementName* as the row element generated for each row.</span></span> <span data-ttu-id="12f25-114">Para obter mais informações, consulte [Usar modo RAW com FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="12f25-114">For more information, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="12f25-115">AUTO</span><span class="sxs-lookup"><span data-stu-id="12f25-115">AUTO</span></span>  
 <span data-ttu-id="12f25-116">Retorna os resultados da consulta em uma árvore XML simples e aninhada.</span><span class="sxs-lookup"><span data-stu-id="12f25-116">Returns query results in a simple, nested XML tree.</span></span> <span data-ttu-id="12f25-117">Cada tabela na cláusula FROM para a qual pelo menos uma coluna está listada na cláusula SELECT é representada como um elemento XML.</span><span class="sxs-lookup"><span data-stu-id="12f25-117">Each table in the FROM clause for which at least one column is listed in the SELECT clause is represented as an XML element.</span></span> <span data-ttu-id="12f25-118">As colunas listadas na cláusula SELECT são mapeadas para os atributos apropriados do elemento.</span><span class="sxs-lookup"><span data-stu-id="12f25-118">The columns listed in the SELECT clause are mapped to the appropriate element attributes.</span></span> <span data-ttu-id="12f25-119">Para obter mais informações, consulte [Usar modo AUTO com FOR XML](use-auto-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="12f25-119">For more information, see [Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="12f25-120">EXPLICIT</span><span class="sxs-lookup"><span data-stu-id="12f25-120">EXPLICIT</span></span>  
 <span data-ttu-id="12f25-121">Especifica que a forma da árvore XML resultante está explicitamente definida.</span><span class="sxs-lookup"><span data-stu-id="12f25-121">Specifies that the shape of the resulting XML tree is defined explicitly.</span></span> <span data-ttu-id="12f25-122">Usando esse modo, as consultas devem ser escritas de uma maneira específica para que informações adicionais sobre o aninhamento desejado sejam especificadas explicitamente.</span><span class="sxs-lookup"><span data-stu-id="12f25-122">By using this mode, queries must be written in a particular way so additional information about the nesting you want is specified explicitly.</span></span> <span data-ttu-id="12f25-123">Para obter mais informações, consulte [Usar modo EXPLICIT com FOR XML](use-explicit-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="12f25-123">For more information, see [Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="12f25-124">PATH</span><span class="sxs-lookup"><span data-stu-id="12f25-124">PATH</span></span>  
 <span data-ttu-id="12f25-125">Fornece um modo mais simples de misturar elementos e atributos e introduzir aninhamento adicional para representar propriedades complexas.</span><span class="sxs-lookup"><span data-stu-id="12f25-125">Provides a simpler way to mix elements and attributes, and to introduce additional nesting for representing complex properties.</span></span> <span data-ttu-id="12f25-126">É possível usar consultas em modo FOR XML EXPLICIT para construir esse tipo de XML a partir de um conjunto de linhas, mas o modo PATH fornece uma alternativa mais simples para as consultas em modo EXPLICIT que provavelmente são trabalhosas.</span><span class="sxs-lookup"><span data-stu-id="12f25-126">You can use FOR XML EXPLICIT mode queries to construct this kind of XML from a rowset, but the PATH mode provides a simpler alternative to the possibly cumbersome EXPLICIT mode queries.</span></span> <span data-ttu-id="12f25-127">O modo PATH, juntamente com a capacidade de escrever consultas FOR XML aninhadas e a diretiva TYPE para retornar instâncias do tipo **xml** , permite escrever consultas com menos complexidade.</span><span class="sxs-lookup"><span data-stu-id="12f25-127">PATH mode, together with the ability to write nested FOR XML queries and the TYPE directive to return **xml** type instances, allows you to write queries with less complexity.</span></span> <span data-ttu-id="12f25-128">Ele fornece uma alternativa a escrita da maioria das consultas em modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="12f25-128">It provides an alternative to writing most EXPLICIT mode queries.</span></span> <span data-ttu-id="12f25-129">Por padrão, o modo PATH gera um wrapper de elemento \<row> para cada linha do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="12f25-129">By default, PATH mode generates a \<row> element wrapper for each row in the result set.</span></span> <span data-ttu-id="12f25-130">Opcionalmente, é possível especificar um nome de elemento.</span><span class="sxs-lookup"><span data-stu-id="12f25-130">You can optionally specify an element name.</span></span> <span data-ttu-id="12f25-131">Nesse caso, o nome especificado será usado como o nome do elemento wrapper.</span><span class="sxs-lookup"><span data-stu-id="12f25-131">If you do, the specified name is used as the wrapper element name.</span></span> <span data-ttu-id="12f25-132">Se você fornecer uma cadeia de caracteres vazia (FOR XML PATH ('')), nenhum elemento wrapper será gerado.</span><span class="sxs-lookup"><span data-stu-id="12f25-132">If you provide an empty string (FOR XML PATH ('')), no wrapper element is generated.</span></span> <span data-ttu-id="12f25-133">Para obter mais informações, consulte [Usar modo PATH com FOR XML](use-path-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="12f25-133">For more information, see [Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="12f25-134">XMLDATA</span><span class="sxs-lookup"><span data-stu-id="12f25-134">XMLDATA</span></span>  
 <span data-ttu-id="12f25-135">Especifica que um esquema XDR (XML-Data Reduced) será retornado.</span><span class="sxs-lookup"><span data-stu-id="12f25-135">Specifies that an inline XML-Data Reduced (XDR) schema should be returned.</span></span> <span data-ttu-id="12f25-136">O esquema é pré-anexado ao documento como um esquema embutido.</span><span class="sxs-lookup"><span data-stu-id="12f25-136">The schema is prepended to the document as an inline schema.</span></span> <span data-ttu-id="12f25-137">Para obter um exemplo de funcionamento, consulte [Usar modo RAW com FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="12f25-137">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="12f25-138">XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="12f25-138">XMLSCHEMA</span></span>  
 <span data-ttu-id="12f25-139">Retorna um XSD (Esquema XML da W3C) embutido.</span><span class="sxs-lookup"><span data-stu-id="12f25-139">Returns an inline W3C XML Schema (XSD).</span></span> <span data-ttu-id="12f25-140">Opcionalmente, é possível especificar um URI de namespace de destino especificando esta diretiva.</span><span class="sxs-lookup"><span data-stu-id="12f25-140">You can optionally specify a target namespace URI when specifying this directive.</span></span> <span data-ttu-id="12f25-141">Isso retorna o namespace especificado no esquema.</span><span class="sxs-lookup"><span data-stu-id="12f25-141">This returns the specified namespace in the schema.</span></span> <span data-ttu-id="12f25-142">Para obter mais informações, consulte [Gerar um esquema XSD embutido](generate-an-inline-xsd-schema.md).</span><span class="sxs-lookup"><span data-stu-id="12f25-142">For more information, see [Generate an Inline XSD Schema](generate-an-inline-xsd-schema.md).</span></span> <span data-ttu-id="12f25-143">Para obter um exemplo de funcionamento, consulte [Usar modo RAW com FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="12f25-143">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="12f25-144">ELEMENTS</span><span class="sxs-lookup"><span data-stu-id="12f25-144">ELEMENTS</span></span>  
 <span data-ttu-id="12f25-145">Se a opção ELEMENTS for especificada, as colunas serão retornadas como subelementos.</span><span class="sxs-lookup"><span data-stu-id="12f25-145">If the ELEMENTS option is specified, the columns are returned as subelements.</span></span> <span data-ttu-id="12f25-146">Caso contrário, elas serão mapeadas para atributos XML.</span><span class="sxs-lookup"><span data-stu-id="12f25-146">Otherwise, they are mapped to XML attributes.</span></span> <span data-ttu-id="12f25-147">Essa opção tem suporte apenas nos modos RAW, AUTO e PATH.</span><span class="sxs-lookup"><span data-stu-id="12f25-147">This option is supported in RAW, AUTO, and PATH modes only.</span></span> <span data-ttu-id="12f25-148">Opcionalmente, é possível especificar XSINIL ou ABSENT ao usar esta diretiva.</span><span class="sxs-lookup"><span data-stu-id="12f25-148">You can optionally specify XSINIL or ABSENT when you use this directive.</span></span> <span data-ttu-id="12f25-149">XSINIL especifica que um elemento que tem um atributo **xsi:nil** definido como True seja criado para valores de colunas NULL.</span><span class="sxs-lookup"><span data-stu-id="12f25-149">XSINIL specifies that an element that has an **xsi:nil** attribute set to True be created for NULL column values.</span></span> <span data-ttu-id="12f25-150">Por padrão, ou quando ABSENT está especificado junto com ELEMENTS, nenhum elemento é criado para obter valores NULL.</span><span class="sxs-lookup"><span data-stu-id="12f25-150">By default or when ABSENT is specified together with ELEMENTS, no elements are created for NULL values.</span></span> <span data-ttu-id="12f25-151">Para obter um exemplo de funcionamento, consulte [Usar modo RAW com FOR XML](use-raw-mode-with-for-xml.md) e [Usar o modo AUTO com FOR XML](use-auto-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="12f25-151">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md) and [Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="12f25-152">BINARY BASE64</span><span class="sxs-lookup"><span data-stu-id="12f25-152">BINARY BASE64</span></span>  
 <span data-ttu-id="12f25-153">Se a opção BINARY Base64 for especificada, quaisquer dados binários retornados pela consulta serão representados no formato codificado na base64.</span><span class="sxs-lookup"><span data-stu-id="12f25-153">If the BINARY Base64 option is specified, any binary data returned by the query is represented in base64-encoded format.</span></span> <span data-ttu-id="12f25-154">Para recuperar dados binários usando o modo RAW e EXPLICIT, esta opção deve ser especificada.</span><span class="sxs-lookup"><span data-stu-id="12f25-154">To retrieve binary data by using RAW and EXPLICIT mode, this option must be specified.</span></span> <span data-ttu-id="12f25-155">Em modo AUTO, por padrão, os dados binários são retornados como uma referência.</span><span class="sxs-lookup"><span data-stu-id="12f25-155">In AUTO mode, binary data is returned as a reference by default.</span></span> <span data-ttu-id="12f25-156">Para obter um exemplo de funcionamento, consulte [Usar modo RAW com FOR XML](use-raw-mode-with-for-xml.md).</span><span class="sxs-lookup"><span data-stu-id="12f25-156">For a working sample, see [Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md).</span></span>  
  
 <span data-ttu-id="12f25-157">TYPE</span><span class="sxs-lookup"><span data-stu-id="12f25-157">TYPE</span></span>  
 <span data-ttu-id="12f25-158">Especifica que a consulta retorna os resultados como tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="12f25-158">Specifies that the query returns the results as the **xml** type.</span></span> <span data-ttu-id="12f25-159">Para obter mais informações, consulte [Diretiva TYPE em consultas FOR XML](type-directive-in-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="12f25-159">For more information, see [TYPE Directive in FOR XML Queries](type-directive-in-for-xml-queries.md).</span></span>  
  
 <span data-ttu-id="12f25-160">ROOT [('*RootName*')]</span><span class="sxs-lookup"><span data-stu-id="12f25-160">ROOT [('*RootName*')]</span></span>  
 <span data-ttu-id="12f25-161">Especifica que um único elemento de nível superior seja adicionado ao XML resultante.</span><span class="sxs-lookup"><span data-stu-id="12f25-161">Specifies that a single, top-level element be added to the resulting XML.</span></span> <span data-ttu-id="12f25-162">Opcionalmente, é possível especificar o nome do elemento raiz a ser gerado.</span><span class="sxs-lookup"><span data-stu-id="12f25-162">You can optionally specify the root element name to generate.</span></span> <span data-ttu-id="12f25-163">O valor padrão é "root".</span><span class="sxs-lookup"><span data-stu-id="12f25-163">The default value is "root".</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="12f25-164">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="12f25-164">See Also</span></span>  
 <span data-ttu-id="12f25-165">[Usar modo RAW com FOR XML](use-raw-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="12f25-165">[Use RAW Mode with FOR XML](use-raw-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="12f25-166">[Usar o modo AUTO com FOR XML](use-auto-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="12f25-166">[Use AUTO Mode with FOR XML](use-auto-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="12f25-167">[Usar o modo EXPLICIT com FOR XML](use-explicit-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="12f25-167">[Use EXPLICIT Mode with FOR XML](use-explicit-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="12f25-168">[Usar o modo PATH com FOR XML](use-path-mode-with-for-xml.md) </span><span class="sxs-lookup"><span data-stu-id="12f25-168">[Use PATH Mode with FOR XML](use-path-mode-with-for-xml.md) </span></span>  
 <span data-ttu-id="12f25-169">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="12f25-169">[SELECT &#40;Transact-SQL&#41;](/sql/t-sql/queries/select-transact-sql) </span></span>  
 [<span data-ttu-id="12f25-170">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="12f25-170">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
