---
title: Mapeamento padrão de elementos e atributos XSD para tabelas e colunas (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XSD schemas [SQLXML], mapping attributes and elements
- mapping schema [SQLXML], default mapping
- element mapping [SQLXML], default mapping
- element mapping [SQLXML]
- table mapping [SQLXML]
- annotated XSD schemas, mapping attributes and elements
- table/view mapping [SQLXML]
- column mapping [SQLXML]
- attribute mapping [SQLXML], default mapping
- default schema mapping
- table mapping [SQLXML], default mapping
- testing XPath query against schema
- xml data type [SQL Server], SQLXML
- table/view mapping [SQLXML], default mapping
- element/attribute mapping [SQLXML]
ms.assetid: 9a18e92a-6cfb-4a14-993a-663a95aabb63
author: rothja
ms.author: jroth
ms.openlocfilehash: 0bccec2413e8a0a6e13283a0f3e5f63ab61e934b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573904"
---
# <a name="default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-40"></a><span data-ttu-id="52822-102">Mapeamento padrão de atributos e elementos XSD para tabelas e colunas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="52822-102">Default Mapping of XSD Elements and Attributes to Tables and Columns (SQLXML 4.0)</span></span>
  <span data-ttu-id="52822-103">Por padrão, um elemento de tipo complexo em um esquema XSD anotado é mapeado para a tabela (exibição) com o mesmo nome no banco de dados especificado, e um elemento ou atributo de tipo simples é mapeado para a coluna com o mesmo nome na tabela.</span><span class="sxs-lookup"><span data-stu-id="52822-103">By default, an element of complex type in an XSD annotated schema maps to the table (view) with the same name in the specified database, and an element or attribute of simple type maps to the column with the same name in the table.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="52822-104">Exemplos</span><span class="sxs-lookup"><span data-stu-id="52822-104">Examples</span></span>  
 <span data-ttu-id="52822-105">Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="52822-105">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="52822-106">Para obter mais informações, consulte [Requirements for running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="52822-106">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-default-mapping"></a><span data-ttu-id="52822-107">a.</span><span class="sxs-lookup"><span data-stu-id="52822-107">A.</span></span> <span data-ttu-id="52822-108">Especificando o mapeamento padrão</span><span class="sxs-lookup"><span data-stu-id="52822-108">Specifying default mapping</span></span>  
 <span data-ttu-id="52822-109">Neste exemplo, nenhuma anotação é especificada no esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="52822-109">In this example, no annotations are specified in the XSD schema.</span></span> <span data-ttu-id="52822-110">O **\<Person.Contact>** elemento é de tipo complexo e, portanto, é mapeado por padrão para a tabela Person. Contact no banco de dados AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="52822-110">The **\<Person.Contact>** element is of complex type and, therefore, maps by default to the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="52822-111">Todos os atributos (ContactID, FirstName, LastName) do **\<Person.Contact>** elemento são de tipo simples e são mapeados por padrão para colunas com os mesmos nomes na tabela Person. Contact.</span><span class="sxs-lookup"><span data-stu-id="52822-111">All the attributes (ContactID, FirstName, LastName) of the **\<Person.Contact>** element are of simple type and map by default to columns with the same names in the Person.Contact table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID"  type="xsd:string" />   
       <xsd:attribute name="FirstName"   type="xsd:string" />   
       <xsd:attribute name="LastName"    type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="52822-112">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="52822-112">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="52822-113">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="52822-113">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="52822-114">Salve o arquivo como MySchema.xml.</span><span class="sxs-lookup"><span data-stu-id="52822-114">Save the file as MySchema.xml.</span></span>  
  
2.  <span data-ttu-id="52822-115">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="52822-115">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="52822-116">Salve o arquivo como MySchemaT.xml no mesmo diretório em que você salvou MySchema.xml.</span><span class="sxs-lookup"><span data-stu-id="52822-116">Save the file as MySchemaT.xml in the same directory where you saved MySchema.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchema.xml">  
            /Person.Contact  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="52822-117">O caminho do diretório especificado para o esquema de mapeamento (MySchema.xml) é relativo ao diretório onde o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="52822-117">The directory path specified for the mapping schema (MySchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="52822-118">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="52822-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchema.xml"  
    ```  
  
3.  <span data-ttu-id="52822-119">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="52822-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="52822-120">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="52822-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="52822-121">Este é o conjunto de resultados parcial:</span><span class="sxs-lookup"><span data-stu-id="52822-121">Here is the partial result set:</span></span>  
  
```  
<?xml version="1.0" encoding="UTF-8" ?>  
<ROOT>  
  <Person.Contact ContactID="1" FirstName="Gustavo" LastName="Achong"/>  
  <Person.Contact ContactID="2" FirstName="Catherine" LastName="Abel"/>  
   ...  
</ROOT>  
```  
  
### <a name="b-mapping-an-xml-element-to-a-database-column"></a><span data-ttu-id="52822-122">B.</span><span class="sxs-lookup"><span data-stu-id="52822-122">B.</span></span> <span data-ttu-id="52822-123">Mapeando um elemento XML para uma coluna de banco de dados</span><span class="sxs-lookup"><span data-stu-id="52822-123">Mapping an XML element to a database column</span></span>  
 <span data-ttu-id="52822-124">Neste exemplo, o mapeamento padrão acontece também porque nenhuma anotação é usada.</span><span class="sxs-lookup"><span data-stu-id="52822-124">In this example, default mapping also takes place because no annotations are used.</span></span> <span data-ttu-id="52822-125">O **\<Person.Contact>** elemento é de tipo complexo e é mapeado para a tabela com o mesmo nome no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="52822-125">The **\<Person.Contact>** element is of complex type and maps to the table with the same name in the database.</span></span> <span data-ttu-id="52822-126">Os elementos **\<FirstName>** e **\<LastName>** e o atributo **EmployeeID** são de tipo simples e, portanto, são mapeados para as colunas com os mesmos nomes.</span><span class="sxs-lookup"><span data-stu-id="52822-126">The elements **\<FirstName>** and **\<LastName>** and the **EmployeeID** attribute are of simple type and, therefore, map to the columns with the same names.</span></span> <span data-ttu-id="52822-127">A única diferença entre isto e o exemplo anterior é que os elementos são usados para mapear os campos FirstName e LastName.</span><span class="sxs-lookup"><span data-stu-id="52822-127">The only difference between this and the previous example are that elements are used for mapping the FirstName and LastName fields.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="FirstName" type="xsd:string" />   
        <xsd:element name="LastName" type="xsd:string" />   
      </xsd:sequence>  
      <xsd:attribute name="ContactID" type="xsd:integer" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="52822-128">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="52822-128">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="52822-129">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="52822-129">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="52822-130">Salve o arquivo como MySchemaElements.xml.</span><span class="sxs-lookup"><span data-stu-id="52822-130">Save the file as MySchemaElements.xml.</span></span>  
  
2.  <span data-ttu-id="52822-131">Crie o modelo a seguir (MySchemaElementsT.xml) e salve-o no mesmo diretório usado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="52822-131">Create the following template (MySchemaElementsT.xml), and save it in the same directory used in the previous step.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchemaElements.xml">  
            /Person.Contact  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="52822-132">O caminho de diretório especificado para o esquema de mapeamento é relativo ao diretório onde o modelo está salvo.</span><span class="sxs-lookup"><span data-stu-id="52822-132">The directory path specified for the mapping schema is relative to the directory where the template is saved.</span></span> <span data-ttu-id="52822-133">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="52822-133">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchemaElements.xml"  
    ```  
  
3.  <span data-ttu-id="52822-134">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="52822-134">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="52822-135">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="52822-135">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="52822-136">Este é o conjunto de resultados parcial:</span><span class="sxs-lookup"><span data-stu-id="52822-136">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact ContactID="1">  
    <FirstName>Gustavo</FirstName>  
    <LastName>Achong</LastName>  
  </Person.Contact>  
   ...  
</ROOT>  
```  
  
### <a name="c-mapping-an-xml-element-to-an-xml-data-type-column"></a><span data-ttu-id="52822-137">C.</span><span class="sxs-lookup"><span data-stu-id="52822-137">C.</span></span> <span data-ttu-id="52822-138">Mapeando um elemento XML para uma coluna de tipo de dados XML</span><span class="sxs-lookup"><span data-stu-id="52822-138">Mapping an XML element to an XML data type column</span></span>  
 <span data-ttu-id="52822-139">Neste exemplo, o mapeamento padrão acontece também porque nenhuma anotação é usada.</span><span class="sxs-lookup"><span data-stu-id="52822-139">In this example, default mapping also takes place because no annotations are used.</span></span> <span data-ttu-id="52822-140">O **\<Production.ProductModel>** elemento é de tipo complexo e é mapeado para a tabela com o mesmo nome no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="52822-140">The **\<Production.ProductModel>** element is of complex type and maps to the table with the same name in the database.</span></span> <span data-ttu-id="52822-141">O atributo **ProductModelID** é do tipo simples e, portanto, é mapeado para as colunas com os mesmos nomes.</span><span class="sxs-lookup"><span data-stu-id="52822-141">The **ProductModelID** attribute is of simple type and, therefore, map to the columns with the same names.</span></span> <span data-ttu-id="52822-142">A única diferença entre isso e os exemplos anteriores é que o **\<Instructions>** elemento está mapeando para uma coluna que usa o `xml` tipo de dados usando o `xsd:anyType` tipo.</span><span class="sxs-lookup"><span data-stu-id="52822-142">The only difference between this and the previous examples is that the **\<Instructions>** element is mapping to a column that uses the `xml` data type by using the `xsd:anyType` type.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Production.ProductModel">  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Instructions" type="xsd:anyType" />   
      </xsd:sequence>  
      <xsd:attribute name="ProductModelID" type="xsd:integer" />   
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="52822-143">O tipo de dados `xml` foi introduzido no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="52822-143">The `xml` data type was introduced in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)].</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="52822-144">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="52822-144">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="52822-145">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="52822-145">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="52822-146">Salve o arquivo como MySchemaXmlAnyElements.xml.</span><span class="sxs-lookup"><span data-stu-id="52822-146">Save the file as MySchemaXmlAnyElements.xml.</span></span>  
  
2.  <span data-ttu-id="52822-147">Crie o modelo a seguir (MySchemaXmlAnyElementsT.xml) e salve-o no mesmo diretório usado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="52822-147">Create the following template (MySchemaXmlAnyElementsT.xml), and save it in the same directory used in the previous step.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="MySchemaXmlAnyElements.xml">  
            /Production.ProductModel[@ProductModelID=7]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="52822-148">O caminho de diretório especificado para o esquema de mapeamento é relativo ao diretório onde o modelo está salvo.</span><span class="sxs-lookup"><span data-stu-id="52822-148">The directory path specified for the mapping schema is relative to the directory where the template is saved.</span></span> <span data-ttu-id="52822-149">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="52822-149">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchemaXmlAnyElements.xml"  
    ```  
  
3.  <span data-ttu-id="52822-150">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="52822-150">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="52822-151">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="52822-151">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="52822-152">Este é o conjunto de resultados parcial:</span><span class="sxs-lookup"><span data-stu-id="52822-152">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductModel ProductModelID="7">  
    <Instructions>  
      <root xmlns="http:  
//schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelManuInstru  
ctions">  
...  
      </root>  
    <Instructions>  
  </Production.ProductModel>  
</ROOT>  
```  
  
## <a name="see-also"></a><span data-ttu-id="52822-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="52822-153">See Also</span></span>  
 <span data-ttu-id="52822-154">[Considerações de segurança de esquema anotadas &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="52822-154">[Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="52822-155">[Dados XML &#40;SQL Server&#41;](../xml/xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="52822-155">[XML Data &#40;SQL Server&#41;](../xml/xml-data-sql-server.md) </span></span>  
 [<span data-ttu-id="52822-156">Suporte ao tipo de dados xml no SQLXML 4.0</span><span class="sxs-lookup"><span data-stu-id="52822-156">xml Data Type Support in SQLXML 4.0</span></span>](../sqlxml/xml-data-type-support-in-sqlxml-4-0.md)  
  
  
