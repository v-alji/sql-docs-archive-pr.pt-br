---
title: Adicionar namespaces a consultas com WITH XMLNAMESPACES | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ELEMENTS XSINIL directive
- adding namespaces
- XSINIL directive
- default namespaces
- queries [XML in SQL Server], WITH XMLNAMESPACES clause
- predefined namespaces [XML in SQL Server]
- FOR XML clause, WITH XMLNAMESPACES clause
- namespaces [XML in SQL Server]
- xml data type [SQL Server], WITH XMLNAMESPACES clause
- WITH XMLNAMESPACES clause
ms.assetid: 2189cb5e-4460-46c5-a254-20c833ebbfec
author: rothja
ms.author: jroth
ms.openlocfilehash: ed5d719a845996215fffc18af64401779f848cd0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569253"
---
# <a name="add-namespaces-to-queries-with-with-xmlnamespaces"></a><span data-ttu-id="67dfc-102">Adicionar namespaces a consultas com WITH XMLNAMESPACES</span><span class="sxs-lookup"><span data-stu-id="67dfc-102">Add Namespaces to Queries with WITH XMLNAMESPACES</span></span>
  <span data-ttu-id="67dfc-103">[WITH XMLNAMESPACES (Transact-SQL)](/sql/t-sql/xml/with-xmlnamespaces) fornece suporte a URI de namespace da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="67dfc-103">[WITH XMLNAMESPACES (Transact-SQL)](/sql/t-sql/xml/with-xmlnamespaces) provides namespace URI support in the following way:</span></span>  
  
-   <span data-ttu-id="67dfc-104">Ele torna o mapeamento do prefixo do namespace para URI disponível ao [Construir consultas XML usando FOR XML](for-xml-sql-server.md) .</span><span class="sxs-lookup"><span data-stu-id="67dfc-104">It makes the namespace prefix to URI mapping available when [Constructing XML Using FOR XML](for-xml-sql-server.md) queries.</span></span>  
  
-   <span data-ttu-id="67dfc-105">Ele torna o mapeamento do namespace para URI disponíveis para o contexto de namespace estático do Faz o namespace a URI que mapeia disponível para o contexto de namespace estático dos [Métodos de tipos de dados xml](/sql/t-sql/xml/xml-data-type-methods).</span><span class="sxs-lookup"><span data-stu-id="67dfc-105">It makes the namespace to URI mapping available to the static namespace context of the [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods).</span></span>  
  
## <a name="using-with-xmlnamespaces-in-the-for-xml-queries"></a><span data-ttu-id="67dfc-106">Usando WITH XMLNAMESPACES em consultas FOR XML</span><span class="sxs-lookup"><span data-stu-id="67dfc-106">Using WITH XMLNAMESPACES in the FOR XML Queries</span></span>  
 <span data-ttu-id="67dfc-107">WITH XMLNAMESPACES permite incluir namespaces XML em consultas FOR XML.</span><span class="sxs-lookup"><span data-stu-id="67dfc-107">WITH XMLNAMESPACES lets you include XML namespaces in FOR XML queries.</span></span> <span data-ttu-id="67dfc-108">Por exemplo, considere a seguinte consulta FOR XML:</span><span class="sxs-lookup"><span data-stu-id="67dfc-108">For example, consider the following FOR XML query:</span></span>  
  
```  
SELECT ProductID, Name, Color  
FROM   Production.Product  
WHERE  ProductID=316 or ProductID=317  
FOR XML RAW  
```  
  
 <span data-ttu-id="67dfc-109">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="67dfc-109">This is the result:</span></span>  
  
```  
<row ProductID="316" Name="Blade" />  
<row ProductID="317" Name="LL Crankarm" Color="Black" />  
  
```  
  
 <span data-ttu-id="67dfc-110">Para adicionar namespaces ao XML construído pela consulta FOR XML, primeiro especifique os mapeamentos de prefixo de namespace para URI usando a cláusula WITH NAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="67dfc-110">To add namespaces to the XML constructed by the FOR XML query, first specify the namespace prefix to URI mappings by using the WITH NAMESPACES clause.</span></span> <span data-ttu-id="67dfc-111">Em seguida, use os prefixos de namespace para especificar os nomes na consulta, conforme mostrado na seguinte consulta modificada.</span><span class="sxs-lookup"><span data-stu-id="67dfc-111">Then, use the namespace prefixes in specifying the names in the query as shown in the following modified query.</span></span> <span data-ttu-id="67dfc-112">Observe que a cláusula WITH XMLNAMESPACES especifica o mapeamento de prefixo de namespace (`ns1`) para o URI (`uri`).</span><span class="sxs-lookup"><span data-stu-id="67dfc-112">Note that the WITH XMLNAMESPACES clause specifies the namespace prefix (`ns1`) to URI (`uri`) mapping.</span></span> <span data-ttu-id="67dfc-113">Em seguida, o `ns1` é usado para especificar os nomes do atributo e do elemento a serem construídos pela consulta FOR XML.</span><span class="sxs-lookup"><span data-stu-id="67dfc-113">The `ns1` prefix is then used in specifying the element and attribute names to be constructed by the FOR XML query.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri' as ns1)  
SELECT ProductID as 'ns1:ProductID',  
       Name      as 'ns1:Name',   
       Color     as 'ns1:Color'  
FROM Production.Product  
WHERE ProductID=316 or ProductID=317  
FOR XML RAW ('ns1:Prod'), ELEMENTS  
  
```  
  
 <span data-ttu-id="67dfc-114">O resultado do XML inclui os prefixos de namespace:</span><span class="sxs-lookup"><span data-stu-id="67dfc-114">The XML result includes the namespace prefixes:</span></span>  
  
```  
<ns1:Prod xmlns:ns1="uri">  
  <ns1:ProductID>316</ns1:ProductID>  
  <ns1:Name>Blade</ns1:Name>  
</ns1:Prod>  
<ns1:Prod xmlns:ns1="uri">  
  <ns1:ProductID>317</ns1:ProductID>  
  <ns1:Name>LL Crankarm</ns1:Name>  
  <ns1:Color>Black</ns1:Color>  
</ns1:Prod>  
  
```  
  
 <span data-ttu-id="67dfc-115">O seguinte se aplica à cláusula WITH XMLNAMESPACES:</span><span class="sxs-lookup"><span data-stu-id="67dfc-115">The following applies to the WITH XMLNAMESPACES clause:</span></span>  
  
-   <span data-ttu-id="67dfc-116">Ela tem suporte apenas nos modos RAW, AUTO e PATH de consultas FOR XML.</span><span class="sxs-lookup"><span data-stu-id="67dfc-116">It is supported only on the RAW, AUTO, and PATH modes of the FOR XML queries.</span></span> <span data-ttu-id="67dfc-117">Não há suporte para o modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="67dfc-117">The EXPLICIT mode is not supported.</span></span>  
  
-   <span data-ttu-id="67dfc-118">Ela afeta apenas os prefixos de namespace de consultas FOR XML e os métodos de tipos de dados **xml** , mas não o analisador XML.</span><span class="sxs-lookup"><span data-stu-id="67dfc-118">It only affects the namespace prefixes of FOR XML queries and the **xml** data type methods, but not the XML parser.</span></span> <span data-ttu-id="67dfc-119">Por exemplo, a consulta a seguir retorna um erro porque o documento XML não tem nenhuma declaração de namespace para o prefixo myNS:</span><span class="sxs-lookup"><span data-stu-id="67dfc-119">For example, the following query returns an error, because the XML document has no namespace declaration for the myNS prefix.</span></span>  
  
-   <span data-ttu-id="67dfc-120">As diretivas de FOR XML, XMLSCHEMA e XMLDATA não podem ser usadas quando uma cláusula WITH XMLNAMESPACES está sendo usada.</span><span class="sxs-lookup"><span data-stu-id="67dfc-120">The FOR XML directives, XMLSCHEMA and XMLDATA cannot be used when a WITH XMLNAMESPACES clause is being used.</span></span>  
  
    ```  
    CREATE TABLE T (x xml)  
    go  
    WITH XMLNAMESPACES ('http://abc' as myNS )  
    INSERT INTO T VALUES('<myNS:root/>')  
    ```  
  
## <a name="using-the-xsinil-directive"></a><span data-ttu-id="67dfc-121">Usando a diretiva XSINIL</span><span class="sxs-lookup"><span data-stu-id="67dfc-121">Using the XSINIL Directive</span></span>  
 <span data-ttu-id="67dfc-122">Não será possível definir o prefixo na cláusula WITH XMLNAMESPACES se você estiver usando a diretiva ELEMENTS XSINIL.</span><span class="sxs-lookup"><span data-stu-id="67dfc-122">You cannot define the xsi prefix in the WITH XMLNAMESPACES clause if you are using the ELEMENTS XSINIL directive.</span></span> <span data-ttu-id="67dfc-123">Em vez disso, ela é adicionada automaticamente quando você usa ELEMENTS XSINIL.</span><span class="sxs-lookup"><span data-stu-id="67dfc-123">Instead, it is added automatically when you use ELEMENTS XSINIL.</span></span> <span data-ttu-id="67dfc-124">A consulta a seguir usa ELEMENTS XSINIL que gera XML centrado em elemento em que valores nulos são mapeados para elementos que têm o atributo **xsi:nil** definido como True.</span><span class="sxs-lookup"><span data-stu-id="67dfc-124">The following query uses ELEMENTS XSINIL that generates element-centric XML where null values are mapped to elements that have the **xsi:nil** attribute set to True.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri' as ns1)  
SELECT ProductID as 'ns1:ProductID',  
       Name      as 'ns1:Name',   
       Color     as 'ns1:Color'  
FROM Production.Product  
WHERE ProductID=316   
FOR XML RAW, ELEMENTS XSINIL  
```  
  
 <span data-ttu-id="67dfc-125">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="67dfc-125">This is the result:</span></span>  
  
```  
<row xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance" xmlns:ns1="uri">  
  <ns1:ProductID>316</ns1:ProductID>  
  <ns1:Name>Blade</ns1:Name>  
  <ns1:Color xsi:nil="true" />  
</row>  
```  
  
## <a name="specifying-default-namespaces"></a><span data-ttu-id="67dfc-126">Especificando namespaces padrão</span><span class="sxs-lookup"><span data-stu-id="67dfc-126">Specifying Default Namespaces</span></span>  
 <span data-ttu-id="67dfc-127">Em vez de declarar um prefixo de namespace, é possível declarar um namespace padrão usando uma palavra-chave DEFAULT.</span><span class="sxs-lookup"><span data-stu-id="67dfc-127">Instead of declaring a namespace prefix, you can declare a default namespace by using a DEFAULT keyword.</span></span> <span data-ttu-id="67dfc-128">Na consulta FOR XML, ele associará o namespace padrão a nós XML no XML resultante.</span><span class="sxs-lookup"><span data-stu-id="67dfc-128">In the FOR XML query, it will bind the default namespace to XML nodes in the resulting XML.</span></span> <span data-ttu-id="67dfc-129">No exemplo a seguir, WITH XMLNAMESPACES define dois prefixos de namespace que são definidos junto com um namespace padrão.</span><span class="sxs-lookup"><span data-stu-id="67dfc-129">In the following example, the WITH XMLNAMESPACES defines two namespace prefixes that are defined together with a default namespace.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri1' as ns1,   
                    'uri2' as ns2,  
                    DEFAULT 'uri2')  
SELECT ProductID,   
      Name,  
      Color  
FROM Production.Product   
WHERE ProductID=316 or ProductID=317  
FOR XML RAW ('ns1:Product'), ROOT('ns2:root'), ELEMENTS  
```  
  
 <span data-ttu-id="67dfc-130">A consulta FOR XML gera XML centrado em elemento.</span><span class="sxs-lookup"><span data-stu-id="67dfc-130">The FOR XML query generates element-centric XML.</span></span> <span data-ttu-id="67dfc-131">Observe que a consulta usa os dois prefixos de namespace na nomeação de nós.</span><span class="sxs-lookup"><span data-stu-id="67dfc-131">Note that the query uses both the namespace prefixes in naming nodes.</span></span> <span data-ttu-id="67dfc-132">Na cláusula SELECT, ProductID, Name e Color não especificam um nome com qualquer prefixo.</span><span class="sxs-lookup"><span data-stu-id="67dfc-132">In the SELECT clause, the ProductID, Name, and Color do not specify a name with any prefix.</span></span> <span data-ttu-id="67dfc-133">Portanto os elementos correspondentes no XML resultante pertencem ao namespace padrão.</span><span class="sxs-lookup"><span data-stu-id="67dfc-133">Therefore, the corresponding elements in the resulting XML belong to the default namespace.</span></span>  
  
```  
<ns2:root xmlns="uri2" xmlns:ns2="uri2" xmlns:ns1="uri1">  
  <ns1:Product>  
    <ProductID>316</ProductID>  
    <Name>Blade</Name>  
  </ns1:Product>  
  <ns1:Product>  
    <ProductID>317</ProductID>  
    <Name>LL Crankarm</Name>  
    <Color>Black</Color>  
  </ns1:Product>  
</ns2:root>  
```  
  
 <span data-ttu-id="67dfc-134">A consulta a seguir é semelhante à anterior, exceto que o modo FOR XML AUTO é especificado.</span><span class="sxs-lookup"><span data-stu-id="67dfc-134">The following query is similar to the previous one, except that the FOR XML AUTO mode is specified.</span></span>  
  
```  
WITH XMLNAMESPACES ('uri1' as ns1,  'uri2' as ns2,DEFAULT 'uri2')  
SELECT ProductID,   
      Name,  
      Color  
FROM Production.Product as "ns1:Product"  
WHERE ProductID=316 or ProductID=317  
FOR XML AUTO, ROOT('ns2:root'), ELEMENTS  
```  
  
## <a name="using-predefined-namespaces"></a><span data-ttu-id="67dfc-135">Usando namespaces predefinidos</span><span class="sxs-lookup"><span data-stu-id="67dfc-135">Using Predefined Namespaces</span></span>  
 <span data-ttu-id="67dfc-136">Quando namespaces predefinidos são usados, exceto pelo namespace xml e o namespace xsi quando ELEMENTS XSINIL é usado, você deve especificar explicitamente a associação do namespace usando WITH XMLNAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="67dfc-136">When you use predefined namespaces, except the xml namespace and the xsi namespace when ELEMENTS XSINIL is used, you must explicitly specify the namespace binding by using WITH XMLNAMESPACES.</span></span> <span data-ttu-id="67dfc-137">A consulta a seguir define explicitamente o prefixo de namespace para associação de URI para o namespace predefinido (`urn:schemas-microsoft-com:xml-sql`).</span><span class="sxs-lookup"><span data-stu-id="67dfc-137">The following query explicitly defines the namespace prefix to URI binding for the predefined namespace (`urn:schemas-microsoft-com:xml-sql`).</span></span>  
  
```  
WITH XMLNAMESPACES ('urn:schemas-microsoft-com:xml-sql' as sql)  
SELECT 'SELECT * FROM Customers FOR XML AUTO, ROOT("a")' AS "sql:query"  
FOR XML PATH('sql:root')  
```  
  
 <span data-ttu-id="67dfc-138">Este é o resultado.</span><span class="sxs-lookup"><span data-stu-id="67dfc-138">This is the result.</span></span> <span data-ttu-id="67dfc-139">Usuários de SQLXML estão familiarizados com esse modelo de XML.</span><span class="sxs-lookup"><span data-stu-id="67dfc-139">SQLXML users are familiar with this XML template.</span></span> <span data-ttu-id="67dfc-140">Para obter mais informações, consulte [Conceitos de programação do SQLXML 4.0](../sqlxml/sqlxml-4-0-programming-concepts.md).</span><span class="sxs-lookup"><span data-stu-id="67dfc-140">For more information, see [SQLXML 4.0 Programming Concepts](../sqlxml/sqlxml-4-0-programming-concepts.md).</span></span>  
  
```  
<sql:root xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>SELECT * FROM Customers FOR XML AUTO, ROOT("a")</sql:query>  
</sql:root>  
```  
  
 <span data-ttu-id="67dfc-141">Apenas o prefixo de namespace xml pode ser usado sem defini-lo explicitamente em WITH XMLNAMESPACES, conforme mostrado na consulta de modo PATH a seguir.</span><span class="sxs-lookup"><span data-stu-id="67dfc-141">Only the xml namespace prefix can be used without explicitly defining it in WITH XMLNAMESPACES, as shown in the following PATH mode query.</span></span> <span data-ttu-id="67dfc-142">Além disso, se o prefixo for declarado, ele deverá ser associado ao namespace http://www.w3.org/XML/1998/namespace.</span><span class="sxs-lookup"><span data-stu-id="67dfc-142">Also, if the prefix is declared, it has to be bound to the namespace http://www.w3.org/XML/1998/namespace.</span></span> <span data-ttu-id="67dfc-143">Os nomes especificados na cláusula SELECT fazem referência ao prefixo de namespace xml que não é definido explicitamente usando WITH XMLNAMESPACES.</span><span class="sxs-lookup"><span data-stu-id="67dfc-143">The names specified in the SELECT clause refer to the xml namespace prefix that is not explicitly defined by using WITH XMLNAMESPACES.</span></span>  
  
```  
SELECT 'en'    as "English/@xml:lang",  
       'food'  as "English",  
       'ger'   as "German/@xml:lang",  
       'Essen' as "German"  
FOR XML PATH ('Translation')  
go  
```  
  
 <span data-ttu-id="67dfc-144">Os atributos @xml:lang usam o namespace de XML predefinido.</span><span class="sxs-lookup"><span data-stu-id="67dfc-144">The @xml:lang attributes use the predefined xml namespace.</span></span> <span data-ttu-id="67dfc-145">Como o XML versão 1.0 não requer a declaração explícita da associação do namespace xml, o resultado não incluirá uma declaração explícita da associação de namespace.</span><span class="sxs-lookup"><span data-stu-id="67dfc-145">Because XML version 1.0 does not require the explicit declaration of the xml namespace binding, the result will not include an explicit declaration of the namespace binding.</span></span>  
  
 <span data-ttu-id="67dfc-146">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="67dfc-146">This is the result:</span></span>  
  
```  
<Translation>  
  <English xml:lang="en">food</English>  
  <German xml:lang="ger">Essen</German>  
</Translation>  
```  
  
## <a name="using-with-xmlnamespaces-with-the-xml-data-type-methods"></a><span data-ttu-id="67dfc-147">Usando WITH XMLNAMESPACES com métodos de tipos de dados xml</span><span class="sxs-lookup"><span data-stu-id="67dfc-147">Using WITH XMLNAMESPACES with the xml Data Type Methods</span></span>  
 <span data-ttu-id="67dfc-148">Os [Métodos de tipos de dados xml](/sql/t-sql/xml/xml-data-type-methods) especificados em uma consulta SELECT, ou em UPDATE quando o método for **modify()** , todos precisam repetir a declaração de namespace em seu prólogo.</span><span class="sxs-lookup"><span data-stu-id="67dfc-148">The [xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) specified in a SELECT query, or in UPDATE when it is the **modify()** method, all have to repeat the namespace declaration in their prolog.</span></span> <span data-ttu-id="67dfc-149">Isto pode ser demorado.</span><span class="sxs-lookup"><span data-stu-id="67dfc-149">This can be time-consuming.</span></span> <span data-ttu-id="67dfc-150">Por exemplo, a consulta a seguir recupera IDs de modelos de produtos cujas descrições no catálogo não incluem especificação.</span><span class="sxs-lookup"><span data-stu-id="67dfc-150">For example, the following query retrieves product model IDs whose catalog descriptions do include specification.</span></span> <span data-ttu-id="67dfc-151">Isto é, o elemento <`Specifications`> existe.</span><span class="sxs-lookup"><span data-stu-id="67dfc-151">That is, the <`Specifications`> element exists.</span></span>  
  
```  
SELECT ProductModelID, CatalogDescription.query('  
declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
    <Product   
        ProductModelID= "{ sql:column("ProductModelID") }"   
        />  
') AS Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist('  
    declare namespace  pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
     /pd:ProductDescription[(pd:Specifications)]'  
    ) = 1  
```  
  
 <span data-ttu-id="67dfc-152">Na consulta anterior, os métodos **query()** e **exist()** declaram o mesmo namespace em seus prólogos.</span><span class="sxs-lookup"><span data-stu-id="67dfc-152">In the previous query, both the **query()** and **exist()** methods declare the same namespace in their prolog.</span></span> <span data-ttu-id="67dfc-153">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="67dfc-153">For example:</span></span>  
  
```  
declare namespace pd="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription";  
```  
  
 <span data-ttu-id="67dfc-154">Alternativamente, você pode declarar WITH XMLNAMESPACES primeiro e usar os prefixos de namespace na consulta.</span><span class="sxs-lookup"><span data-stu-id="67dfc-154">Alternatively, you can declare WITH XMLNAMESPACES first and use the namespace prefixes in the query.</span></span> <span data-ttu-id="67dfc-155">Nesse caso, os métodos **query()** e **exist()** não precisam incluir declarações de namespace em seus prólogos.</span><span class="sxs-lookup"><span data-stu-id="67dfc-155">In this case, the **query()** and **exist()** methods  do not have to include namespace declarations in their prolog.</span></span>  
  
```  
WITH XMLNAMESPACES ('https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription' as pd)  
SELECT ProductModelID, CatalogDescription.query('  
    <Product   
        ProductModelID= "{ sql:column("ProductModelID") }"   
        />  
') AS Result  
FROM Production.ProductModel  
WHERE CatalogDescription.exist('  
     /pd:ProductDescription[(pd:Specifications)]'  
    ) = 1  
Go  
```  
  
 <span data-ttu-id="67dfc-156">Observe que uma declaração explícita no prólogo de XQuery substitui o prefixo de namespace e o namespace do elemento padrão definidos na cláusula WITH.</span><span class="sxs-lookup"><span data-stu-id="67dfc-156">Note that an explicit declaration in the XQuery prolog overrides the namespace prefix and the default element namespace that are defined in the WITH clause.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="67dfc-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="67dfc-157">See Also</span></span>  
 <span data-ttu-id="67dfc-158">[Métodos de tipos de dados xml](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="67dfc-158">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="67dfc-159">[Referência de linguagem XQuery &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server) </span><span class="sxs-lookup"><span data-stu-id="67dfc-159">[XQuery Language Reference &#40;SQL Server&#41;](/sql/xquery/xquery-language-reference-sql-server) </span></span>  
 <span data-ttu-id="67dfc-160">[WITH XMLNAMESPACES &#40;Transact-SQL&#41;](/sql/t-sql/xml/with-xmlnamespaces) </span><span class="sxs-lookup"><span data-stu-id="67dfc-160">[WITH XMLNAMESPACES &#40;Transact-SQL&#41;](/sql/t-sql/xml/with-xmlnamespaces) </span></span>  
 [<span data-ttu-id="67dfc-161">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="67dfc-161">FOR XML &#40;SQL Server&#41;</span></span>](for-xml-sql-server.md)  
  
  
