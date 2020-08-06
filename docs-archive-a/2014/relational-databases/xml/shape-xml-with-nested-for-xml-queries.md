---
title: Formar XML com consultas FOR XML aninhadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML query
- queries [XML in SQL Server], nested FOR XML
- XML [SQL Server], FOR XML queries
ms.assetid: 8dc42c05-16e8-4b7b-a5d3-550b55acae26
author: rothja
ms.author: jroth
ms.openlocfilehash: 738b5b3ec67dada90c851d284ccc8b3009a51aa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575680"
---
# <a name="shape-xml-with-nested-for-xml-queries"></a><span data-ttu-id="f1654-102">Formar XML com consultas FOR XML aninhadas</span><span class="sxs-lookup"><span data-stu-id="f1654-102">Shape XML with Nested FOR XML Queries</span></span>
  <span data-ttu-id="f1654-103">O exemplo a seguir consulta a tabela `Production.Product` para recuperar os valores de `ListPrice` e `StandardCost` de um produto específico.</span><span class="sxs-lookup"><span data-stu-id="f1654-103">The following example queries the `Production.Product` table to retrieve the `ListPrice` and `StandardCost` values of a specific product.</span></span> <span data-ttu-id="f1654-104">Para tornar a consulta interessante, os dois preços são retornados em um elemento <`Price`> e cada elemento <`Price`> tem um atributo `PriceType`.</span><span class="sxs-lookup"><span data-stu-id="f1654-104">To make the query interesting, both prices are returned in a <`Price`> element, and each <`Price`> element has a `PriceType` attribute.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f1654-105">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f1654-105">Example</span></span>  
 <span data-ttu-id="f1654-106">Esta é a forma esperada do XML:</span><span class="sxs-lookup"><span data-stu-id="f1654-106">This is the expected shape of the XML:</span></span>  
  
```  
<xsd:schema xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet2" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet2" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="Production.Product" type="xsd:anyType" />  
</xsd:schema>  
<Production.Product xmlns="urn:schemas-microsoft-com:sql:SqlRowSet2" ProductID="520">  
  <Price xmlns="" PriceType="ListPrice">133.34</Price>  
  <Price xmlns="" PriceType="StandardCost">98.77</Price>  
</Production.Product>  
```  
  
 <span data-ttu-id="f1654-107">Esta é a consulta FOR XML aninhada:</span><span class="sxs-lookup"><span data-stu-id="f1654-107">This is the nested FOR XML query:</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT Product.ProductID,   
          (SELECT 'ListPrice' as PriceType,   
                   CAST(CAST(ListPrice as NVARCHAR(40)) as XML)   
           FROM    Production.Product Price   
           WHERE   Price.ProductID=Product.ProductID   
           FOR XML AUTO, TYPE),  
          (SELECT  'StandardCost' as PriceType,   
                   CAST(CAST(StandardCost as NVARCHAR(40)) as XML)   
           FROM    Production.Product Price   
           WHERE   Price.ProductID=Product.ProductID   
           FOR XML AUTO, TYPE)  
FROM Production.Product  
WHERE ProductID=520  
for XML AUTO, TYPE, XMLSCHEMA  
```  
  
 <span data-ttu-id="f1654-108">Observe o seguinte na consulta anterior:</span><span class="sxs-lookup"><span data-stu-id="f1654-108">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="f1654-109">A instrução SELECT externa constrói o elemento <`Product`> que tem um atributo **ProductID** e dois elementos filho <`Price`>.</span><span class="sxs-lookup"><span data-stu-id="f1654-109">The outer SELECT statement constructs the <`Product`> element that has a **ProductID** attribute and two <`Price`> child elements.</span></span>  
  
-   <span data-ttu-id="f1654-110">A instrução SELECT interna constrói dois elementos <`Price`>, cada um com um atributo **PriceType** e XML que retorna o preço do produto.</span><span class="sxs-lookup"><span data-stu-id="f1654-110">The two inner SELECT statements construct two <`Price`> elements, each with a **PriceType** attribute and XML that returns the product price.</span></span>  
  
-   <span data-ttu-id="f1654-111">A diretiva XMLSCHEMA na instrução SELECT externa gera o esquema XSD embutido que descreve a forma do XML resultante.</span><span class="sxs-lookup"><span data-stu-id="f1654-111">The XMLSCHEMA directive in the outer SELECT statement generates the inline XSD schema that describes the shape of the resulting XML.</span></span>  
  
 <span data-ttu-id="f1654-112">Para tornar a consulta interessante, é possível escrever a consulta FOR XML e, em seguida, escrever uma XQuery em relação ao resultado para reformatar o XML, conforme mostrado na seguinte consulta:</span><span class="sxs-lookup"><span data-stu-id="f1654-112">To make the query interesting, you can write the FOR XML query and then write an XQuery against the result to reshape the XML, as shown in the following query:</span></span>  
  
```  
SELECT ProductID,   
 ( SELECT p2.ListPrice, p2.StandardCost  
   FROM Production.Product p2   
   WHERE Product.ProductID = p2.ProductID  
   FOR XML AUTO, ELEMENTS XSINIL, type ).query('  
                                   for $p in /p2/*  
                                   return   
                                    <Price PriceType = "{local-name($p)}">  
                                     { data($p) }  
                                    </Price>  
                                  ')  
FROM Production.Product  
WHERE ProductID = 520  
FOR XML AUTO, TYPE  
```  
  
 <span data-ttu-id="f1654-113">O exemplo anterior usa o método `query()` do tipo de dados `xml` para consultar o XML retornado pela consulta FOR XML interna e construir o resultado esperado.</span><span class="sxs-lookup"><span data-stu-id="f1654-113">The previous example uses the `query()` method of the `xml` data type to query the XML returned by the inner FOR XML query and construct the expected result.</span></span>  
  
 <span data-ttu-id="f1654-114">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="f1654-114">This is the result:</span></span>  
  
```  
<Production.Product ProductID="520">  
  <Price PriceType="ListPrice">133.3400</Price>  
  <Price PriceType="StandardCost">98.7700</Price>  
</Production.Product>  
```  
  
## <a name="see-also"></a><span data-ttu-id="f1654-115">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f1654-115">See Also</span></span>  
 [<span data-ttu-id="f1654-116">Usar consultas FOR XML aninhadas</span><span class="sxs-lookup"><span data-stu-id="f1654-116">Use Nested FOR XML Queries</span></span>](use-nested-for-xml-queries.md)  
  
  
