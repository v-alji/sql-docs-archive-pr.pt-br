---
title: Sintaxe do caminho do elemento para dados de relatório XML (SSRS) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: reporting-services-native
ms.topic: conceptual
helpviewer_keywords:
- ElementPath syntax
- XML [Reporting Services], data retrieval
ms.assetid: 07bd7a4e-fd7a-4a72-9344-3258f7c286d1
author: maggiesMSFT
ms.author: maggies
manager: kfile
ms.openlocfilehash: b7d66b39761dc278abff25a3b22ccd18ca74272b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686086"
---
# <a name="element-path-syntax-for-xml-report-data-ssrs"></a><span data-ttu-id="c82c3-102">Sintaxe do caminho do elemento para dados de relatório XML (SSRS)</span><span class="sxs-lookup"><span data-stu-id="c82c3-102">Element Path Syntax for XML Report Data (SSRS)</span></span>
  <span data-ttu-id="c82c3-103">No Designer de Relatórios, você especifica os dados para uso em um relatório de uma fonte de dados XML definindo um caminho do elemento que faz distinção entre maiúsculas e minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c82c3-103">In Report Designer, you specify the data to use for a report from an XML data source by defining a case-sensitive element path.</span></span> <span data-ttu-id="c82c3-104">Um caminho de elemento indica como transpor os nós hierárquicos XML e seus atributos na fonte de dados XML.</span><span class="sxs-lookup"><span data-stu-id="c82c3-104">An element path indicates how to traverse the XML hierarchical nodes and their attributes in the XML data source.</span></span> <span data-ttu-id="c82c3-105">Para usar o caminho do elemento padrão, deixe a consulta do conjunto de dados ou o `ElementPath` XML da `Query` XML vazio.</span><span class="sxs-lookup"><span data-stu-id="c82c3-105">To use the default element path, leave the dataset query or the XML `ElementPath` of the XML `Query` empty.</span></span> <span data-ttu-id="c82c3-106">Quando os dados são recuperados da fonte de dados XML, os nós do elemento que possuem valores de texto e os atributos do nó do elemento se tornam colunas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="c82c3-106">When data is retrieved from the XML data source, element nodes that have text values and element node attributes become columns in the result set.</span></span> <span data-ttu-id="c82c3-107">Os valores dos nós e atributos tornam-se os dados da linha quando a consulta é executada.</span><span class="sxs-lookup"><span data-stu-id="c82c3-107">The values of the nodes and attributes become the row data when you run the query.</span></span> <span data-ttu-id="c82c3-108">As colunas são exibidas como a coleção de campos do conjunto de dados no painel de dados do relatório.</span><span class="sxs-lookup"><span data-stu-id="c82c3-108">The columns appear as the dataset field collection in the Report Data pane.</span></span> <span data-ttu-id="c82c3-109">Este tópico descreve a sintaxe do caminho do elemento.</span><span class="sxs-lookup"><span data-stu-id="c82c3-109">This topic describes the element path syntax.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c82c3-110">A sintaxe do caminho do elemento é independente do namespace.</span><span class="sxs-lookup"><span data-stu-id="c82c3-110">Element path syntax is namespace-independent.</span></span> <span data-ttu-id="c82c3-111">Para usar namespaces em um caminho de elemento, use a sintaxe de consulta XML que inclui um `ElementPath` elemento XML descrito em [sintaxe de consulta XML para dados de relatório xml &#40;&#41;do SSRS ](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c82c3-111">To use namespaces in an element path, use the XML query syntax that includes an XML `ElementPath` element described in [XML Query Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>  
  
 <span data-ttu-id="c82c3-112">A tabela a seguir descreve as convenções usadas para definir um caminho de elemento.</span><span class="sxs-lookup"><span data-stu-id="c82c3-112">The following table describes conventions used to define an element path.</span></span>  
  
|<span data-ttu-id="c82c3-113">Convenção</span><span class="sxs-lookup"><span data-stu-id="c82c3-113">Convention</span></span>|<span data-ttu-id="c82c3-114">Usado para</span><span class="sxs-lookup"><span data-stu-id="c82c3-114">Used for</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="c82c3-115">**bold**</span><span class="sxs-lookup"><span data-stu-id="c82c3-115">**bold**</span></span>|<span data-ttu-id="c82c3-116">Texto que deve ser digitado exatamente como mostrado.</span><span class="sxs-lookup"><span data-stu-id="c82c3-116">Text that must be typed exactly as shown.</span></span>|  
|<span data-ttu-id="c82c3-117">&#124; (barra vertical)</span><span class="sxs-lookup"><span data-stu-id="c82c3-117">&#124; (vertical bar)</span></span>|<span data-ttu-id="c82c3-118">Separa itens de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="c82c3-118">Separates syntax items.</span></span> <span data-ttu-id="c82c3-119">Somente um desses itens poderá ser selecionado.</span><span class="sxs-lookup"><span data-stu-id="c82c3-119">You can choose only one of the items.</span></span>|  
|`[ ] (brackets)`|<span data-ttu-id="c82c3-120">Itens de sintaxe opcionais.</span><span class="sxs-lookup"><span data-stu-id="c82c3-120">Optional syntax items.</span></span> <span data-ttu-id="c82c3-121">Não digite os colchetes.</span><span class="sxs-lookup"><span data-stu-id="c82c3-121">Do not type the brackets.</span></span>|  
|<span data-ttu-id="c82c3-122">**{}** (chaves)</span><span class="sxs-lookup"><span data-stu-id="c82c3-122">**{ }** (braces)</span></span>|<span data-ttu-id="c82c3-123">Delimita parâmetros de itens de sintaxe.</span><span class="sxs-lookup"><span data-stu-id="c82c3-123">Delimits parameters of syntax items.</span></span>|  
|<span data-ttu-id="c82c3-124">[ **,** ...*n*]</span><span class="sxs-lookup"><span data-stu-id="c82c3-124">[**,**...*n*]</span></span>|<span data-ttu-id="c82c3-125">Indica que o item precedente pode ser repetido *n* vezes.</span><span class="sxs-lookup"><span data-stu-id="c82c3-125">Indicates the preceding item can be repeated *n* number of times.</span></span> <span data-ttu-id="c82c3-126">As ocorrências são separadas por vírgulas.</span><span class="sxs-lookup"><span data-stu-id="c82c3-126">The occurrences are separated by commas.</span></span>|  
  
## <a name="syntax"></a><span data-ttu-id="c82c3-127">Sintaxe</span><span class="sxs-lookup"><span data-stu-id="c82c3-127">Syntax</span></span>  
  
```  
  
Element path ::=  
    ElementNode[/Element path]  
ElementNode ::=  
    XMLName[(Encoding)][{[FieldList]}]  
XMLName ::=  
    [NamespacePrefix:]XMLLocalName  
Encoding ::=  
        HTMLEncoded | Base64Encoded  
FieldList ::=  
    Field[,FieldList]  
Field ::=  
    Attribute | Value | Element | ElementNode  
Attribute ::=  
        @XMLName[(Type)]  
Value ::=  
        @[(Type)]  
Element ::=  
    XMLName[(Type)]  
Type ::=  
        String | Integer | Boolean | Float | Decimal | Date | XML   
NamespacePrefix ::=  
    Identifier that specifies the namespace.  
XMLLocalName :: =  
    Identifier in the XML tag.   
```  
  
## <a name="remarks"></a><span data-ttu-id="c82c3-128">Comentários</span><span class="sxs-lookup"><span data-stu-id="c82c3-128">Remarks</span></span>  
 <span data-ttu-id="c82c3-129">A tabela a seguir resume os termos do caminho do elemento.</span><span class="sxs-lookup"><span data-stu-id="c82c3-129">The following table summarizes element path terms.</span></span> <span data-ttu-id="c82c3-130">Os exemplos na tabela referem-se ao documento XML de exemplo Customers.xml, que está incluído na seção Exemplos deste tópico.</span><span class="sxs-lookup"><span data-stu-id="c82c3-130">Examples in the table refer to the example XML document Customers.xml, which is included in the Examples section of this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c82c3-131">As marcas XML diferenciam maiúsculas de minúsculas.</span><span class="sxs-lookup"><span data-stu-id="c82c3-131">XML tags are case-sensitive.</span></span> <span data-ttu-id="c82c3-132">Ao especificar um ElementNode no caminho do elemento, você deve corresponder exatamente as marcas XML na fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c82c3-132">When you specify an ElementNode in the element path, you must exactly match the XML tags in the data source.</span></span>  
  
|<span data-ttu-id="c82c3-133">Termo</span><span class="sxs-lookup"><span data-stu-id="c82c3-133">Term</span></span>|<span data-ttu-id="c82c3-134">Definição</span><span class="sxs-lookup"><span data-stu-id="c82c3-134">Definition</span></span>|  
|----------|----------------|  
|<span data-ttu-id="c82c3-135">Caminho do elemento</span><span class="sxs-lookup"><span data-stu-id="c82c3-135">Element path</span></span>|<span data-ttu-id="c82c3-136">Define a sequência de nós a serem transpostos dentro do documento XML para recuperar dados do campo para um conjunto de dados com uma fonte de dados XML.</span><span class="sxs-lookup"><span data-stu-id="c82c3-136">Defines the sequence of nodes to traverse within the XML document in order to retrieve field data for a dataset with an XML data source.</span></span>|  
|`ElementNode`|<span data-ttu-id="c82c3-137">O nó XML no documento XML.</span><span class="sxs-lookup"><span data-stu-id="c82c3-137">The XML node in the XML document.</span></span> <span data-ttu-id="c82c3-138">Os nós são designados por marcas e existem em uma relação hierárquica com outros nós.</span><span class="sxs-lookup"><span data-stu-id="c82c3-138">Nodes are designated by tags and exist in a hierarchical relationship with other nodes.</span></span> <span data-ttu-id="c82c3-139">Por exemplo, \<Customers> é o nó do elemento raiz.</span><span class="sxs-lookup"><span data-stu-id="c82c3-139">For example, \<Customers> is the root element node.</span></span> <span data-ttu-id="c82c3-140">\<Customer>é um subelemento de \<Customers> .</span><span class="sxs-lookup"><span data-stu-id="c82c3-140">\<Customer> is a subelement of \<Customers>.</span></span>|  
|`XMLName`|<span data-ttu-id="c82c3-141">O nome do nó.</span><span class="sxs-lookup"><span data-stu-id="c82c3-141">The name of the node.</span></span> <span data-ttu-id="c82c3-142">Por exemplo, o nome do nó Clientes é Clientes.</span><span class="sxs-lookup"><span data-stu-id="c82c3-142">For example, the name of the Customers node is Customers.</span></span> <span data-ttu-id="c82c3-143">Um `XMLName` pode ser prefixado com um identificador de namespace para nomear exclusivamente cada nó.</span><span class="sxs-lookup"><span data-stu-id="c82c3-143">An `XMLName` can be prefixed with a namespace identifier to uniquely name every node.</span></span>|  
|`Encoding`|<span data-ttu-id="c82c3-144">Indica que o `Value` deste elemento é XML codificado e precisa ser decodificado e incluído como um subelemento desse elemento.</span><span class="sxs-lookup"><span data-stu-id="c82c3-144">Indicates that the `Value` for this element is encoded XML and needs to be decoded and included as a subelement of this element.</span></span>|  
|`FieldList`|<span data-ttu-id="c82c3-145">Define o conjunto de elementos e atributos a serem usados para recuperar dados.</span><span class="sxs-lookup"><span data-stu-id="c82c3-145">Defines the set of elements and attributes to use to retrieve data.</span></span><br /><br /> <span data-ttu-id="c82c3-146">Se não estiverem especificados, todos os atributos e subelementos serão usados como campos.</span><span class="sxs-lookup"><span data-stu-id="c82c3-146">If not specified, all attributes and subelements are used as fields.</span></span> <span data-ttu-id="c82c3-147">Se a lista de campos vazia for especificada ( **{}** ), nenhum campo desse nó será usado.</span><span class="sxs-lookup"><span data-stu-id="c82c3-147">If the empty field list is specified (**{}**), no fields from this node are used.</span></span><br /><br /> <span data-ttu-id="c82c3-148">Uma `FieldList` pode não conter um `Value` e um `Element` ou `ElementNode`.</span><span class="sxs-lookup"><span data-stu-id="c82c3-148">A `FieldList` may not contain both a `Value` and an `Element` or `ElementNode`.</span></span>|  
|`Field`|<span data-ttu-id="c82c3-149">Especifica os dados recuperados como um campo do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="c82c3-149">Specifies the data that is retrieved as a dataset field.</span></span>|  
|`Attribute`|<span data-ttu-id="c82c3-150">Um par de nome-valor dentro do `ElementNode`.</span><span class="sxs-lookup"><span data-stu-id="c82c3-150">A name-value pair within the `ElementNode`.</span></span> <span data-ttu-id="c82c3-151">Por exemplo, no nó do elemento \<Customer ID="1"> , `ID` é um atributo e `@ID(Integer)` retorna "1" como um tipo inteiro no campo de dados correspondente `ID` .</span><span class="sxs-lookup"><span data-stu-id="c82c3-151">For example, in the element node \<Customer ID="1">, `ID` is an attribute and `@ID(Integer)` returns "1" as an integer type in the corresponding data field `ID`.</span></span>|  
|`Value`|<span data-ttu-id="c82c3-152">O valor do elemento.</span><span class="sxs-lookup"><span data-stu-id="c82c3-152">The value of the element.</span></span> <span data-ttu-id="c82c3-153">`Value` pode ser usado apenas no último `ElementNode` no caminho do elemento.</span><span class="sxs-lookup"><span data-stu-id="c82c3-153">`Value` can only be used on the last `ElementNode` in the element path.</span></span> <span data-ttu-id="c82c3-154">Por exemplo, como \<Return> é um nó folha, se você o inclui no final de um caminho de elemento, o valor de `Return {@}` é `Chair` .</span><span class="sxs-lookup"><span data-stu-id="c82c3-154">For example, because \<Return> is a leaf node, if you include it at the end of an element path, the value of `Return {@}` is `Chair`.</span></span>|  
|`Element`|<span data-ttu-id="c82c3-155">O valor do subelemento nomeado.</span><span class="sxs-lookup"><span data-stu-id="c82c3-155">The value of the named subelement.</span></span> <span data-ttu-id="c82c3-156">Por exemplo, Clientes {}/Cliente {}/Sobrenome recupera valores apenas para o elemento Sobrenome.</span><span class="sxs-lookup"><span data-stu-id="c82c3-156">For example, Customers {}/Customer {}/LastName retrieves values for only the LastName element.</span></span>|  
|`Type`|<span data-ttu-id="c82c3-157">O tipo de dados opcional a ser usado para o campo criado desse elemento.</span><span class="sxs-lookup"><span data-stu-id="c82c3-157">The optional data type to use for the field created from this element.</span></span>|  
|`NamespacePrefix`|<span data-ttu-id="c82c3-158">O `NamespacePrefix` é definido no elemento Consulta XML.</span><span class="sxs-lookup"><span data-stu-id="c82c3-158">`NamespacePrefix` is defined in the XML Query element.</span></span> <span data-ttu-id="c82c3-159">Se não existir nenhum elemento Consulta XML, os namespaces no `ElementPath` XML serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="c82c3-159">If no XML Query element exists, namespaces in the XML `ElementPath` are ignored.</span></span> <span data-ttu-id="c82c3-160">Se existir um elemento Consulta XML, o `ElementPath` XML terá um atributo opcional `IgnoreNamespaces`.</span><span class="sxs-lookup"><span data-stu-id="c82c3-160">If there is an XML Query element, the XML `ElementPath` has an optional attribute `IgnoreNamespaces`.</span></span> <span data-ttu-id="c82c3-161">Se IgnoreNamespaces for `true` , os namespaces no XML `ElementPath` e no documento XML serão ignorados.</span><span class="sxs-lookup"><span data-stu-id="c82c3-161">If IgnoreNamespaces is `true`, namespaces in the XML `ElementPath` and the XML document are ignored.</span></span> <span data-ttu-id="c82c3-162">Para obter mais informações, consulte [Sintaxe de consulta XML para dados de relatório XML &#40;SSRS&#41;](report-data-ssrs.md).</span><span class="sxs-lookup"><span data-stu-id="c82c3-162">For more information, see [XML Query Syntax for XML Report Data &#40;SSRS&#41;](report-data-ssrs.md).</span></span>|  
  
## <a name="example---no-namespaces"></a><span data-ttu-id="c82c3-163">Exemplo – Nenhum namespace</span><span class="sxs-lookup"><span data-stu-id="c82c3-163">Example - No Namespaces</span></span>  
 <span data-ttu-id="c82c3-164">Os exemplos a seguir usam o documento XML Customers.xml.</span><span class="sxs-lookup"><span data-stu-id="c82c3-164">The following examples use the XML document Customers.xml.</span></span> <span data-ttu-id="c82c3-165">Esta tabela mostra exemplos de sintaxe do caminho do elemento e os resultados do uso do caminho do elemento em uma consulta que define um conjunto de dados, baseado no documento XML como uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="c82c3-165">This table shows examples of element path syntax and the results of using the element path in a query that defines a dataset, based on the XML document as a data source.</span></span>  
  
 <span data-ttu-id="c82c3-166">Observe que, quando o caminho do elemento está vazio, a consulta usa o caminho do elemento padrão: o primeiro caminho para uma coleção de nós folha.</span><span class="sxs-lookup"><span data-stu-id="c82c3-166">Note that when the element path is empty, the query uses the default element path: the first path to a leaf node collection.</span></span> <span data-ttu-id="c82c3-167">No primeiro exemplo, deixar o caminho do elemento vazio é equivalente a especificar o caminho do elemento /Clientes/Cliente/Pedidos/Pedido.</span><span class="sxs-lookup"><span data-stu-id="c82c3-167">In the first example, leaving the element path empty is equivalent to specifying the element path /Customers/Customer/Orders/Order.</span></span> <span data-ttu-id="c82c3-168">Todos os valores e atributos do nó ao longo do caminho são retornados no conjunto de resultados, e os nomes de nós e de atributos são exibidos como campos do conjunto de dados.</span><span class="sxs-lookup"><span data-stu-id="c82c3-168">All node value and attributes along the path are returned in the result set, and the node names and attributes names appear as dataset fields.</span></span>  
  
-   <span data-ttu-id="c82c3-169">*Vazio*</span><span class="sxs-lookup"><span data-stu-id="c82c3-169">*Empty*</span></span>  
  
    |<span data-ttu-id="c82c3-170">Order</span><span class="sxs-lookup"><span data-stu-id="c82c3-170">Order</span></span>|<span data-ttu-id="c82c3-171">Qtd</span><span class="sxs-lookup"><span data-stu-id="c82c3-171">Qty</span></span>|<span data-ttu-id="c82c3-172">ID</span><span class="sxs-lookup"><span data-stu-id="c82c3-172">ID</span></span>|<span data-ttu-id="c82c3-173">Nome</span><span class="sxs-lookup"><span data-stu-id="c82c3-173">FirstName</span></span>|<span data-ttu-id="c82c3-174">LastName</span><span class="sxs-lookup"><span data-stu-id="c82c3-174">LastName</span></span>|<span data-ttu-id="c82c3-175">Customer.ID</span><span class="sxs-lookup"><span data-stu-id="c82c3-175">Customer.ID</span></span>|<span data-ttu-id="c82c3-176">xmlns</span><span class="sxs-lookup"><span data-stu-id="c82c3-176">xmlns</span></span>|  
    |-----------|---------|--------|---------------|--------------|-----------------|-----------|  
    |<span data-ttu-id="c82c3-177">Chair</span><span class="sxs-lookup"><span data-stu-id="c82c3-177">Chair</span></span>|<span data-ttu-id="c82c3-178">6</span><span class="sxs-lookup"><span data-stu-id="c82c3-178">6</span></span>|<span data-ttu-id="c82c3-179">1</span><span class="sxs-lookup"><span data-stu-id="c82c3-179">1</span></span>|<span data-ttu-id="c82c3-180">Bobby</span><span class="sxs-lookup"><span data-stu-id="c82c3-180">Bobby</span></span>|<span data-ttu-id="c82c3-181">Moore</span><span class="sxs-lookup"><span data-stu-id="c82c3-181">Moore</span></span>|<span data-ttu-id="c82c3-182">11</span><span class="sxs-lookup"><span data-stu-id="c82c3-182">11</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="c82c3-183">Table</span><span class="sxs-lookup"><span data-stu-id="c82c3-183">Table</span></span>|<span data-ttu-id="c82c3-184">1</span><span class="sxs-lookup"><span data-stu-id="c82c3-184">1</span></span>|<span data-ttu-id="c82c3-185">2</span><span class="sxs-lookup"><span data-stu-id="c82c3-185">2</span></span>|<span data-ttu-id="c82c3-186">Bobby</span><span class="sxs-lookup"><span data-stu-id="c82c3-186">Bobby</span></span>|<span data-ttu-id="c82c3-187">Moore</span><span class="sxs-lookup"><span data-stu-id="c82c3-187">Moore</span></span>|<span data-ttu-id="c82c3-188">11</span><span class="sxs-lookup"><span data-stu-id="c82c3-188">11</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="c82c3-189">Sofa</span><span class="sxs-lookup"><span data-stu-id="c82c3-189">Sofa</span></span>|<span data-ttu-id="c82c3-190">2</span><span class="sxs-lookup"><span data-stu-id="c82c3-190">2</span></span>|<span data-ttu-id="c82c3-191">8</span><span class="sxs-lookup"><span data-stu-id="c82c3-191">8</span></span>|<span data-ttu-id="c82c3-192">Crystal</span><span class="sxs-lookup"><span data-stu-id="c82c3-192">Crystal</span></span>|<span data-ttu-id="c82c3-193">Hu</span><span class="sxs-lookup"><span data-stu-id="c82c3-193">Hu</span></span>|<span data-ttu-id="c82c3-194">20</span><span class="sxs-lookup"><span data-stu-id="c82c3-194">20</span></span>|http://www.adventure-works.com|  
    |<span data-ttu-id="c82c3-195">EndTables</span><span class="sxs-lookup"><span data-stu-id="c82c3-195">EndTables</span></span>|<span data-ttu-id="c82c3-196">2</span><span class="sxs-lookup"><span data-stu-id="c82c3-196">2</span></span>|<span data-ttu-id="c82c3-197">15</span><span class="sxs-lookup"><span data-stu-id="c82c3-197">15</span></span>|<span data-ttu-id="c82c3-198">Wyatt</span><span class="sxs-lookup"><span data-stu-id="c82c3-198">Wyatt</span></span>|<span data-ttu-id="c82c3-199">Diaz</span><span class="sxs-lookup"><span data-stu-id="c82c3-199">Diaz</span></span>|<span data-ttu-id="c82c3-200">33</span><span class="sxs-lookup"><span data-stu-id="c82c3-200">33</span></span>|http://www.adventure-works.com|  
  
-   `Customers {}/Customer`  
  
    |<span data-ttu-id="c82c3-201">Nome</span><span class="sxs-lookup"><span data-stu-id="c82c3-201">FirstName</span></span>|<span data-ttu-id="c82c3-202">LastName</span><span class="sxs-lookup"><span data-stu-id="c82c3-202">LastName</span></span>|<span data-ttu-id="c82c3-203">ID</span><span class="sxs-lookup"><span data-stu-id="c82c3-203">ID</span></span>|  
    |---------------|--------------|--------|  
    |<span data-ttu-id="c82c3-204">Bobby</span><span class="sxs-lookup"><span data-stu-id="c82c3-204">Bobby</span></span>|<span data-ttu-id="c82c3-205">Moore</span><span class="sxs-lookup"><span data-stu-id="c82c3-205">Moore</span></span>|<span data-ttu-id="c82c3-206">11</span><span class="sxs-lookup"><span data-stu-id="c82c3-206">11</span></span>|  
    |<span data-ttu-id="c82c3-207">Crystal</span><span class="sxs-lookup"><span data-stu-id="c82c3-207">Crystal</span></span>|<span data-ttu-id="c82c3-208">Hu</span><span class="sxs-lookup"><span data-stu-id="c82c3-208">Hu</span></span>|<span data-ttu-id="c82c3-209">20</span><span class="sxs-lookup"><span data-stu-id="c82c3-209">20</span></span>|  
    |<span data-ttu-id="c82c3-210">Wyatt</span><span class="sxs-lookup"><span data-stu-id="c82c3-210">Wyatt</span></span>|<span data-ttu-id="c82c3-211">Diaz</span><span class="sxs-lookup"><span data-stu-id="c82c3-211">Diaz</span></span>|<span data-ttu-id="c82c3-212">33</span><span class="sxs-lookup"><span data-stu-id="c82c3-212">33</span></span>|  
  
-   `Customers {}/Customer {}/LastName`  
  
    |<span data-ttu-id="c82c3-213">LastName</span><span class="sxs-lookup"><span data-stu-id="c82c3-213">LastName</span></span>|  
    |--------------|  
    |<span data-ttu-id="c82c3-214">Moore</span><span class="sxs-lookup"><span data-stu-id="c82c3-214">Moore</span></span>|  
    |<span data-ttu-id="c82c3-215">Hu</span><span class="sxs-lookup"><span data-stu-id="c82c3-215">Hu</span></span>|  
    |<span data-ttu-id="c82c3-216">Diaz</span><span class="sxs-lookup"><span data-stu-id="c82c3-216">Diaz</span></span>|  
  
-   `Customers {}/Customer {}/Orders/Order {@,@Qty}`  
  
    |<span data-ttu-id="c82c3-217">Order</span><span class="sxs-lookup"><span data-stu-id="c82c3-217">Order</span></span>|<span data-ttu-id="c82c3-218">Qtd</span><span class="sxs-lookup"><span data-stu-id="c82c3-218">Qty</span></span>|  
    |-----------|---------|  
    |<span data-ttu-id="c82c3-219">Chair</span><span class="sxs-lookup"><span data-stu-id="c82c3-219">Chair</span></span>|<span data-ttu-id="c82c3-220">6</span><span class="sxs-lookup"><span data-stu-id="c82c3-220">6</span></span>|  
    |<span data-ttu-id="c82c3-221">Table</span><span class="sxs-lookup"><span data-stu-id="c82c3-221">Table</span></span>|<span data-ttu-id="c82c3-222">1</span><span class="sxs-lookup"><span data-stu-id="c82c3-222">1</span></span>|  
    |<span data-ttu-id="c82c3-223">Sofa</span><span class="sxs-lookup"><span data-stu-id="c82c3-223">Sofa</span></span>|<span data-ttu-id="c82c3-224">2</span><span class="sxs-lookup"><span data-stu-id="c82c3-224">2</span></span>|  
    |<span data-ttu-id="c82c3-225">EndTables</span><span class="sxs-lookup"><span data-stu-id="c82c3-225">EndTables</span></span>|<span data-ttu-id="c82c3-226">2</span><span class="sxs-lookup"><span data-stu-id="c82c3-226">2</span></span>|  
  
-   `Customers {}/Customer/Orders/Order{ @ID(Integer)}`  
  
    |<span data-ttu-id="c82c3-227">Order.ID</span><span class="sxs-lookup"><span data-stu-id="c82c3-227">Order.ID</span></span>|<span data-ttu-id="c82c3-228">Nome</span><span class="sxs-lookup"><span data-stu-id="c82c3-228">FirstName</span></span>|<span data-ttu-id="c82c3-229">LastName</span><span class="sxs-lookup"><span data-stu-id="c82c3-229">LastName</span></span>|<span data-ttu-id="c82c3-230">ID</span><span class="sxs-lookup"><span data-stu-id="c82c3-230">ID</span></span>|  
    |--------------|---------------|--------------|--------|  
    |<span data-ttu-id="c82c3-231">1</span><span class="sxs-lookup"><span data-stu-id="c82c3-231">1</span></span>|<span data-ttu-id="c82c3-232">Bobby</span><span class="sxs-lookup"><span data-stu-id="c82c3-232">Bobby</span></span>|<span data-ttu-id="c82c3-233">Moore</span><span class="sxs-lookup"><span data-stu-id="c82c3-233">Moore</span></span>|<span data-ttu-id="c82c3-234">11</span><span class="sxs-lookup"><span data-stu-id="c82c3-234">11</span></span>|  
    |<span data-ttu-id="c82c3-235">2</span><span class="sxs-lookup"><span data-stu-id="c82c3-235">2</span></span>|<span data-ttu-id="c82c3-236">Bobby</span><span class="sxs-lookup"><span data-stu-id="c82c3-236">Bobby</span></span>|<span data-ttu-id="c82c3-237">Moore</span><span class="sxs-lookup"><span data-stu-id="c82c3-237">Moore</span></span>|<span data-ttu-id="c82c3-238">11</span><span class="sxs-lookup"><span data-stu-id="c82c3-238">11</span></span>|  
    |<span data-ttu-id="c82c3-239">8</span><span class="sxs-lookup"><span data-stu-id="c82c3-239">8</span></span>|<span data-ttu-id="c82c3-240">Crystal</span><span class="sxs-lookup"><span data-stu-id="c82c3-240">Crystal</span></span>|<span data-ttu-id="c82c3-241">Hu</span><span class="sxs-lookup"><span data-stu-id="c82c3-241">Hu</span></span>|<span data-ttu-id="c82c3-242">20</span><span class="sxs-lookup"><span data-stu-id="c82c3-242">20</span></span>|  
    |<span data-ttu-id="c82c3-243">15</span><span class="sxs-lookup"><span data-stu-id="c82c3-243">15</span></span>|<span data-ttu-id="c82c3-244">Wyatt</span><span class="sxs-lookup"><span data-stu-id="c82c3-244">Wyatt</span></span>|<span data-ttu-id="c82c3-245">Diaz</span><span class="sxs-lookup"><span data-stu-id="c82c3-245">Diaz</span></span>|<span data-ttu-id="c82c3-246">33</span><span class="sxs-lookup"><span data-stu-id="c82c3-246">33</span></span>|  
  
#### <a name="xml-document-customersxml"></a><span data-ttu-id="c82c3-247">Documento XML: Customers.xml</span><span class="sxs-lookup"><span data-stu-id="c82c3-247">XML document: Customers.xml</span></span>  
 <span data-ttu-id="c82c3-248">Para tentar os exemplos de caminhos de elementos na seção anterior, você pode copiar esse XML e salvá-lo em uma URL acessível pelo Designer de Relatórios e, em seguida, usar o documento XML como uma fonte de dados: por exemplo, `http://localhost/Customers.xml`.</span><span class="sxs-lookup"><span data-stu-id="c82c3-248">To try out the element path examples in the previous section, you can copy this XML and save it to a URL that is accessible by Report Designer, and then use the XML document as an XML data source: for example, `http://localhost/Customers.xml`.</span></span>  
  
```  
<?xml version="1.0"?>  
<Customers xmlns="http://www.adventure-works.com">  
   <Customer ID="11">  
      <FirstName>Bobby</FirstName>  
      <LastName>Moore</LastName>  
      <Orders>  
         <Order ID="1" Qty="6">Chair</Order>  
         <Order ID="2" Qty="1">Table</Order>  
      </Orders>  
      <Returns>  
         <Return ID="1" Qty="2">Chair</Return>  
      </Returns>  
   </Customer>  
   <Customer ID="20">  
      <FirstName>Crystal</FirstName>  
      <LastName>Hu</LastName>  
      <Orders>  
         <Order ID="8" Qty="2">Sofa</Order>  
      </Orders>  
      <Returns/>  
   </Customer>  
   <Customer ID="33">  
      <FirstName>Wyatt</FirstName>  
      <LastName>Diaz</LastName>  
      <Orders>  
         <Order ID="15" Qty="2">EndTables</Order>  
      </Orders>  
      <Returns/>  
   </Customer>  
</Customers>  
```  
  
 <span data-ttu-id="c82c3-249">Como alternativa, é possível criar uma fonte de dados XML que não possui nenhuma cadeia de conexão e inserir Customers.XML na consulta, usando o seguinte procedimento:</span><span class="sxs-lookup"><span data-stu-id="c82c3-249">Alternatively, you can create an XML data source that has no connection string and embed Customers.XML in the query, using the following procedure:</span></span>  
  
###### <a name="to-embed-customersxml-in-a-query"></a><span data-ttu-id="c82c3-250">Para inserir Customers.XML em um consulta</span><span class="sxs-lookup"><span data-stu-id="c82c3-250">To embed Customers.XML in a query</span></span>  
  
1.  <span data-ttu-id="c82c3-251">Crie uma fonte de dados XML com uma cadeia de conexão em branco.</span><span class="sxs-lookup"><span data-stu-id="c82c3-251">Create an XML data source with a blank connection string.</span></span>  
  
2.  <span data-ttu-id="c82c3-252">Crie um novo conjunto de dados para a fonte de dados XML.</span><span class="sxs-lookup"><span data-stu-id="c82c3-252">Create a new dataset for the XML data source.</span></span>  
  
3.  <span data-ttu-id="c82c3-253">Na caixa de diálogo **Propriedades do Conjunto de Dados** , clique em **Designer de Consulta**.</span><span class="sxs-lookup"><span data-stu-id="c82c3-253">In the **Dataset Properties** dialog box, click **Query Designer**.</span></span> <span data-ttu-id="c82c3-254">A caixa de diálogo do Designer de Consulta baseada em texto é aberta.</span><span class="sxs-lookup"><span data-stu-id="c82c3-254">The text-based query designer dialog box opens.</span></span>  
  
4.  <span data-ttu-id="c82c3-255">No painel de consulta, digite as duas linhas a seguir:</span><span class="sxs-lookup"><span data-stu-id="c82c3-255">In the query pane, enter the following two lines:</span></span>  
  
     `<Query>`  
  
     `<XmlData>`  
  
5.  <span data-ttu-id="c82c3-256">Copie Customers.XML e cole o texto no painel de consulta depois de `<XmlData>`.</span><span class="sxs-lookup"><span data-stu-id="c82c3-256">Copy Customers.XML and paste the text in the query pane after `<XmlData>`.</span></span>  
  
6.  <span data-ttu-id="c82c3-257">No painel de consulta, exclua a primeira linha que você copiou de Customers.XML: `<?xml version="1.0"?>`</span><span class="sxs-lookup"><span data-stu-id="c82c3-257">In the query pane, delete the first line that you copied from Customers.XML: `<?xml version="1.0"?>`</span></span>  
  
7.  <span data-ttu-id="c82c3-258">No final da consulta, adicione as duas linhas seguintes:</span><span class="sxs-lookup"><span data-stu-id="c82c3-258">At the end of the query, add the following two lines:</span></span>  
  
     `<XmlData>`  
  
     `<Query>`  
  
8.  <span data-ttu-id="c82c3-259">Clique em **Executar consulta** (!).</span><span class="sxs-lookup"><span data-stu-id="c82c3-259">Click **Run Query** (!).</span></span>  
  
     <span data-ttu-id="c82c3-260">O conjunto de resultados exibe 4 linhas de dados com as seguintes colunas: `xmlns`, `Customer.ID`, `FirstName`, `LastName`, `ID`, `Qty`, `Order`.</span><span class="sxs-lookup"><span data-stu-id="c82c3-260">The result set displays 4 lines of data with the following columns: `xmlns`, `Customer.ID`, `FirstName`, `LastName`, `ID`, `Qty`, `Order`.</span></span>  
  
9. [!INCLUDE[clickOK](../../includes/clickok-md.md)]  
  
## <a name="see-also"></a><span data-ttu-id="c82c3-261">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c82c3-261">See Also</span></span>  
 <span data-ttu-id="c82c3-262">[Tipo de conexão XML &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c82c3-262">[XML Connection Type &#40;SSRS&#41;](xml-connection-type-ssrs.md) </span></span>  
 <span data-ttu-id="c82c3-263">[Reporting Services tutoriais &#40;SSRS&#41;](../reporting-services-tutorials-ssrs.md) </span><span class="sxs-lookup"><span data-stu-id="c82c3-263">[Reporting Services Tutorials &#40;SSRS&#41;](../reporting-services-tutorials-ssrs.md) </span></span>  
 [<span data-ttu-id="c82c3-264">Adicionar, editar e atualizar campos no painel de dados do relatório &#40;Construtor de Relatórios e SSRS&#41;</span><span class="sxs-lookup"><span data-stu-id="c82c3-264">Add, Edit, Refresh Fields in the Report Data Pane &#40;Report Builder and SSRS&#41;</span></span>](add-edit-refresh-fields-in-the-report-data-pane-report-builder-and-ssrs.md)  
  
  
