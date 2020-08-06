---
title: 'Exemplos: Usando o modo PATH | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- PATH FOR XML mode, examples
ms.assetid: 3564e13b-9b97-49ef-8cf9-6a78677b09a3
author: rothja
ms.author: jroth
ms.openlocfilehash: 0876d93ffe246b6129a3838f8dbae47f3be7ffaf
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686197"
---
# <a name="examples-using-path-mode"></a><span data-ttu-id="f37f3-102">Exemplos: uso do modo PATH</span><span class="sxs-lookup"><span data-stu-id="f37f3-102">Examples: Using PATH Mode</span></span>
  <span data-ttu-id="f37f3-103">Os exemplos a seguir ilustram o uso do modo PATH para gerar XML a partir de uma consulta SELECT.</span><span class="sxs-lookup"><span data-stu-id="f37f3-103">The following examples illustrate the use of PATH mode in generating XML from a SELECT query.</span></span> <span data-ttu-id="f37f3-104">Muitas dessas consultas são especificadas em relação a documentos XML de instruções da fabricação de bicicletas que são armazenados na coluna Instructions da tabela ProductModel.</span><span class="sxs-lookup"><span data-stu-id="f37f3-104">Many of these queries are specified against the bicycle manufacturing instructions XML documents that are stored in the Instructions column of the ProductModel table.</span></span>  
  
## <a name="specifying-a-simple-path-mode-query"></a><span data-ttu-id="f37f3-105">Especificando uma consulta em modo PATH</span><span class="sxs-lookup"><span data-stu-id="f37f3-105">Specifying a simple PATH mode query</span></span>  
 <span data-ttu-id="f37f3-106">Esta consulta especifica um FOR XML em modo PATH.</span><span class="sxs-lookup"><span data-stu-id="f37f3-106">This query specifies a FOR XML PATH mode.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT   
       ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH;  
GO  
```  
  
 <span data-ttu-id="f37f3-107">O resultado a seguir é XML centrado em elemento, onde cada valor de coluna no conjunto de linhas resultante é encapsulado em um elemento.</span><span class="sxs-lookup"><span data-stu-id="f37f3-107">The following result is element-centric XML where each column value in the resulting rowset is wrapped in an element.</span></span> <span data-ttu-id="f37f3-108">Como a cláusula `SELECT` não especifica nenhum alias para os nomes das colunas, os nomes dos elementos filho gerados são os mesmos que os nomes das colunas correspondentes na cláusula `SELECT`.</span><span class="sxs-lookup"><span data-stu-id="f37f3-108">Because the `SELECT` clause does not specify any aliases for the column names, the child element names generated are the same as the corresponding column names in the `SELECT` clause.</span></span> <span data-ttu-id="f37f3-109">Para cada linha no conjunto de linhas é adicionada uma marca <`row`>.</span><span class="sxs-lookup"><span data-stu-id="f37f3-109">For each row in the rowset a <`row`> tag is added.</span></span>  
  
 `<row>`  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</row>`  
  
 `<row>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
 `</row>`  
  
 <span data-ttu-id="f37f3-110">O resultado a seguir é o mesmo que o da consulta em modo `RAW` com a opção `ELEMENTS` especificada.</span><span class="sxs-lookup"><span data-stu-id="f37f3-110">The following result is the same as the `RAW` mode query with the `ELEMENTS` option specified.</span></span> <span data-ttu-id="f37f3-111">Ele retorna XML centrado em elemento com um elemento <`row`> padrão para cada linha no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="f37f3-111">It returns element-centric XML with a default <`row`> element for each row in the result set.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML RAW, ELEMENTS;  
```  
  
 <span data-ttu-id="f37f3-112">Opcionalmente, é possível especificar o nome do elemento de linha para substituir a <`row`>padrão.</span><span class="sxs-lookup"><span data-stu-id="f37f3-112">You can optionally specify the row element name to overwrite the default <`row`>.</span></span> <span data-ttu-id="f37f3-113">Por exemplo, a consulta a seguir retorna o elemento <`ProductModel`> para cada linha no conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="f37f3-113">For example, the following query returns the <`ProductModel`> element for each row in the rowset.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML PATH ('ProductModel');  
GO  
```  
  
 <span data-ttu-id="f37f3-114">O XML resultante terá um nome de elemento de linha especificado.</span><span class="sxs-lookup"><span data-stu-id="f37f3-114">The resulting XML will have a specified row element name.</span></span>  
  
 `<ProductModel>`  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</ProductModel>`  
  
 `<ProductModel>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
 `</ProductModel>`  
  
 <span data-ttu-id="f37f3-115">Se você especificar uma cadeia de caracteres de comprimento zero, o elemento de encapsulamento não será produzido.</span><span class="sxs-lookup"><span data-stu-id="f37f3-115">If you specify a zero-length string, the wrapping element is not produced.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID,  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH ('');  
GO  
```  
  
 <span data-ttu-id="f37f3-116">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="f37f3-116">This is the result:</span></span>  
  
 `<ProductModelID>122</ProductModelID>`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `<ProductModelID>119</ProductModelID>`  
  
 `<Name>Bike Wash</Name>`  
  
## <a name="specifying-xpath-like-column-names"></a><span data-ttu-id="f37f3-117">Especificando nomes de colunas como XPath</span><span class="sxs-lookup"><span data-stu-id="f37f3-117">Specifying XPath-like column names</span></span>  
 <span data-ttu-id="f37f3-118">Na consulta a seguir, o nome da coluna `ProductModelID` especificado começa com '\@' e não contém uma barra ('/').</span><span class="sxs-lookup"><span data-stu-id="f37f3-118">In the following query the `ProductModelID` column name specified starts with '\@' and does not contain a slash mark ('/').</span></span> <span data-ttu-id="f37f3-119">Portanto, um atributo do elemento <`row`> que tem o valor de coluna correspondente é criado no XML resultante.</span><span class="sxs-lookup"><span data-stu-id="f37f3-119">Therefore, an attribute of the <`row`> element that has the corresponding column value is created in the resulting XML.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID AS "@id",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 OR ProductModelID=119  
FOR XML PATH ('ProductModelData');  
GO  
```  
  
 <span data-ttu-id="f37f3-120">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="f37f3-120">This is the result:</span></span>  
  
 `< ProductModelData id="122">`  
  
 `<Name>All-Purpose Bike Stand</Name>`  
  
 `</ ProductModelData >`  
  
 `< ProductModelData id="119">`  
  
 `<Name>Bike Wash</Name>`  
  
 `</ ProductModelData >`  
  
 <span data-ttu-id="f37f3-121">Você pode adicionar um único elemento de nível superior por meio da especificação da opção `root` em `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="f37f3-121">You can add a single top-level element by specifying the `root` option in `FOR XML`.</span></span>  
  
```  
SELECT ProductModelID AS "@id",  
       Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML PATH ('ProductModelData'), root ('Root');  
GO  
```  
  
 <span data-ttu-id="f37f3-122">Para gerar uma hierarquia, você pode incluir sintaxe como PATH.</span><span class="sxs-lookup"><span data-stu-id="f37f3-122">To generate a hierarchy, you can include PATH-like syntax.</span></span> <span data-ttu-id="f37f3-123">Por exemplo, altere o nome da coluna `Name` para "SomeChild/ModelName" e você obterá XML com hierarquia, conforme mostrado neste resultado:</span><span class="sxs-lookup"><span data-stu-id="f37f3-123">For example, change the column name for the `Name` column to "SomeChild/ModelName" and you will obtain XML with hierarchy, as shown in this result:</span></span>  
  
 `<Root>`  
  
 `<ProductModelData id="122">`  
  
 `<SomeChild>`  
  
 `<ModelName>All-Purpose Bike Stand</ModelName>`  
  
 `</SomeChild>`  
  
 `</ProductModelData>`  
  
 `<ProductModelData id="119">`  
  
 `<SomeChild>`  
  
 `<ModelName>Bike Wash</ModelName>`  
  
 `</SomeChild>`  
  
 `</ProductModelData>`  
  
 `</Root>`  
  
 <span data-ttu-id="f37f3-124">Além da ID do modelo e do nome do produto, a consulta a seguir recupera os locais de instruções de fabricação do modelo do produto.</span><span class="sxs-lookup"><span data-stu-id="f37f3-124">Besides the product model ID and name, the following query retrieves the manufacturing instruction locations for the product model.</span></span> <span data-ttu-id="f37f3-125">Como a coluna Instructions é de tipo `xml`, o método `query()` de tipo de dados `xml` é especificado para recuperar o local.</span><span class="sxs-lookup"><span data-stu-id="f37f3-125">Because the Instructions column is of `xml` type, the `query()` method of `xml` data type is specified to retrieve the location.</span></span>  
  
```  
SELECT ProductModelID AS "@id",  
       Name,  
       Instructions.query('declare namespace MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions";  
                /MI:root/MI:Location   
              ') AS ManuInstr  
FROM Production.ProductModel  
WHERE ProductModelID = 7  
FOR XML PATH ('ProductModelData'), root ('Root');  
GO  
```  
  
 <span data-ttu-id="f37f3-126">Este é o resultado parcial.</span><span class="sxs-lookup"><span data-stu-id="f37f3-126">This is the partial result.</span></span> <span data-ttu-id="f37f3-127">Como a consulta especifica ManuInstr como o nome da coluna, o XML retornado pelo `query()` método é encapsulado em uma marca de> de <, `ManuInstr` conforme mostrado a seguir:</span><span class="sxs-lookup"><span data-stu-id="f37f3-127">Because the query specifies ManuInstr as the column name, the XML returned by the `query()` method is wrapped in a <`ManuInstr`> tag as shown in the following:</span></span>  
  
 `<Root>`  
  
 `<ProductModelData id="7">`  
  
 `<Name>HL Touring Frame</Name>`  
  
 `<ManuInstr>`  
  
 `<MI:Location xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"`  
  
 `<MI:step>...</MI:step>...`  
  
 `</MI:Location>`  
  
 `...`  
  
 `</ManuInstr>`  
  
 `</ProductModelData>`  
  
 `</Root>`  
  
 <span data-ttu-id="f37f3-128">Na consulta FOR XML anterior, talvez você queira incluir namespaces para os elementos <`Root`> e <`ProductModelData`>.</span><span class="sxs-lookup"><span data-stu-id="f37f3-128">In the previous FOR XML query, you may want to include namespaces for the <`Root`> and <`ProductModelData`> elements.</span></span> <span data-ttu-id="f37f3-129">Isso pode ser feito primeiro definindo o prefixo para a associação do namespace usando WITH XMLNAMESPACES e usando prefixos na consulta FOR XML.</span><span class="sxs-lookup"><span data-stu-id="f37f3-129">You can do this by first defining the prefix to namespace binding by using WITH XMLNAMESPACES and using prefixes in the FOR XML query.</span></span> <span data-ttu-id="f37f3-130">Para obter mais informações, consulte [Adicionar Namespaces a consultas com WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span><span class="sxs-lookup"><span data-stu-id="f37f3-130">For more information, see [Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
WITH XMLNAMESPACES (  
   'uri1' AS ns1,    
   'uri2' AS ns2,  
   'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions' as MI)  
SELECT ProductModelID AS "ns1:ProductModelID",  
       Name           AS "ns1:Name",  
       Instructions.query('  
                /MI:root/MI:Location   
              ')   
FROM Production.ProductModel  
WHERE ProductModelID=7  
FOR XML PATH ('ns2:ProductInfo'), root('ns1:root');  
GO  
```  
  
 <span data-ttu-id="f37f3-131">Observe que o prefixo `MI` também está definido em `WITH XMLNAMESPACES`.</span><span class="sxs-lookup"><span data-stu-id="f37f3-131">Note that the `MI` prefix is also defined in the `WITH XMLNAMESPACES`.</span></span> <span data-ttu-id="f37f3-132">Como resultado, o método `query()` do tipo `xml` especificado não define o prefixo no prólogo da consulta.</span><span class="sxs-lookup"><span data-stu-id="f37f3-132">As a result, the `query()` method of the `xml` type specified does not define the prefix in the query prolog.</span></span> <span data-ttu-id="f37f3-133">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="f37f3-133">This is the result:</span></span>  
  
 `<ns1:root xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions" xmlns="uri2" xmlns:ns2="uri2" xmlns:ns1="uri1">`  
  
 `<ns2:ProductInfo>`  
  
 `<ns1:ProductModelID>7</ns1:ProductModelID>`  
  
 `<ns1:Name>HL Touring Frame</ns1:Name>`  
  
 `<MI:Location xmlns:MI="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstructions"`  
  
 `LaborHours="2.5" LotSize="100" MachineHours="3" SetupHours="0.5" LocationID="10" xmlns="">`  
  
 `<MI:step>`  
  
 `Insert <MI:material>aluminum sheet MS-2341</MI:material> into the <MI:tool>T-85A framing tool</MI:tool>.`  
  
 `</MI:step>`  
  
 `...`  
  
 `</MI:Location>`  
  
 `...`  
  
 `</ns2:ProductInfo>`  
  
 `</ns1:root>`  
  
## <a name="generating-a-value-list-using-path-mode"></a><span data-ttu-id="f37f3-134">Gerando uma lista de valores com o modo PATH</span><span class="sxs-lookup"><span data-stu-id="f37f3-134">Generating a value list using PATH mode</span></span>  
 <span data-ttu-id="f37f3-135">Para cada modelo de produto, essa consulta constrói uma lista de valores de IDs de produtos.</span><span class="sxs-lookup"><span data-stu-id="f37f3-135">For each product model, this query constructs a value list of product IDs.</span></span> <span data-ttu-id="f37f3-136">Para cada ID de produto, a consulta também constrói elementos aninhados <`ProductName`>, conforme mostrado neste fragmento de XML:</span><span class="sxs-lookup"><span data-stu-id="f37f3-136">For each product ID, the query also constructs <`ProductName`> nested elements, as shown in this XML fragment:</span></span>  
  
 `<ProductModelData ProductModelID="7" ProductModelName="..."`  
  
 `ProductIDs="product id list in the product model" >`  
  
 `<ProductName>...</ProductName>`  
  
 `<ProductName>...</ProductName>`  
  
 `...`  
  
 `</ProductModelData>`  
  
 <span data-ttu-id="f37f3-137">Esta é a consulta que produz o XML desejado:</span><span class="sxs-lookup"><span data-stu-id="f37f3-137">This is the query that produces the XML you want:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID     AS "@ProductModelID",  
       Name               S "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')) S "@ProductIDs",  
       (SELECT Name AS "ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
        FOR XML PATH ('')) as "ProductNames"  
FROM   Production.ProductModel  
WHERE  ProductModelID= 7 or ProductModelID=9  
FOR XML PATH('ProductModelData');  
```  
  
 <span data-ttu-id="f37f3-138">Observe o seguinte na consulta anterior:</span><span class="sxs-lookup"><span data-stu-id="f37f3-138">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="f37f3-139">O primeiro `SELECT` aninhado retorna uma lista de ProductIDs usando `data()` como o nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="f37f3-139">The first nested `SELECT` returns a list of ProductIDs by using `data()` as the column name.</span></span> <span data-ttu-id="f37f3-140">Como a consulta especifica uma cadeia de caracteres vazia como o nome do elemento de linha em `FOR XML PATH`, nenhum elemento é gerado.</span><span class="sxs-lookup"><span data-stu-id="f37f3-140">Because the query specifies an empty string as the row element name in `FOR XML PATH`, no element is generated.</span></span> <span data-ttu-id="f37f3-141">Em vez disso, a lista de valores é atribuída ao atributo `ProductID` .</span><span class="sxs-lookup"><span data-stu-id="f37f3-141">Instead, the value list is assigned to the `ProductID` attribute.</span></span>  
  
-   <span data-ttu-id="f37f3-142">O segundo `SELECT` aninhado recupera nomes de produtos no modelo do produto.</span><span class="sxs-lookup"><span data-stu-id="f37f3-142">The second nested `SELECT` retrieves product names for products in the product model.</span></span> <span data-ttu-id="f37f3-143">Ele gera elementos de <`ProductName`> que são retornados encapsulados no elemento <`ProductNames`>, pois a consulta especifica `ProductNames` como o nome da coluna.</span><span class="sxs-lookup"><span data-stu-id="f37f3-143">It generates <`ProductName`> elements that are returned wrapped in the <`ProductNames`> element, because the query specifies `ProductNames` as the column name.</span></span>  
  
 <span data-ttu-id="f37f3-144">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="f37f3-144">This is the partial result:</span></span>  
  
 `<ProductModelData PId="7"`  
  
 `ProductModelName="HL Touring Frame"`  
  
 `ProductIDs="885 887 ...">`  
  
 `<ProductNames>`  
  
 `<ProductName>HL Touring Frame - Yellow, 60</ProductName>`  
  
 `<ProductName>HL Touring Frame - Yellow, 46</ProductName></ProductNames>`  
  
 `...`  
  
 `</ProductModelData>`  
  
 `<ProductModelData PId="9"`  
  
 `ProductModelName="LL Road Frame"`  
  
 `ProductIDs="722 723 724 ...">`  
  
 `<ProductNames>`  
  
 `<ProductName>LL Road Frame - Black, 58</ProductName>`  
  
 `<ProductName>LL Road Frame - Black, 60</ProductName>`  
  
 `<ProductName>LL Road Frame - Black, 62</ProductName>`  
  
 `...`  
  
 `</ProductNames>`  
  
 `</ProductModelData>`  
  
 <span data-ttu-id="f37f3-145">A subconsulta que constrói os nomes dos produtos retorna o resultado como uma cadeia de caracteres cuja entidade é criada e, em seguida, é adicionada ao XML.</span><span class="sxs-lookup"><span data-stu-id="f37f3-145">The subquery constructing the product names returns the result as a string that is entitized and then added to the XML.</span></span> <span data-ttu-id="f37f3-146">Se você adicionar a diretiva de tipo `FOR XML PATH (''), type`, a subconsulta retornará o resultado como tipo `xml` e não ocorrerá nenhum definição de entidade.</span><span class="sxs-lookup"><span data-stu-id="f37f3-146">If you add the type directive, `FOR XML PATH (''), type`, the subquery returns the result as `xml` type and no entitization occurs.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID AS "@ProductModelID",  
      Name AS "@ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')  
       ) AS "@ProductIDs",  
       (  
       SELECT Name AS "ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH (''), type  
       ) AS "ProductNames"  
  
FROM Production.ProductModel  
WHERE ProductModelID= 7 OR ProductModelID=9  
FOR XML PATH('ProductModelData');  
```  
  
## <a name="adding-namespaces-in-the-resulting-xml"></a><span data-ttu-id="f37f3-147">Adicionando namespaces no XML resultante</span><span class="sxs-lookup"><span data-stu-id="f37f3-147">Adding namespaces in the resulting XML</span></span>  
 <span data-ttu-id="f37f3-148">Conforme descrito em [Adicionando namespaces usando WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md), é possível usar WITH XMLNAMESPACES para incluir namespaces em consultas em modo PATH.</span><span class="sxs-lookup"><span data-stu-id="f37f3-148">As described in [Adding Namespaces Using WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md), you can use WITH XMLNAMESPACES to include namespaces in the PATH mode queries.</span></span> <span data-ttu-id="f37f3-149">Por exemplo, nomes especificados na cláusula SELECT incluem prefixos de namespace.</span><span class="sxs-lookup"><span data-stu-id="f37f3-149">For example, names specified in the SELECT clause include namespace prefixes.</span></span> <span data-ttu-id="f37f3-150">A consulta do modo `PATH` a seguir constrói XML com namespaces.</span><span class="sxs-lookup"><span data-stu-id="f37f3-150">The following `PATH` mode query constructs XML with namespaces.</span></span>  
  
```  
SELECT 'en'    as "English/@xml:lang",  
       'food'  as "English",  
       'ger'   as "German/@xml:lang",  
       'Essen' as "German"  
FOR XML PATH ('Translation')  
GO  
```  
  
 <span data-ttu-id="f37f3-151">O atributo `@xml:lang` adicionado ao elemento <`English`> está definido no namespace xml predefinido.</span><span class="sxs-lookup"><span data-stu-id="f37f3-151">The `@xml:lang` attribute added to the <`English`> element is defined in the predefined xml namespace.</span></span>  
  
 <span data-ttu-id="f37f3-152">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="f37f3-152">This is the result:</span></span>  
  
 `<Translation>`  
  
 `<English xml:lang="en">food</English>`  
  
 `<German xml:lang="ger">Essen</German>`  
  
 `</Translation>`  
  
 <span data-ttu-id="f37f3-153">A consulta a seguir é semelhante ao exemplo C, exceto pelo fato de que ela usa `WITH XMLNAMESPACES` para incluir namespaces no resultado XML.</span><span class="sxs-lookup"><span data-stu-id="f37f3-153">The following query is similar to example C, except that it uses `WITH XMLNAMESPACES` to include namespaces in the XML result.</span></span> <span data-ttu-id="f37f3-154">Para obter mais informações, consulte [Adicionar Namespaces a consultas com WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span><span class="sxs-lookup"><span data-stu-id="f37f3-154">For more information, see [Add Namespaces to Queries with WITH XMLNAMESPACES](add-namespaces-to-queries-with-with-xmlnamespaces.md).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
WITH XMLNAMESPACES ('uri1' AS ns1,  DEFAULT 'uri2')  
SELECT ProductModelID AS "@ns1:ProductModelID",  
      Name AS "@ns1:ProductModelName",  
      (SELECT ProductID AS "data()"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH ('')  
       ) AS "@ns1:ProductIDs",  
       (  
       SELECT ProductID AS "@ns1:ProductID",   
              Name AS "@ns1:ProductName"  
       FROM   Production.Product  
       WHERE  Production.Product.ProductModelID =   
              Production.ProductModel.ProductModelID  
       FOR XML PATH , type   
       ) AS "ns1:ProductNames"  
FROM Production.ProductModel  
WHERE ProductModelID= 7 OR ProductModelID=9  
FOR XML PATH('ProductModelData'), root('root');  
```  
  
 <span data-ttu-id="f37f3-155">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="f37f3-155">This is the result:</span></span>  
  
 `<root xmlns="uri2" xmlns:ns1="uri1">`  
  
 `<ProductModelData ns1:ProductModelID="7" ns1:ProductModelName="HL Touring Frame" ns1:ProductIDs="885 887 888 889 890 891 892 893">`  
  
 `<ns1:ProductNames>`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="885" ns1:ProductName="HL Touring Frame - Yellow, 60" />`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="887" ns1:ProductName="HL Touring Frame - Yellow, 46" />`  
  
 `...`  
  
 `</ns1:ProductNames>`  
  
 `</ProductModelData>`  
  
 `<ProductModelData ns1:ProductModelID="9" ns1:ProductModelName="LL Road Frame" ns1:ProductIDs="722 723 724 725 726 727 728 729 730 736 737 738">`  
  
 `<ns1:ProductNames>`  
  
 `<row xmlns="uri2" xmlns:ns1="uri1" ns1:ProductID="722" ns1:ProductName="LL Road Frame - Black, 58" />`  
  
 `...`  
  
 `</ns1:ProductNames>`  
  
 `</ProductModelData>`  
  
 `</root>`  
  
## <a name="see-also"></a><span data-ttu-id="f37f3-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f37f3-156">See Also</span></span>  
 [<span data-ttu-id="f37f3-157">Usar o modo PATH com FOR XML</span><span class="sxs-lookup"><span data-stu-id="f37f3-157">Use PATH Mode with FOR XML</span></span>](use-path-mode-with-for-xml.md)  
  
  
