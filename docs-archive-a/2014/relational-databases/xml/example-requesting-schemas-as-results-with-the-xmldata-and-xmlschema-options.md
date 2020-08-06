---
title: 'Exemplo: solicitando esquemas como resultados com as opções XMLDATA e XMLSCHEMA | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- RAW mode, requesting schema example
- RAW mode, with XMLDATA and XMLSCHEMA
ms.assetid: 3504ca38-be66-42b2-8dab-f499c9584840
author: rothja
ms.author: jroth
ms.openlocfilehash: af244e3436df4d8665079ce20fb749a44021fe04
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684629"
---
# <a name="example-requesting-schemas-as-results-with-the-xmldata-and-xmlschema-options"></a><span data-ttu-id="bb854-102">Exemplo: Solicitando esquemas como resultados com as opções XMLDATA e XMLSCHEMA</span><span class="sxs-lookup"><span data-stu-id="bb854-102">Example: Requesting Schemas as Results with the XMLDATA and XMLSCHEMA Options</span></span>
  <span data-ttu-id="bb854-103">A consulta a seguir retorna o esquema XML-DATA que descreve a estrutura do documento.</span><span class="sxs-lookup"><span data-stu-id="bb854-103">The following query returns the XML-DATA schema that describes the document structure.</span></span>  
  
## <a name="example"></a><span data-ttu-id="bb854-104">Exemplo</span><span class="sxs-lookup"><span data-stu-id="bb854-104">Example</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, XMLDATA  
GO  
```  
  
 <span data-ttu-id="bb854-105">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="bb854-105">This is the result:</span></span>  
  
```  
<Schema name="Schema1" xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:datatypes">  
  <ElementType name="row" content="empty" model="closed">  
    <AttributeType name="ProductModelID" dt:type="i4" />  
    <AttributeType name="Name" dt:type="string" />  
    <attribute type="ProductModelID" />  
    <attribute type="Name" />  
  </ElementType>  
</Schema>  
<row xmlns="x-schema:#Schema1" ProductModelID="122" Name="All-Purpose Bike Stand" />  
<row xmlns="x-schema:#Schema1" ProductModelID="119" Name="Bike Wash" />  
```  
  
> [!NOTE]
>  <span data-ttu-id="bb854-106">O <`Schema`> é declarado como um namespace.</span><span class="sxs-lookup"><span data-stu-id="bb854-106">The <`Schema`> is declared as a namespace.</span></span> <span data-ttu-id="bb854-107">Para evitar colisões de namespace quando vários esquemas XML-Data são solicitados em diferentes consultas FOR XML, o identificador do namespace, `Schema1` neste exemplo, é alterado a cada execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="bb854-107">To avoid namespace collisions when multiple XML-Data schemas are requested in different FOR XML queries, the namespace identifier, `Schema1` in this example, changes with every query execution.</span></span> <span data-ttu-id="bb854-108">O identificador de namespace é composto de **Schema_n_** onde **_n_** é um inteiro.</span><span class="sxs-lookup"><span data-stu-id="bb854-108">The namespace identifier is made up of **Schema_n_** where **_n_** is an integer.</span></span>  
  
 <span data-ttu-id="bb854-109">Com a especificação da opção `XMLSCHEMA` , é possível solicitar o esquema XSD para o resultado.</span><span class="sxs-lookup"><span data-stu-id="bb854-109">By specifying the `XMLSCHEMA` option, you can request the XSD schema for the result.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, XMLSCHEMA  
GO  
```  
  
 <span data-ttu-id="bb854-110">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="bb854-110">This is the result:</span></span>  
  
```  
<xsd:schema targetNamespace="urn:schemas-microsoft-com:sql:SqlRowSet1" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="row">  
    <xsd:complexType>  
      <xsd:attribute name="ProductModelID" type="sqltypes:int" use="required" />  
      <xsd:attribute name="Name" use="required">  
        <xsd:simpleType sqltypes:sqlTypeAlias="[AdventureWorks].[dbo].[Name]">  
          <xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033" sqltypes:sqlCompareOptions="IgnoreCase IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">  
            <xsd:maxLength value="50" />  
          </xsd:restriction>  
        </xsd:simpleType>  
      </xsd:attribute>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" ProductModelID="122" Name="All-Purpose Bike Stand" />  
<row xmlns="urn:schemas-microsoft-com:sql:SqlRowSet1" ProductModelID="119" Name="Bike Wash" />  
  
```  
  
 <span data-ttu-id="bb854-111">É possível especificar o URI do namespace de destino como um argumento opcional para XMLSCHEMA em FOR XML.</span><span class="sxs-lookup"><span data-stu-id="bb854-111">You can specify the target namespace URI as an optional argument to XMLSCHEMA in FOR XML.</span></span> <span data-ttu-id="bb854-112">Isso retorna o namespace de destino especificado no esquema.</span><span class="sxs-lookup"><span data-stu-id="bb854-112">This returns the specified target namespace in the schema.</span></span> <span data-ttu-id="bb854-113">Esse namespace de destino permanece o mesmo sempre que você executa a consulta.</span><span class="sxs-lookup"><span data-stu-id="bb854-113">This target namespace remains the same every time you execute the query.</span></span> <span data-ttu-id="bb854-114">Por exemplo, a seguinte versão modificada da consulta anterior inclui o URI do namespace, `'urn:example.com'`, como um argumento.</span><span class="sxs-lookup"><span data-stu-id="bb854-114">For example, the following modified version of the previous query includes the namespace URI, `'urn:example.com'`, as an argument.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT ProductModelID, Name  
FROM Production.ProductModel  
WHERE ProductModelID=122 or ProductModelID=119  
FOR XML RAW, XMLSCHEMA ('urn:example.com')  
GO  
```  
  
 <span data-ttu-id="bb854-115">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="bb854-115">This is the result:</span></span>  
  
```  
<xsd:schema targetNamespace="urn:example.com" xmlns:xsd="http://www.w3.org/2001/XMLSchema" xmlns:sqltypes="https://schemas.microsoft.com/sqlserver/2004/sqltypes" elementFormDefault="qualified">  
  <xsd:import namespace="https://schemas.microsoft.com/sqlserver/2004/sqltypes" schemaLocation="https://schemas.microsoft.com/sqlserver/2004/sqltypes/sqltypes.xsd" />  
  <xsd:element name="row">  
    <xsd:complexType>  
      <xsd:attribute name="ProductModelID" type="sqltypes:int" use="required" />  
      <xsd:attribute name="Name" use="required">  
        <xsd:simpleType sqltypes:sqlTypeAlias="[AdventureWorks].[dbo].[Name]">  
          <xsd:restriction base="sqltypes:nvarchar" sqltypes:localeId="1033" sqltypes:sqlCompareOptions="IgnoreCase IgnoreKanaType IgnoreWidth" sqltypes:sqlSortId="52">  
            <xsd:maxLength value="50" />  
          </xsd:restriction>  
        </xsd:simpleType>  
      </xsd:attribute>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
<row xmlns="urn:example.com" ProductModelID="122" Name="All-Purpose Bike Stand" />  
<row xmlns="urn:example.com" ProductModelID="119" Name="Bike Wash" />  
```  
  
## <a name="see-also"></a><span data-ttu-id="bb854-116">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bb854-116">See Also</span></span>  
 [<span data-ttu-id="bb854-117">Usar o modo RAW com FOR XML</span><span class="sxs-lookup"><span data-stu-id="bb854-117">Use RAW Mode with FOR XML</span></span>](use-raw-mode-with-for-xml.md)  
  
  
