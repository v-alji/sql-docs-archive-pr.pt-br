---
title: Gerar um esquema XSD embutido | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XSD schemas [SQL Server]
- XMLSCHEMA option
- schemas [SQL Server], XML
- XDR schemas
- FOR XML clause, inline XSD schema generation
- inline XSD schema generation [SQL Server]
- XMLDATA option
ms.assetid: 04b35145-1cca-45f4-9eb7-990abf2e647d
author: rothja
ms.author: jroth
ms.openlocfilehash: 2af748d4fc6ae67f57568be58ec7f59876098f52
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686182"
---
# <a name="generate-an-inline-xsd-schema"></a><span data-ttu-id="30e2b-102">Gerar um esquema XSD embutido</span><span class="sxs-lookup"><span data-stu-id="30e2b-102">Generate an Inline XSD Schema</span></span>
  <span data-ttu-id="30e2b-103">Em uma cláusula FOR XML, é possível solicitar que a consulta retorne um esquema embutido junto com os resultados da consulta.</span><span class="sxs-lookup"><span data-stu-id="30e2b-103">In a FOR XML clause, you can request that your query return an inline schema together with the query results.</span></span> <span data-ttu-id="30e2b-104">Para obter um esquema XDR, use a palavra-chave XMLDATA na cláusula FOR XML.</span><span class="sxs-lookup"><span data-stu-id="30e2b-104">If you want an XDR schema, you use the XMLDATA keyword in the FOR XML clause.</span></span> <span data-ttu-id="30e2b-105">Para obter um esquema XSD, use a palavra-chave XMLSCHEMA.</span><span class="sxs-lookup"><span data-stu-id="30e2b-105">If you want an XSD schema, you use the XMLSCHEMA keyword.</span></span>  
  
 <span data-ttu-id="30e2b-106">Este tópico descreve a palavra-chave XMLSCHEMA e explica a estrutura do esquema XSD embutido resultante.</span><span class="sxs-lookup"><span data-stu-id="30e2b-106">This topic describes the XMLSCHEMA keyword and explains the structure of the resulting inline XSD schema.</span></span> <span data-ttu-id="30e2b-107">As limitações a seguir estão presentes quando você está solicitando esquemas embutidos:</span><span class="sxs-lookup"><span data-stu-id="30e2b-107">Following are the limitations when you are requesting inline schemas:</span></span>  
  
-   <span data-ttu-id="30e2b-108">É possível especificar XMLSCHEMA em modo RAW e AUTO, não em modo EXPLICIT.</span><span class="sxs-lookup"><span data-stu-id="30e2b-108">You can specify XMLSCHEMA only in RAW and AUTO mode, not in EXPLICIT mode.</span></span>  
  
-   <span data-ttu-id="30e2b-109">Se uma consulta FOR XML aninhada especificar a diretiva TYPE, o resultado da consulta será do tipo `xml` e esse resultado será tratado como uma instância de dados XML não tipados.</span><span class="sxs-lookup"><span data-stu-id="30e2b-109">If a nested FOR XML query specifies the TYPE directive, the query result is of `xml` type, and this result is treated as an instance of untyped XML data.</span></span> <span data-ttu-id="30e2b-110">Para obter mais informações, veja [Dados XML &#40;SQL Server&#41;](xml-data-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="30e2b-110">For more information, see [XML Data &#40;SQL Server&#41;](xml-data-sql-server.md).</span></span>  
  
 <span data-ttu-id="30e2b-111">Quando você especifica XMLSCHEMA em uma consulta FOR XML, recebe um esquema e dados XML, o resultado da consulta.</span><span class="sxs-lookup"><span data-stu-id="30e2b-111">When you specify XMLSCHEMA in a FOR XML query, you receive both a schema and XML data, the query result.</span></span> <span data-ttu-id="30e2b-112">Cada elemento de alto nível dos dados faz referência ao esquema anterior usando uma declaração de namespace padrão que, por sua vez, faz referência ao namespace de destino do esquema embutido.</span><span class="sxs-lookup"><span data-stu-id="30e2b-112">Each top-level element of the data refers to the previous schema by using a default namespace declaration that, in turn, refers to the target namespace of the inline schema.</span></span>  
  
 <span data-ttu-id="30e2b-113">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="30e2b-113">For example:</span></span>  
  
```  
<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="Production.ProductModel">  
    <xsd:complexType>  
      <xsd:attribute name="ProductModelID" type="sqltypes:int" use="required" />  
      <xsd:attribute name="Name" use="required">  
        <xsd:simpleType sqltypes:sqlTypeAlias="[AdventureWorks2012].[dbo].[Name]">  
          <xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033" sqltypes:sqlCompareOptions="IgnoreCase IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">  
            <xsd:maxLength value="50" />  
          </xsd:restriction>  
        </xsd:simpleType>  
      </xsd:attribute>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
<Production.ProductModel xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" ProductModelID="1" Name="Classic Vest" />  
```  
  
 <span data-ttu-id="30e2b-114">O resultado inclui o esquema XML e o resultado do XML.</span><span class="sxs-lookup"><span data-stu-id="30e2b-114">The result includes XML schema and the XML result.</span></span> <span data-ttu-id="30e2b-115">O elemento de alto nível <`ProductModel`> no resultado faz referência ao esquema usando a declaração de namespace padrão, xmlns = "urn:schemas-microsoft-com:sql:SqlRowSet 1."</span><span class="sxs-lookup"><span data-stu-id="30e2b-115">The <`ProductModel`> top-level element in the result refers to the schema by using the default namespace declaration, xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" .</span></span>  
  
 <span data-ttu-id="30e2b-116">A parte de esquema do resultado pode conter vários documentos de esquema que descrevem vários namespaces.</span><span class="sxs-lookup"><span data-stu-id="30e2b-116">The schema part of the result may contain multiple schema documents that describe multiple namespaces.</span></span> <span data-ttu-id="30e2b-117">Como um mínimo, os seguintes dois documentos de esquema são retornados:</span><span class="sxs-lookup"><span data-stu-id="30e2b-117">At a minimum, the following two schema documents are returned:</span></span>  
  
-   <span data-ttu-id="30e2b-118">Um documento de esquema para o namespace **Sqltypes** e para o qual os tipos básicos de SQL estão sendo retornados.</span><span class="sxs-lookup"><span data-stu-id="30e2b-118">One schema document for the **Sqltypes** namespace, and for which the base SQL types are being returned.</span></span>  
  
-   <span data-ttu-id="30e2b-119">Outro documento de esquema que descreve a forma do resultado da consulta FOR XML.</span><span class="sxs-lookup"><span data-stu-id="30e2b-119">Another schema document that describes the shape of the FOR XML query result.</span></span>  
  
 <span data-ttu-id="30e2b-120">Além disso, se quaisquer tipos de dados `xml` tipados estiverem incluídos no resultado da consulta, os esquemas associados a esses tipos de dados `xml` tipados serão incluídos.</span><span class="sxs-lookup"><span data-stu-id="30e2b-120">Also, if any typed `xml` data types are included in the query result, the schemas associated with those typed `xml` data types are included.</span></span>  
  
 <span data-ttu-id="30e2b-121">O namespace de destino do documento de esquema que descreve a forma do resultado de FOR XML contém uma parte fixa e uma parte numérica que é incrementada automaticamente.</span><span class="sxs-lookup"><span data-stu-id="30e2b-121">The target namespace of the schema document that describes the shape of the FOR XML result contains a fixed portion and a numeric portion that increments automatically.</span></span> <span data-ttu-id="30e2b-122">O formato desse namespace é mostrado no exemplo a seguir em que *n* é um inteiro positivo.</span><span class="sxs-lookup"><span data-stu-id="30e2b-122">The format of this namespace is shown in the following where *n* is a positive integer.</span></span> <span data-ttu-id="30e2b-123">Por exemplo, na consulta anterior, urn:schemas-microsoft-com:sql:SqlRowSet 1 é o namespace de destino.</span><span class="sxs-lookup"><span data-stu-id="30e2b-123">For example, in the previous query, urn:schemas-microsoft-com:sql:SqlRowSet1 is the target namespace.</span></span>  
  
```  
urn:schemas-microsoft-com:sql:SqlRowSetn  
```  
  
 <span data-ttu-id="30e2b-124">A alteração nos namespaces de destino no resultado que ocorreu de uma execução para outra pode não ser desejável.</span><span class="sxs-lookup"><span data-stu-id="30e2b-124">The change in the target namespaces in the result that occurred from one execution to another may not be desirable.</span></span> <span data-ttu-id="30e2b-125">Por exemplo, se você consultar o XML resultante, a alteração no namespace de destino precisará que a consulta seja atualizada.</span><span class="sxs-lookup"><span data-stu-id="30e2b-125">For example, if you query the resulting XML, the change in target namespace will require that you update your query.</span></span> <span data-ttu-id="30e2b-126">Opcionalmente, é possível especificar um namespace de destino quando a opção XMLSCHEMA é adicionada à cláusula FOR XML.</span><span class="sxs-lookup"><span data-stu-id="30e2b-126">You can optionally specify a target namespace when the XMLSCHEMA option is added in the FOR XML clause.</span></span> <span data-ttu-id="30e2b-127">O XML resultante incluirá o namespace fornecido e permanecerá igual, independentemente de quantas vezes você executou a consulta.</span><span class="sxs-lookup"><span data-stu-id="30e2b-127">The resulting XML will include the namespace you provided and will remain the same, regardless of how many times you run the query.</span></span>  
  
```  
SELECT ProductModelID, Name  
FROM   Production.ProductModel  
WHERE ProductModelID=1  
FOR XML AUTO, XMLSCHEMA ('MyURI')  
```  
  
## <a name="entity-elements"></a><span data-ttu-id="30e2b-128">Elementos de entidade</span><span class="sxs-lookup"><span data-stu-id="30e2b-128">Entity Elements</span></span>  
 <span data-ttu-id="30e2b-129">Para discutir os detalhes da estrutura do esquema XSD gerada para o resultado da consulta, é necessário primeiro descrever o elemento</span><span class="sxs-lookup"><span data-stu-id="30e2b-129">In order to discuss the details of the XSD schema structure generated for the query result, the entity element has to first be described</span></span>  
  
 <span data-ttu-id="30e2b-130">Um elemento de entidade nos dados XML retornados pela consulta FOR XML é um elemento gerado a partir de uma tabela e não de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="30e2b-130">An entity element in the XML data returned by FOR XML query is an element that is generated from a table and not from a column.</span></span> <span data-ttu-id="30e2b-131">Por exemplo, a consulta FOR XML a seguir retorna informações de contato da tabela `Person` no banco de dados `AdventureWorks2012` .</span><span class="sxs-lookup"><span data-stu-id="30e2b-131">For example, the following FOR XML query returns contact information from the `Person` table in the `AdventureWorks2012` database.</span></span>  
  
```  
SELECT BusinessEntityID, FirstName  
FROM Person.Person  
WHERE BusinessEntityID = 1  
FOR XML AUTO, ELEMENTS  
```  
  
 <span data-ttu-id="30e2b-132">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="30e2b-132">This is the result:</span></span>  
  
 `<Person>`  
  
 `<BusinessEntityID>1</BusinessEntityID>`  
  
 `<FirstName>Ken</FirstName>`  
  
 `</Person>`  
  
 <span data-ttu-id="30e2b-133">Nesse resultado, <`Person`> é o elemento de entidade.</span><span class="sxs-lookup"><span data-stu-id="30e2b-133">In this result, <`Person`> is the entity element.</span></span> <span data-ttu-id="30e2b-134">Pode haver vários elementos de entidade no resultado XML e cada um deles tem uma declaração global no esquema XSD embutido.</span><span class="sxs-lookup"><span data-stu-id="30e2b-134">There can be multiple entity elements in the XML result and each of these has a global declaration in the inline XSD schema.</span></span> <span data-ttu-id="30e2b-135">Por exemplo, a consulta a seguir recupera o cabeçalho do pedido de vendas e informações detalhadas de um pedido específico.</span><span class="sxs-lookup"><span data-stu-id="30e2b-135">For example, the following query retrieves sales order header and detail information for a specific order.</span></span>  
  
```  
SELECT  SalesOrderHeader.SalesOrderID, ProductID, OrderQty  
FROM    Sales.SalesOrderHeader, Sales.SalesOrderDetail  
WHERE   SalesOrderHeader.SalesOrderID = SalesOrderDetail.SalesOrderID  
AND     SalesOrderHeader.SalesOrderID=5001  
FOR XML AUTO, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="30e2b-136">Como a consulta especifica a diretiva ELEMENTS, o XML resultante é centrado em elemento.</span><span class="sxs-lookup"><span data-stu-id="30e2b-136">Because the query specifies the ELEMENTS directive, the resulting XML is element-centric.</span></span> <span data-ttu-id="30e2b-137">A consulta também especifica a diretiva XMLSCHEMA.</span><span class="sxs-lookup"><span data-stu-id="30e2b-137">The query also specifies the XMLSCHEMA directive.</span></span> <span data-ttu-id="30e2b-138">Portanto, um esquema XSD embutido é retornado.</span><span class="sxs-lookup"><span data-stu-id="30e2b-138">Therefore, an inline XSD schema is returned.</span></span> <span data-ttu-id="30e2b-139">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="30e2b-139">This is the result:</span></span>  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:schema="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />`  
  
 `<xsd:element name="Sales.SalesOrderHeader">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="SalesOrderID" type="sqltypes:int" />`  
  
 `<xsd:element ref="schema:Sales.SalesOrderDetail" minOccurs="0" maxOccurs="unbounded" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `<xsd:element name="Sales.SalesOrderDetail">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" />`  
  
 `<xsd:element name="OrderQty" type="sqltypes:smallint" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 <span data-ttu-id="30e2b-140">Observe o seguinte na consulta anterior:</span><span class="sxs-lookup"><span data-stu-id="30e2b-140">Note the following from the previous query:</span></span>  
  
-   <span data-ttu-id="30e2b-141">No resultado, <`SalesOrderHeader`> e <`SalesOrderDetail`> são elementos de entidade.</span><span class="sxs-lookup"><span data-stu-id="30e2b-141">In the result, <`SalesOrderHeader`> and <`SalesOrderDetail`> are entity elements.</span></span> <span data-ttu-id="30e2b-142">Por isso, eles são declarados globalmente no esquema.</span><span class="sxs-lookup"><span data-stu-id="30e2b-142">Because of this, they are globally declared in the schema.</span></span> <span data-ttu-id="30e2b-143">Isto é, a declaração é exibida no nível superior dentro do elemento <`Schema`>.</span><span class="sxs-lookup"><span data-stu-id="30e2b-143">That is, the declaration appears at the top level inside the <`Schema`> element.</span></span>  
  
-   <span data-ttu-id="30e2b-144">O <`SalesOrderID`>, <`ProductID`>e <`OrderQty`> não são elementos de entidade porque são mapeados para colunas.</span><span class="sxs-lookup"><span data-stu-id="30e2b-144">The <`SalesOrderID`>, <`ProductID`>, and <`OrderQty`> are not entity elements, because they map to columns.</span></span> <span data-ttu-id="30e2b-145">Os dados de coluna são retornados como elementos no XML por causa da diretiva ELEMENTS.</span><span class="sxs-lookup"><span data-stu-id="30e2b-145">The column data is returned as elements in the XML, because of the ELEMENTS directive.</span></span> <span data-ttu-id="30e2b-146">Estes são mapeados para elementos locais do tipo complexo do elemento de entidade.</span><span class="sxs-lookup"><span data-stu-id="30e2b-146">These are mapped to local elements of the entity element's complex type.</span></span> <span data-ttu-id="30e2b-147">Observe que, se a diretiva ELEMENTS não for especificada, os valores de `SalesOrderID`, `ProductID` e `OrderQty` serão mapeados para atributos locais do tipo complexo do elemento de entidade correspondente.</span><span class="sxs-lookup"><span data-stu-id="30e2b-147">Note that if the ELEMENTS directive is not specified, the `SalesOrderID`, `ProductID` and `OrderQty` values are mapped to local attributes of the corresponding entity element's complex type.</span></span>  
  
## <a name="attribute-name-clashes"></a><span data-ttu-id="30e2b-148">Conflitos de nomes de atributos</span><span class="sxs-lookup"><span data-stu-id="30e2b-148">Attribute Name Clashes</span></span>  
 <span data-ttu-id="30e2b-149">A discussão a seguir baseia-se nas tabelas `CustOrder` e `CustOrderDetail` .</span><span class="sxs-lookup"><span data-stu-id="30e2b-149">The following discussion is based on the `CustOrder` and `CustOrderDetail` tables.</span></span> <span data-ttu-id="30e2b-150">Para testar os exemplos a seguir, crie essas tabelas e adicione seus próprios dados de exemplo:</span><span class="sxs-lookup"><span data-stu-id="30e2b-150">To test the following samples, create these tables and add your own sample data:</span></span>  
  
```  
CREATE TABLE CustOrder (OrderID int primary key, CustomerID int)  
GO  
CREATE TABLE CustOrderDetail (OrderID int, ProductID int, Qty int)  
GO  
```  
  
 <span data-ttu-id="30e2b-151">No FOR XML, algumas vezes, o mesmo nome é usado para indicar propriedades e atributos diferentes.</span><span class="sxs-lookup"><span data-stu-id="30e2b-151">In FOR XML, the same name is sometimes used to indicate different properties, attributes.</span></span> <span data-ttu-id="30e2b-152">Por exemplo, a seguinte consulta em modo RAW centrada em atributo gera dois atributos que têm o mesmo nome, OrderID.</span><span class="sxs-lookup"><span data-stu-id="30e2b-152">For example, the following attribute-centric RAW mode query generates two attributes that have the same name, OrderID.</span></span> <span data-ttu-id="30e2b-153">Isso gera um erro.</span><span class="sxs-lookup"><span data-stu-id="30e2b-153">This generates an error.</span></span>  
  
```  
SELECT CustOrder.OrderID,   
       CustOrderDetail.ProductID,   
       CustOrderDetail.OrderID  
FROM   dbo.CustOrder, dbo.CustOrderDetail  
WHERE  CustOrder.OrderID = CustOrderDetail.OrderID  
FOR XML RAW, XMLSCHEMA  
```  
  
 <span data-ttu-id="30e2b-154">No entanto, como é aceitável ter dois elementos com o mesmo nome, é possível eliminar o problema adicionando a diretiva ELEMENTS:</span><span class="sxs-lookup"><span data-stu-id="30e2b-154">However, because it is acceptable to have two elements that have the same name, you can eliminate the problem by adding the ELEMENTS directive:</span></span>  
  
```  
SELECT CustOrder.OrderID,  
       CustOrderDetail.ProductID,   
       CustOrderDetail.OrderID  
from   dbo.CustOrder, dbo.CustOrderDetail  
where  CustOrder.OrderID = CustOrderDetail.OrderID  
FOR XML RAW, XMLSCHEMA, ELEMENTS  
```  
  
 <span data-ttu-id="30e2b-155">Este é o resultado.</span><span class="sxs-lookup"><span data-stu-id="30e2b-155">This is the result.</span></span> <span data-ttu-id="30e2b-156">Observe que no esquema XSD embutido, o elemento OrderID está definido duas vezes.</span><span class="sxs-lookup"><span data-stu-id="30e2b-156">Note in the inline XSD schema, the OrderID element is defined two times.</span></span> <span data-ttu-id="30e2b-157">Uma das declarações tem minOccurs definido como 0, que corresponde ao OrderID da tabela CustOrderDetail, e a segunda é mapeada para a coluna de chave primária OrderID da tabela `CustOrder` , na qual, por padrão, minOccurs é 1.</span><span class="sxs-lookup"><span data-stu-id="30e2b-157">One of the declarations has minOccurs set to 0, corresponding to the OrderID from the CustOrderDetail table, and the second one maps to the OrderID primary key column of the `CustOrder` table where minOccurs is 1 by default.</span></span>  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="OrderID" type="sqltypes:int" />`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" minOccurs="0" />`  
  
 `<xsd:element name="OrderID" type="sqltypes:int" minOccurs="0" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
## <a name="element-name-clashes"></a><span data-ttu-id="30e2b-158">Conflitos de nomes de elementos</span><span class="sxs-lookup"><span data-stu-id="30e2b-158">Element Name Clashes</span></span>  
 <span data-ttu-id="30e2b-159">Em FOR XML, o mesmo nome pode ser usado para indicar dois subelementos.</span><span class="sxs-lookup"><span data-stu-id="30e2b-159">In FOR XML, the same name can be used to indicate two subelements.</span></span> <span data-ttu-id="30e2b-160">Por exemplo, a consulta a seguir recupera valores de ListPrice e DealerPrice de produtos, mas a consulta especifica o mesmo alias, Price, para essas duas colunas.</span><span class="sxs-lookup"><span data-stu-id="30e2b-160">For example, the following query retrieves ListPrice and DealerPrice values of products, but the query specifies the same alias, Price, for these two columns.</span></span> <span data-ttu-id="30e2b-161">Portanto o conjunto de linhas resultante terá duas colunas com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="30e2b-161">Therefore, the resulting rowset will have two columns with same name.</span></span>  
  
### <a name="case-1-both-subelements-are-nonkey-columns-of-the-same-type-and-can-be-null"></a><span data-ttu-id="30e2b-162">Caso 1: Os dois subelementos são colunas não chave do mesmo tipo e podem ser NULL</span><span class="sxs-lookup"><span data-stu-id="30e2b-162">Case 1: Both subelements are nonkey columns of the same type and can be NULL</span></span>  
 <span data-ttu-id="30e2b-163">Na consulta seguinte, os dois subelementos são colunas não chave do mesmo tipo e podem ser NULL.</span><span class="sxs-lookup"><span data-stu-id="30e2b-163">In the following query, both subelements are nonkey columns of the same type and can be NULL.</span></span>  
  
```  
DROP TABLE T  
go  
CREATE TABLE T (ProductID int primary key, ListPrice money, DealerPrice money)  
go  
INSERT INTO T values (1, 1.25, null)  
go  
  
SELECT ProductID, ListPrice Price, DealerPrice Price  
FROM   T  
for    XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="30e2b-164">Este é o XML correspondente gerado.</span><span class="sxs-lookup"><span data-stu-id="30e2b-164">This is the corresponding XML generated.</span></span> <span data-ttu-id="30e2b-165">Apenas uma fração do XSD embutido é mostrada:</span><span class="sxs-lookup"><span data-stu-id="30e2b-165">Only a fraction of the inline XSD is shown:</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" minOccurs="0" maxOccurs="2" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<ProductID>1</ProductID>`  
  
 `<Price>1.2500</Price>`  
  
 `</row>`  
  
 <span data-ttu-id="30e2b-166">Observe o seguinte no esquema XSD embutido:</span><span class="sxs-lookup"><span data-stu-id="30e2b-166">Note the following in the inline XSD schema:</span></span>  
  
-   <span data-ttu-id="30e2b-167">ListPrice e DealerPrice são do mesmo tipo, `money`, e ambos podem ser NULL na tabela.</span><span class="sxs-lookup"><span data-stu-id="30e2b-167">Both the ListPrice and DealerPrice are of the same type, `money`, and both can be NULL in the table.</span></span> <span data-ttu-id="30e2b-168">Portanto, como eles podem não ser retornados no XML resultante, há apenas um elemento filho <`Price`> na declaração de tipo complexo do elemento <`row`> que tem minOccurs=0 e maxOccurs=2.</span><span class="sxs-lookup"><span data-stu-id="30e2b-168">Therefore, because they may not be returned in the resulting XML, there is only one <`Price`> child element in the complex type declaration of the <`row`> element that has minOccurs=0 and maxOccurs=2.</span></span>  
  
-   <span data-ttu-id="30e2b-169">No resultado, como o valor de `DealerPrice` é NULL na tabela, apenas `ListPrice` é retornado como um elemento <`Price`>.</span><span class="sxs-lookup"><span data-stu-id="30e2b-169">In the result, because the `DealerPrice` value is NULL in the table, only `ListPrice` is returned as a <`Price`> element.</span></span> <span data-ttu-id="30e2b-170">Se adicionar o parâmetro `XSINIL` à diretiva ELEMENTS, você receberá os dois elementos que têm o valor de `xsi:nil` definido como TRUE para o elemento<`Price`> correspondente a DealerPrice.</span><span class="sxs-lookup"><span data-stu-id="30e2b-170">If you add the `XSINIL` parameter to the ELEMENTS directive, you will receive both of the elements that have the `xsi:nil` value set to TRUE for the<`Price`> element that corresponds to DealerPrice.</span></span> <span data-ttu-id="30e2b-171">Também receberá dois elementos filho <`Price`> na definição de tipo complexo <`row`> no esquema XSD embutido com o atributo `nillable` definido como TRUE para ambos.</span><span class="sxs-lookup"><span data-stu-id="30e2b-171">You will also receive two <`Price`> child elements in the <`row`> complex type definition in the inline XSD schema with the `nillable` attribute set to TRUE for both.</span></span> <span data-ttu-id="30e2b-172">Este fragmento é um resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="30e2b-172">This fragment is a partial result:</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="ProductID" type="sqltypes:int" nillable="1" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" nillable="1" />`  
  
 `<xsd:element name="Price" type="sqltypes:money" nillable="1" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">`  
  
 `<ProductID>1</ProductID>`  
  
 `<Price>1.2500</Price>`  
  
 `<Price xsi:nil="true" />`  
  
 `</row>`  
  
### <a name="case-2-one-key-and-one-nonkey-column-of-the-same-type"></a><span data-ttu-id="30e2b-173">Caso 2: Uma coluna de chave e uma de não chave do mesmo tipo</span><span class="sxs-lookup"><span data-stu-id="30e2b-173">Case 2: One key and one nonkey column of the same type</span></span>  
 <span data-ttu-id="30e2b-174">A consulta a seguir ilustra uma coluna de chave e uma de não chave do mesmo tipo.</span><span class="sxs-lookup"><span data-stu-id="30e2b-174">The following query illustrates one key and one nonkey column of the same type.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 int, Col3 nvarchar(20))  
go  
INSERT INTO T VALUES (1, 1, 'test')  
go   
```  
  
 <span data-ttu-id="30e2b-175">A seguinte consulta na tabela **T** especifica o mesmo alias para Col1 e Col2, em que Col1 é uma chave primária e não pode ser nula e Col2 pode ser nula.</span><span class="sxs-lookup"><span data-stu-id="30e2b-175">The following query against table **T** specifies the same alias for Col1 and Col2, where Col1 is a primary key and cannot be null, and Col2 can be null.</span></span> <span data-ttu-id="30e2b-176">Isso gera dois elementos irmãos que são filhos do elemento <`row`>.</span><span class="sxs-lookup"><span data-stu-id="30e2b-176">This generates two sibling elements that are children of the <`row`> element.</span></span>  
  
```  
SELECT Col1 as Col, Col2 as Col, Col3  
FROM T  
FOR XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="30e2b-177">Este é o resultado.</span><span class="sxs-lookup"><span data-stu-id="30e2b-177">This is the result.</span></span> <span data-ttu-id="30e2b-178">Apenas um fragmento do esquema XSD embutido é mostrado.</span><span class="sxs-lookup"><span data-stu-id="30e2b-178">Only a fragment of the inline XSD schema is shown.</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="Col" type="sqltypes:int" />`  
  
 `<xsd:element name="Col" type="sqltypes:int" minOccurs="0" />`  
  
 `<xsd:element name="Col3" minOccurs="0">`  
  
 `<xsd:simpleType>`  
  
 `<xsd:restriction base="sqltypes:nvarchar"`  
  
 `sqltypes:localeId="1033"`  
  
 `sqltypes:sqlCompareOptions="IgnoreCase`  
  
 `IgnoreKanaType IgnoreWidth"`  
  
 `sqltypes:sqlSortId="52">`  
  
 `<xsd:maxLength value="20" />`  
  
 `</xsd:restriction>`  
  
 `</xsd:simpleType>`  
  
 `</xsd:element>`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<Col>1</Col>`  
  
 `<Col>1</Col>`  
  
 `<Col3>test</Col3>`  
  
 `</row>`  
  
 <span data-ttu-id="30e2b-179">Observe que, no esquema XSD embutido, o elemento <`Col`> correspondente a Col2 tem minOccurs definido como 0.</span><span class="sxs-lookup"><span data-stu-id="30e2b-179">Note in the inline XSD schema that the <`Col`> element corresponding to the Col2 has minOccurs set to 0.</span></span>  
  
### <a name="case-3-both-elements-of-different-types-and-corresponding-columns-can-be-null"></a><span data-ttu-id="30e2b-180">Caso 3: Os dois elementos de tipos diferentes e colunas correspondentes podem ser NULL</span><span class="sxs-lookup"><span data-stu-id="30e2b-180">Case 3: Both elements of different types and corresponding columns can be NULL</span></span>  
 <span data-ttu-id="30e2b-181">A consulta seguinte é especificada para a tabela de exemplo mostrada no caso 2:</span><span class="sxs-lookup"><span data-stu-id="30e2b-181">The following query is specified against the sample table shown in case 2:</span></span>  
  
```  
SELECT Col1, Col2 as Col, Col3 as Col  
FROM T  
FOR XML RAW, ELEMENTS, XMLSCHEMA  
```  
  
 <span data-ttu-id="30e2b-182">Na consulta a seguir, Col2 e Col3 recebem os mesmos alias.</span><span class="sxs-lookup"><span data-stu-id="30e2b-182">In the following query, Col2 and Col3 are given the same aliases.</span></span> <span data-ttu-id="30e2b-183">Isso gera dois elementos irmãos que têm o mesmo nome e que são filhos do elemento <`raw`> no resultado.</span><span class="sxs-lookup"><span data-stu-id="30e2b-183">This generates two sibling elements that have the same name and that are both children of the <`raw`> element in the result.</span></span> <span data-ttu-id="30e2b-184">Essas duas colunas são de tipos diferentes e podem ser NULL.</span><span class="sxs-lookup"><span data-stu-id="30e2b-184">Both of these columns are of different types and both can be NULL.</span></span> <span data-ttu-id="30e2b-185">Este é o resultado.</span><span class="sxs-lookup"><span data-stu-id="30e2b-185">This is the result.</span></span> <span data-ttu-id="30e2b-186">Apenas um esquema XSD embutido parcial é mostrado.</span><span class="sxs-lookup"><span data-stu-id="30e2b-186">Only partial inline XSD schema is shown.</span></span>  
  
 `...`  
  
 `<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">`  
  
 `<xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" />`  
  
 `<xsd:simpleType name="Col1">`  
  
 `<xsd:restriction base="sqltypes:int" />`  
  
 `</xsd:simpleType>`  
  
 `<xsd:simpleType name="Col2">`  
  
 `<xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033"`  
  
 `sqltypes:sqlCompareOptions="IgnoreCase`  
  
 `IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">`  
  
 `<xsd:maxLength value="20" />`  
  
 `</xsd:restriction>`  
  
 `</xsd:simpleType>`  
  
 `<xsd:element name="row">`  
  
 `<xsd:complexType>`  
  
 `<xsd:sequence>`  
  
 `<xsd:element name="Col1" type="sqltypes:int" />`  
  
 `<xsd:element name="Col" minOccurs="0" maxOccurs="2" type="xsd:anySimpleType" />`  
  
 `</xsd:sequence>`  
  
 `</xsd:complexType>`  
  
 `</xsd:element>`  
  
 `</xsd:schema>`  
  
 `<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1">`  
  
 `<Col1>1</Col1>`  
  
 `<Col xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`  
  
 `xsi:type="Col1">1</Col>`  
  
 `<Col xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance"`  
  
 `xsi:type="Col2">test</Col>`  
  
 `</row>`  
  
 <span data-ttu-id="30e2b-187">Observe o seguinte no esquema XSD embutido:</span><span class="sxs-lookup"><span data-stu-id="30e2b-187">Note the following in the inline XSD schema:</span></span>  
  
-   <span data-ttu-id="30e2b-188">Como Col2 e Col3 podem ser NULL, a declaração do elemento <`Col`> especifica minOccurs como 0 e maxOccurs como 2.</span><span class="sxs-lookup"><span data-stu-id="30e2b-188">Because both Col2 and Col3 can be NULL, the <`Col`> element declaration specifies the minOccurs as 0 and maxOccurs as 2.</span></span>  
  
-   <span data-ttu-id="30e2b-189">Como os dois elementos <`Col`> são irmãos, há uma declaração de elemento no esquema.</span><span class="sxs-lookup"><span data-stu-id="30e2b-189">Because both the <`Col`> elements are siblings, there is one element declaration in the schema.</span></span> <span data-ttu-id="30e2b-190">Além disso, como os dois elementos também são de tipos diferentes, embora ambos sejam de tipos simples, o tipo do elemento no esquema é `xsd:anySimpleType`.</span><span class="sxs-lookup"><span data-stu-id="30e2b-190">Also, because both of the elements are also of different types, though both are simple types, the type of the element in the schema is `xsd:anySimpleType`.</span></span> <span data-ttu-id="30e2b-191">No resultado, cada tipo de instância é identificado pelo atributo `xsi:type` .</span><span class="sxs-lookup"><span data-stu-id="30e2b-191">In the result, each instance type is identified by the `xsi:type` attribute.</span></span>  
  
-   <span data-ttu-id="30e2b-192">No resultado, cada instância do elemento <`Col`> faz referência ao seu tipo de instância usando o atributo `xsi:type`.</span><span class="sxs-lookup"><span data-stu-id="30e2b-192">In the result, every instance of the <`Col`> element refers to its instance type by using the `xsi:type` attribute.</span></span>  
  
  
