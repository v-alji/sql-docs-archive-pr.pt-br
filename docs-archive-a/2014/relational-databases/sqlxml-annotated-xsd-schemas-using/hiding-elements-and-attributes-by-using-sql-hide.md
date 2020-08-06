---
title: 'Ocultando elementos e atributos usando SQL: Hide | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- hiding elements
- element mapping [SQLXML], hiding attributes and elements
- hide annotation
- sql:hide
- table/view mapping [SQLXML], hiding attributes and elements
- table mapping [SQLXML], hiding attributes and elements
- hiding attributes
- annotated XSD schemas, hiding attributes and elements
- attribute mapping [SQLXML], hiding attributes and elements
- column mapping [SQLXML]
- element hiding [SQLXML]
- XSD schemas [SQLXML], hiding attributes and elements
- attribute hiding [SQLXML]
ms.assetid: 0978301b-f068-46b6-82b9-dc555161f52e
author: rothja
ms.author: jroth
ms.openlocfilehash: 5a3beb48be1d9809b170faeafa964ba45156ac28
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685481"
---
# <a name="hiding-elements-and-attributes-by-using-sqlhide"></a><span data-ttu-id="d29e3-102">Ocultando elementos e atributos usando sql:hide</span><span class="sxs-lookup"><span data-stu-id="d29e3-102">Hiding Elements and Attributes by Using sql:hide</span></span>
  <span data-ttu-id="d29e3-103">Quando uma consulta XPath é executada em um esquema XSD, o documento XML resultante tem elementos e atributos especificados no esquema.</span><span class="sxs-lookup"><span data-stu-id="d29e3-103">When an XPath query is executed against an XSD schema, the resulting XML document has elements and attributes that are specified in the schema.</span></span> <span data-ttu-id="d29e3-104">É possível especificar que alguns elementos e atributos permaneçam ocultos no esquema usando a anotação `sql:hide`.</span><span class="sxs-lookup"><span data-stu-id="d29e3-104">You can specify that some elements and attributes be hidden in the schema by using the `sql:hide` annotation.</span></span> <span data-ttu-id="d29e3-105">Isso é útil quando os critérios de seleção da consulta exigem a presença de elementos ou atributos específicos no esquema, mas você não deseja que eles retornem no documento XML gerado.</span><span class="sxs-lookup"><span data-stu-id="d29e3-105">This is useful when the selection criteria of the query require particular elements or attributes in the schema, but you do not want them returned in the XML document that is generated.</span></span>  
  
 <span data-ttu-id="d29e3-106">A anotação `sql:hide` usa um valor booliano (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="d29e3-106">The `sql:hide` annotation takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="d29e3-107">Os valores aceitáveis são 0, 1, true e false.</span><span class="sxs-lookup"><span data-stu-id="d29e3-107">The acceptable values are 0, 1, true, and false.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d29e3-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d29e3-108">Examples</span></span>  
 <span data-ttu-id="d29e3-109">Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="d29e3-109">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="d29e3-110">Para obter mais informações, consulte [Requirements for running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="d29e3-110">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlhide-on-an-attribute"></a><span data-ttu-id="d29e3-111">a.</span><span class="sxs-lookup"><span data-stu-id="d29e3-111">A.</span></span> <span data-ttu-id="d29e3-112">Especificando sql:hide em um atributo</span><span class="sxs-lookup"><span data-stu-id="d29e3-112">Specifying sql:hide on an attribute</span></span>  
 <span data-ttu-id="d29e3-113">O esquema XSD neste exemplo consiste em um **\<Person.Contact>** elemento com atributos **ContactID**, **FirstName**e **LastName** .</span><span class="sxs-lookup"><span data-stu-id="d29e3-113">The XSD schema in this example consists of an **\<Person.Contact>** element with **ContactID**, **FirstName**, and **LastName** attributes.</span></span>  
  
 <span data-ttu-id="d29e3-114">O **\<Person.Contact>** elemento é de tipo complexo e, portanto, é mapeado para a tabela de mesmo nome (mapeamento padrão).</span><span class="sxs-lookup"><span data-stu-id="d29e3-114">The **\<Person.Contact>** element is of complex type and, therefore, maps to the table of the same name (default mapping).</span></span> <span data-ttu-id="d29e3-115">Todos os atributos do **\<Person.Contact>** elemento são de tipo simples e são mapeados para colunas com os mesmos nomes em Person. contacttable no banco de dados AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d29e3-115">All the attributes of **\<Person.Contact>** element are of simple type and map to columns with the same names in the Person.Contacttable in the AdventureWorks database.</span></span> <span data-ttu-id="d29e3-116">No esquema, a `sql:hide` anotação é especificada no atributo **ContactID** .</span><span class="sxs-lookup"><span data-stu-id="d29e3-116">In the schema, the `sql:hide` annotation is specified on the **ContactID** attribute.</span></span> <span data-ttu-id="d29e3-117">Quando uma consulta XPath é especificada nesse esquema, o **ContactID** não é retornado no documento XML.</span><span class="sxs-lookup"><span data-stu-id="d29e3-117">When an XPath query is specified against this schema, the **ContactID** is not returned in the XML document.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID"  sql:hide="true" />   
       <xsd:attribute name="FirstName"   type="xsd:string" />   
       <xsd:attribute name="LastName"    type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="d29e3-118">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="d29e3-118">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="d29e3-119">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d29e3-119">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="d29e3-120">Salve o arquivo como Hide.xml.</span><span class="sxs-lookup"><span data-stu-id="d29e3-120">Save the file as Hide.xml.</span></span>  
  
2.  <span data-ttu-id="d29e3-121">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="d29e3-121">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="d29e3-122">Salve o arquivo como HideT.xml no mesmo diretório onde você salvou Hide.xml.</span><span class="sxs-lookup"><span data-stu-id="d29e3-122">Save the file as HideT.xml in the same directory where you saved Hide.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="Hide.xml">  
            /Person.Contact[@ContactID="1"]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="d29e3-123">O caminho de diretório especificado para o esquema de mapeamento (Hide.xml) é relativo ao diretório onde o modelo está salvo.</span><span class="sxs-lookup"><span data-stu-id="d29e3-123">The directory path specified for the mapping schema (Hide.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="d29e3-124">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d29e3-124">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\Hide.xml"  
    ```  
  
3.  <span data-ttu-id="d29e3-125">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="d29e3-125">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="d29e3-126">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="d29e3-126">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="d29e3-127">Este é o conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="d29e3-127">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <Person.Contact FirstName="Gustavo" LastName="Achong" />   
</ROOT>  
```  
  
 <span data-ttu-id="d29e3-128">Quando `sql:hide` é especificado em um elemento, este e seus atributos ou elementos filho não são exibidos no documento XML gerado.</span><span class="sxs-lookup"><span data-stu-id="d29e3-128">When `sql:hide` is specified on an element, the element and its attributes or child elements do not appear in the XML document that is generated.</span></span> <span data-ttu-id="d29e3-129">Aqui está outro esquema XSD no que `sql:hide` é especificado no **\<OD>** elemento:</span><span class="sxs-lookup"><span data-stu-id="d29e3-129">Here is another XSD schema in which `sql:hide` is specified on the **\<OD>** element:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:dt="urn:schemas-microsoft-com:datatypes"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:annotation>  
    <xsd:documentation>  
      Sales.Customer-Sales.SalesOrderHeader-Sales.SalesOrderDetail Schema  
      Copyright 2004 Microsoft. All rights reserved.  
    </xsd:documentation>  
    <xsd:appinfo>  
      <sql:relationship name="CustomerOrder"  
         parent="Sales.Customer"  
                  parent-key="CustomerID"  
                  child-key="CustomerID"  
                  child="Sales.SalesOrderHeader" />  
       <sql:relationship name="OrderOrderDetails"  
                  parent="Sales.SalesOrderHeader"  
                  parent-key="SalesOrderID"  
                  child-key="SalesOrderID"  
                  child="Sales.SalesOrderDetail"/>  
    </xsd:appinfo>  
  </xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Sales.Customer">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"   
                     maxOccurs="unbounded"   
                     sql:relationship="CustomerOrder">  
          <xsd:complexType>  
            <xsd:sequence>  
               <xsd:element name="OD" sql:relation="Sales.SalesOrderDetail"                                       maxOccurs="unbounded"                                       sql:relationship="OrderOrderDetails"                                       sql:hide="1">  
                  <xsd:complexType>  
                    <xsd:attribute name="SalesOrderID" type="xsd:string"/>  
                    <xsd:attribute name="ProductID" type="xsd:string"/>  
                  </xsd:complexType>  
               </xsd:element>  
            </xsd:sequence>  
          <xsd:attribute name="CustomerID" type="xsd:string"/>  
          <xsd:attribute name="OID" sql:field="SalesOrderID"   
                                    type="xsd:string"/>  
          <xsd:attribute name="OrderDate" type="xsd:date"/>   
        </xsd:complexType>  
      </xsd:element>  
    </xsd:sequence>  
    <xsd:attribute name="CID" sql:field="CustomerID"   
                                type="xsd:string"/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="d29e3-130">Quando uma consulta XPath (por exemplo `/Customers[@CID="1"]` ) é especificada nesse esquema, o documento XML gerado não inclui o **\<OD>** elemento e seus filhos, conforme mostrado neste resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="d29e3-130">When an XPath query (for example `/Customers[@CID="1"]`) is specified against this schema, the XML document that is generated does not include the **\<OD>** element and its children, as shown in this partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customers CID="1">  
    <Order CustomerID="1" OID="43860" OrderDate="2001-08-01" />   
    <Order CustomerID="1" OID="44501" OrderDate="2001-11-01" />   
    <Order CustomerID="1" OID="45283" OrderDate="2002-02-01" />   
    <Order CustomerID="1" OID="46042" OrderDate="2002-05-01" />   
  </Customers>  
</ROOT>  
```  
  
  
