---
title: 'Excluindo elementos de esquema do documento XML resultante usando SQL: mapeado (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- element does not map [SQLXML]
- annotated XSD schemas, excluding schema elements
- mapped annotation
- table mapping [SQLXML], excluding schema elements
- sql:mapped
- excluding schema elements
- element mapping [SQLXML], excluding schema elements
- column mapping [SQLXML]
- XSD schemas [SQLXML], excluding schema elements
- attribute mapping [SQLXML], excluding schema elements
- table/view mapping [SQLXML], excluding schema elements
ms.assetid: 7d2649dd-0038-4a2c-b16d-f80f7c306966
author: rothja
ms.author: jroth
ms.openlocfilehash: 1c79ae005b9630fcbfcd16bfc22c2aeb21b7bf9e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573905"
---
# <a name="excluding-schema-elements-from-the-resulting-xml-document-using-sqlmapped-sqlxml-40"></a><span data-ttu-id="c8fcf-102">Excluindo elementos de esquema do documento XML resultante usando sql:mapped (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="c8fcf-102">Excluding Schema Elements from the Resulting XML Document Using sql:mapped (SQLXML 4.0)</span></span>
  <span data-ttu-id="c8fcf-103">Todo elemento e atributo no esquema XSD é mapeado para uma tabela/exibição e uma coluna do banco de dados devido ao mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-103">Every element and attribute in the XSD schema maps to a database table/view and column because of the default mapping.</span></span> <span data-ttu-id="c8fcf-104">Se desejar criar um elemento no esquema XSD que não é mapeado para nenhuma tabela (exibição) ou coluna do banco de dados e que não aparece no XML, é possível especificar a anotação `sql:mapped`.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-104">If you want to create an element in the XSD schema that does not map to any database table (view) or column and that does not appear in the XML, you can specify the `sql:mapped` annotation.</span></span>  
  
 <span data-ttu-id="c8fcf-105">A anotação `sql:mapped` é especialmente útil quando o esquema não pode ser modificado ou quando o esquema é usado para validar XML de outras fontes e ainda contém dados que não estão armazenados em seu banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-105">The `sql:mapped` annotation is especially useful if the schema cannot be modified or if the schema is used to validate XML from other sources and yet contains data that is not stored in your database.</span></span> <span data-ttu-id="c8fcf-106">A anotação `sql:mapped` difere de `sql:is-constant` pois os elementos e atributos não mapeados não são exibidos no documento XML.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-106">The `sql:mapped` annotation differs from `sql:is-constant` in that the unmapped elements and attributes do not appear in the XML document.</span></span>  
  
 <span data-ttu-id="c8fcf-107">A anotação `sql:mapped` usa um valor Booliano (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="c8fcf-107">The `sql:mapped` annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="c8fcf-108">Os valores aceitáveis são 0, 1, true e false.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-108">The acceptable values are 0, 1, true, and false.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="c8fcf-109">Exemplos</span><span class="sxs-lookup"><span data-stu-id="c8fcf-109">Examples</span></span>  
 <span data-ttu-id="c8fcf-110">Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-110">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="c8fcf-111">Para obter mais informações, consulte [Requirements for running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="c8fcf-111">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlmapped-annotation"></a><span data-ttu-id="c8fcf-112">a.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-112">A.</span></span> <span data-ttu-id="c8fcf-113">Especificando a anotação sql:mapped</span><span class="sxs-lookup"><span data-stu-id="c8fcf-113">Specifying the sql:mapped annotation</span></span>  
 <span data-ttu-id="c8fcf-114">Suponha que você tenha um esquema XSD de alguma outra origem.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-114">Assume you have an XSD schema from some other source.</span></span> <span data-ttu-id="c8fcf-115">Esse esquema XSD consiste em um **\<Person.Contact>** elemento com os atributos **ContactID**, **FirstName**, **LastName**e **HomeAddress** .</span><span class="sxs-lookup"><span data-stu-id="c8fcf-115">This XSD schema consists of an **\<Person.Contact>** element with **ContactID**, **FirstName**, **LastName**, and **HomeAddress** attributes.</span></span>  
  
 <span data-ttu-id="c8fcf-116">No mapeamento deste esquema XSD para a tabela Person. Contact no banco de dados AdventureWorks, `sql:mapped` é especificado no atributo **HomeAddress** porque a tabela Employees não armazena os endereços residenciais dos funcionários.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-116">In mapping this XSD schema to the Person.Contact table in the AdventureWorks database, `sql:mapped` is specified on the **HomeAddress** attribute because the Employees table does not store the home addresses of employees.</span></span> <span data-ttu-id="c8fcf-117">Como resultado, este atributo não é mapeado para o banco de dados e não é retornado no documento XML resultante quando uma consulta XPath é especificada com relação ao esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-117">As a result, this attribute is not mapped to the database and is not returned in the resulting XML document when an XPath query is specified against the mapping schema.</span></span>  
  
 <span data-ttu-id="c8fcf-118">O mapeamento padrão é executado para o restante do esquema.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-118">Default mapping takes place for the rest of the schema.</span></span> <span data-ttu-id="c8fcf-119">O **\<Person.Contact>** elemento é mapeado para a tabela Person. Contact e todos os atributos são mapeados para as colunas com o mesmo nome na tabela Person. Contact.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-119">The **\<Person.Contact>** element maps to the Person.Contact table, and all the attributes map to the columns with the same name in the Person.Contact table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact">  
    <xsd:complexType>  
      <xsd:attribute name="ContactID"   type="xsd:string"/>  
      <xsd:attribute name="FirstName"    type="xsd:string" />  
      <xsd:attribute name="LastName"     type="xsd:string" />  
      <xsd:attribute name="HomeAddress" type="xsd:string"   
                     sql:mapped="false" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="c8fcf-120">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="c8fcf-120">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="c8fcf-121">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-121">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="c8fcf-122">Salve o arquivo como sql-mapped.xml.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-122">Save the file as sql-mapped.xml.</span></span>  
  
2.  <span data-ttu-id="c8fcf-123">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-123">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="c8fcf-124">Salve o arquivo como sql-mappedT.xml no mesmo diretório em que você salvou sql-mapped.xml.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-124">Save the file as sql-mappedT.xml in the same directory where you saved sql-mapped.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sql-mapped.xml">  
            /Person.Contact[@ContactID < 10]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="c8fcf-125">O caminho do diretório especificado para o esquema de mapeamento (MySchema.xml) é relativo ao diretório onde o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-125">The directory path specified for the mapping schema (MySchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="c8fcf-126">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="c8fcf-126">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\sql-mapped.xml"  
    ```  
  
3.  <span data-ttu-id="c8fcf-127">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-127">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="c8fcf-128">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c8fcf-128">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="c8fcf-129">Este é o conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="c8fcf-129">This is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact ContactID="1" FirstName="Gustavo" LastName="Achong" />   
  <Person.Contact ContactID="2" FirstName="Catherine" LastName="Abel" />   
  <Person.Contact ContactID="3" FirstName="Kim" LastName="Abercrombie" />   
  <Person.Contact ContactID="4" FirstName="Humberto" LastName="Acevedo" />   
  <Person.Contact ContactID="5" FirstName="Pilar" LastName="Ackerman" />   
  <Person.Contact ContactID="6" FirstName="Frances" LastName="Adams" />   
  <Person.Contact ContactID="7" FirstName="Margaret" LastName="Smith" />   
  <Person.Contact ContactID="8" FirstName="Carla" LastName="Adams" />   
  <Person.Contact ContactID="9" FirstName="Jay" LastName="Adams" />   
</ROOT>  
```  
  
 <span data-ttu-id="c8fcf-130">Observe que ContactID, FirstName e LastName estão presentes, mas HomeAddress não está, pois o esquema de mapeamento especificou 0 para o atributo `sql:mapped`.</span><span class="sxs-lookup"><span data-stu-id="c8fcf-130">Note that the ContactID, FirstName, and LastName are present, but HomeAddress is not because the mapping schema specified 0 for the `sql:mapped` attribute.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c8fcf-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c8fcf-131">See Also</span></span>  
 [<span data-ttu-id="c8fcf-132">Mapeamento padrão de elementos e atributos XSD para tabelas e colunas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="c8fcf-132">Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md)  
  
  
