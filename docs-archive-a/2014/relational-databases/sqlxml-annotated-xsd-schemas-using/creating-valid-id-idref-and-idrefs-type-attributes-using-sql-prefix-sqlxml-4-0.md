---
title: 'Criando atributos de tipo ID, IDREF e IDREFS válidos usando SQL: prefix (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREFS relationships [SQLXML]
- annotated XSD schemas, ID type attribute
- IDREF type attribute [SQLXML]
- annotated XSD schemas, IDREFS type attribute
- ID type attribute [SQLXML]
- sql:prefix
- prefix annotation
- IDREF relationships [SQLXML]
- IDREFS type attribute [SQLXML]
- annotated XSD schemas, IDREF type attribute
- ID relationships [SQLXML]
ms.assetid: 1c7f77d3-81f3-4820-bb63-c4aaa4ea9aa1
author: rothja
ms.author: jroth
ms.openlocfilehash: cb9e63bebd0cebbfeed75ea5cbe2ea62683234fc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573906"
---
# <a name="creating-valid-id-idref-and-idrefs-type-attributes-using-sqlprefix-sqlxml-40"></a><span data-ttu-id="3a100-102">Criando atributos de tipo ID, IDREF e IDREFS válidos usando sql:prefix (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="3a100-102">Creating Valid ID, IDREF, and IDREFS Type Attributes Using sql:prefix (SQLXML 4.0)</span></span>
  <span data-ttu-id="3a100-103">Um atributo pode ser especificado como um atributo de tipo ID.</span><span class="sxs-lookup"><span data-stu-id="3a100-103">An attribute can be specified to be an ID type attribute.</span></span> <span data-ttu-id="3a100-104">Atributos especificados como IDREF ou IDREFS poderão, então, ser usados para fazer referência aos atributos de tipo ID, permitindo vínculos entre documentos.</span><span class="sxs-lookup"><span data-stu-id="3a100-104">Attributes specified as IDREF or IDREFS can then be used to refer to the ID type attributes, enabling links between documents.</span></span>  
  
 <span data-ttu-id="3a100-105">ID, IDREF e IDREFS correspondem a relações CP/FK (chave primária/chave estrangeira) no banco de dados, com poucas diferenças.</span><span class="sxs-lookup"><span data-stu-id="3a100-105">ID, IDREF, and IDREFS correspond to PK/FK (primary key/foreign key) relationships in the database, with few differences.</span></span> <span data-ttu-id="3a100-106">Em um documento XML, os valores de atributos de tipo ID devem ser distintos.</span><span class="sxs-lookup"><span data-stu-id="3a100-106">In an XML document, the values of ID type attributes must be distinct.</span></span> <span data-ttu-id="3a100-107">Se os atributos **CustomerID** e **OrderID** forem especificados como tipo de ID em um documento XML, esses valores deverão ser distintos.</span><span class="sxs-lookup"><span data-stu-id="3a100-107">If **CustomerID** and **OrderID** attributes are specified as ID type in an XML document, these values must be distinct.</span></span> <span data-ttu-id="3a100-108">No entanto, em um banco de dados, as colunas CustomerID e OrderID podem ter os mesmos valores.</span><span class="sxs-lookup"><span data-stu-id="3a100-108">However, in a database, CustomerID and OrderID columns can have the same values.</span></span> <span data-ttu-id="3a100-109">(Por exemplo, CustomerID = 1 e OrderID = 1 são válidos no banco de dados.)</span><span class="sxs-lookup"><span data-stu-id="3a100-109">(For example, CustomerID = 1 and OrderID = 1 are valid in the database).</span></span>  
  
 <span data-ttu-id="3a100-110">Para que os atributos ID, IDREF e IDREFS sejam válidos:</span><span class="sxs-lookup"><span data-stu-id="3a100-110">For the ID, IDREF, and IDREFS attributes to be valid:</span></span>  
  
-   <span data-ttu-id="3a100-111">O valor de ID deve ser exclusivo dentro do documento XML.</span><span class="sxs-lookup"><span data-stu-id="3a100-111">The value of ID must be unique within the XML document.</span></span>  
  
-   <span data-ttu-id="3a100-112">Para todos os atributos IDREF e IDREFS, os valores de ID referenciados devem estar no documento XML.</span><span class="sxs-lookup"><span data-stu-id="3a100-112">For every IDREF and IDREFS, the referenced ID values must be in the XML document.</span></span>  
  
-   <span data-ttu-id="3a100-113">O valor de um atributo ID, IDREF e IDREFS deve ser um token nomeado.</span><span class="sxs-lookup"><span data-stu-id="3a100-113">The value of an ID, IDREF, and IDREFS must be a named token.</span></span> <span data-ttu-id="3a100-114">(Por exemplo, o valor inteiro 101 não pode ser um valor de ID.)</span><span class="sxs-lookup"><span data-stu-id="3a100-114">(For example, the integer value 101 cannot be an ID value.)</span></span>  
  
-   <span data-ttu-id="3a100-115">Os atributos de tipo ID, IDREF e IDREFS não podem ser mapeados para colunas do tipo `text`, `ntext` ou `image`, nem para qualquer outro tipo de dados binários (por exemplo, `timestamp`).</span><span class="sxs-lookup"><span data-stu-id="3a100-115">The attributes of ID, IDREF, and IDREFS type cannot be mapped to columns of the type `text`, `ntext`, or `image` or any other binary data type (for example, `timestamp`).</span></span>  
  
 <span data-ttu-id="3a100-116">Se um documento XML contiver várias IDs, use a anotação `sql:prefix` para garantir que os valores sejam exclusivos.</span><span class="sxs-lookup"><span data-stu-id="3a100-116">If an XML document contains multiple IDs, use the `sql:prefix` annotation to ensure that the values are unique.</span></span>  
  
 <span data-ttu-id="3a100-117">Observe que a anotação `sql:prefix` não pode ser usada com atributo fixo XSD.</span><span class="sxs-lookup"><span data-stu-id="3a100-117">Note that `sql:prefix` annotation cannot be used with XSD fixed attribute.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="3a100-118">Exemplos</span><span class="sxs-lookup"><span data-stu-id="3a100-118">Examples</span></span>  
 <span data-ttu-id="3a100-119">Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="3a100-119">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="3a100-120">Para obter mais informações, consulte [Requirements for running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="3a100-120">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-id-and-idrefs-types"></a><span data-ttu-id="3a100-121">a.</span><span class="sxs-lookup"><span data-stu-id="3a100-121">A.</span></span> <span data-ttu-id="3a100-122">Especificando os tipos ID e IDREFS</span><span class="sxs-lookup"><span data-stu-id="3a100-122">Specifying ID and IDREFS types</span></span>  
 <span data-ttu-id="3a100-123">No esquema a seguir, o **\<Customer>** elemento consiste no **\<Order>** elemento filho.</span><span class="sxs-lookup"><span data-stu-id="3a100-123">In the following schema, the **\<Customer>** element consists of the **\<Order>** child element.</span></span> <span data-ttu-id="3a100-124">O **\<Order>** elemento também tem um elemento filho, o **\<OrderDetail>** elemento.</span><span class="sxs-lookup"><span data-stu-id="3a100-124">The **\<Order>** element also has a child element, the **\<OrderDetail>** element.</span></span>  
  
 <span data-ttu-id="3a100-125">O atributo **OrderIDList** de **\<Customer>** é um atributo de tipo IDREFS que se refere ao atributo **OrderID** do **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="3a100-125">The **OrderIDList** attribute of **\<Customer>** is an IDREFS type attribute that refers to the **OrderID** attribute of the **\<Order>** element.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
                 parent="Sales.Customer"  
                 parent-key="CustomerID"  
                 child="Sales.SalesOrderHeader"  
                 child-key="CustomerID" />  
    <sql:relationship name="OrderOrderDetail"  
                 parent="Sales.SalesOrderHeader"  
                 parent-key="SalesOrderID"  
                 child="Sales.SalesOrderDetail"  
                 child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"    
               sql:relationship="CustOrders" maxOccurs="unbounded" >  
          <xsd:complexType>  
              <xsd:sequence>  
                <xsd:element name="OrderDetail"   
                             sql:relation="Sales.SalesOrderDetail"   
                   sql:relationship="OrderOrderDetail"   
                   maxOccurs="unbounded" >  
                  <xsd:complexType>  
                   <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                   <xsd:attribute name="ProductID" type="xsd:string" />  
                   <xsd:attribute name="OrderQty" type="xsd:integer" />  
                  </xsd:complexType>  
               </xsd:element>  
             </xsd:sequence>  
             <xsd:attribute name="SalesOrderID"   
                            type="xsd:ID" sql:prefix="ord-" />  
             <xsd:attribute name="OrderDate" type="xsd:date" />  
             <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
      </xsd:element>  
    </xsd:sequence>  
    <xsd:attribute name="CustomerID" type="xsd:string" />  
    <xsd:attribute name="OrderIDList" type="xsd:IDREFS"   
                   sql:relation="Sales.SalesOrderHeader" sql:field="SalesOrderID"  
                   sql:relationship="CustOrders" sql:prefix="ord-">  
    </xsd:attribute>  
  </xsd:complexType>  
</xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="3a100-126">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="3a100-126">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="3a100-127">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="3a100-127">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="3a100-128">Salve o arquivo como sqlPrefix.xml.</span><span class="sxs-lookup"><span data-stu-id="3a100-128">Save the file as sqlPrefix.xml.</span></span>  
  
2.  <span data-ttu-id="3a100-129">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="3a100-129">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="3a100-130">Salve o arquivo como sqlPrefixT.xml no mesmo diretório onde você salvou sqlPrefix.xml.</span><span class="sxs-lookup"><span data-stu-id="3a100-130">Save the file as sqlPrefixT.xml in the same directory where you saved sqlPrefix.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="sqlPrefix.xml">  
        /Customer[@CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="3a100-131">O caminho de diretório especificado para o esquema de mapeamento (sqlPrefix.xml) é relativo ao diretório onde o modelo está salvo.</span><span class="sxs-lookup"><span data-stu-id="3a100-131">The directory path specified for the mapping schema (sqlPrefix.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="3a100-132">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="3a100-132">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\sqlPrefix.xml"  
    ```  
  
3.  <span data-ttu-id="3a100-133">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="3a100-133">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="3a100-134">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="3a100-134">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="3a100-135">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="3a100-135">This is the partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" OrderIDList="ord-43860 ord-44501 ord-45283 ord-46042">  
    <Order SalesOrderID="ord-43860" OrderDate="2001-08-01" CustomerID="1">  
      <OrderDetail SalesOrderID="43860" ProductID="729" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="732" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="738" OrderQty="1" />   
      <OrderDetail SalesOrderID="43860" ProductID="753" OrderQty="2" />   
      ...  
    </Order>  
    ...  
 </Customer>  
</ROOT>  
```  
  
  
