---
title: Usando esquemas XSD anotados em consultas (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- queries [SQLXML]
- inline schemas [SQLXML]
- XPath queries [SQLXML], annotated XSD schemas in queries
- queries [SQLXML], annotated XSD schemas
- retrieving data
- mapping schema [SQLXML], queries
- multiple inline schemas
- annotated XSD schemas, queries
- XSD schemas [SQLXML], queries
- templates [SQLXML], annotated XSD schemas in queries
ms.assetid: 927a30a2-eae8-420d-851d-551c5f884f3c
author: rothja
ms.author: jroth
ms.openlocfilehash: c3038ea234f707da7a87a030cb4110510f5a77c8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575727"
---
# <a name="using-annotated-xsd-schemas-in-queries-sqlxml-40"></a><span data-ttu-id="b381c-102">Usando esquemas XSD anotados em consultas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="b381c-102">Using Annotated XSD Schemas in Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="b381c-103">Você pode especificar consultas com relação a um esquema anotado para recuperar dados do banco de dados especificando consultas XPath em um modelo com relação ao esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="b381c-103">You can specify queries against an annotated schema to retrieve data from the database by specifying XPath queries in a template against the XSD schema.</span></span>  
  
 <span data-ttu-id="b381c-104">O **\<sql:xpath-query>** elemento permite que você especifique uma consulta XPath em relação ao modo de exibição XML definido pelo esquema anotado.</span><span class="sxs-lookup"><span data-stu-id="b381c-104">The **\<sql:xpath-query>** element allows you to specify an XPath query against the XML view that is defined by the annotated schema.</span></span> <span data-ttu-id="b381c-105">O esquema anotado no qual a consulta XPath deve ser executada é identificada usando o `mapping-schema` atributo do **\<sql:xpath-query>** elemento.</span><span class="sxs-lookup"><span data-stu-id="b381c-105">The annotated schema against which the XPath query is to be executed is identified by using the `mapping-schema` attribute of the **\<sql:xpath-query>** element.</span></span>  
  
 <span data-ttu-id="b381c-106">Os modelos são documentos XML válidos que contêm uma ou mais consultas.</span><span class="sxs-lookup"><span data-stu-id="b381c-106">Templates are valid XML documents that contain one or more queries.</span></span> <span data-ttu-id="b381c-107">As consultas FOR XML e XPath retornam um fragmento de documento.</span><span class="sxs-lookup"><span data-stu-id="b381c-107">The FOR XML and XPath queries return a document fragment.</span></span> <span data-ttu-id="b381c-108">Os modelos atuam como contêineres dos fragmentos de documento; os modelos oferecem uma maneira de especificar um único elemento de nível superior.</span><span class="sxs-lookup"><span data-stu-id="b381c-108">Templates act as containers for the document fragments; templates thus provide a way to specify a single, top-level element.</span></span>  
  
 <span data-ttu-id="b381c-109">Os exemplos deste tópico usam modelos para especificar uma consulta XPath com relação a um esquema anotado para recuperar dados do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b381c-109">The examples in this topic use templates to specify an XPath query against an annotated schema to retrieve data from the database.</span></span>  
  
 <span data-ttu-id="b381c-110">Por exemplo, considere este esquema anotado:</span><span class="sxs-lookup"><span data-stu-id="b381c-110">For example, consider this annotated schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Person.Contact" >  
     <xsd:complexType>  
       <xsd:attribute name="ContactID" type="xsd:string" />   
       <xsd:attribute name="FirstName" type="xsd:string" />   
       <xsd:attribute name="LastName"  type="xsd:string" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="b381c-111">Para fins de ilustração, este esquema XSD é armazenado em arquivo nomeado Schema2.xml.</span><span class="sxs-lookup"><span data-stu-id="b381c-111">For the purpose of illustration, this XSD schema is stored in file named Schema2.xml.</span></span> <span data-ttu-id="b381c-112">Você poderá ter uma consulta XPath com relação ao esquema anotado especificado no seguinte arquivo de modelo (Schema2T.xml):</span><span class="sxs-lookup"><span data-stu-id="b381c-112">You could then have an XPath query against the annotated schema specified in the following template file (Schema2T.xml):</span></span>  
  
```  
<sql:xpath-query   
     xmlns:sql="urn:schemas-microsoft-com:xmlsql"  
     >  
          Person.Contact[@ContactID="1"]  
</sql:xpath-query>  
```  
  
 <span data-ttu-id="b381c-113">Em seguida, você poderá criar e usar o Script de Teste SQLXML 4.0 (Sqlxml4test.vbs) para executar a consulta como parte de um arquivo de modelo.</span><span class="sxs-lookup"><span data-stu-id="b381c-113">You can then create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the query as part of a template file.</span></span> <span data-ttu-id="b381c-114">Para obter mais informações, consulte [esquemas XDR anotados &#40;preteridos no SQLXML 4,0&#41;](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="b381c-114">For more information, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="using-inline-mapping-schemas"></a><span data-ttu-id="b381c-115">Usando esquemas de mapeamento embutidos</span><span class="sxs-lookup"><span data-stu-id="b381c-115">Using Inline Mapping Schemas</span></span>  
 <span data-ttu-id="b381c-116">Um esquema anotado pode ser incluído diretamente em um modelo e, em seguida, uma consulta XPath pode ser especificada no modelo com relação ao esquema embutido.</span><span class="sxs-lookup"><span data-stu-id="b381c-116">An annotated schema can be included directly in a template, and then an XPath query can be specified in the template against the inline schema.</span></span> <span data-ttu-id="b381c-117">O modelo pode também ser um diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="b381c-117">The template can also be an updategram.</span></span>  
  
 <span data-ttu-id="b381c-118">Um modelo pode incluir vários esquemas embutidos.</span><span class="sxs-lookup"><span data-stu-id="b381c-118">A template can include multiple inline schemas.</span></span> <span data-ttu-id="b381c-119">Para usar um esquema embutido que está incluído em um modelo, especifique o atributo **ID** com um valor exclusivo no **\<xsd:schema>** elemento e, em seguida, use **#idvalue** para fazer referência ao esquema embutido.</span><span class="sxs-lookup"><span data-stu-id="b381c-119">To use an inline schema that is included in a template, specify the **id** attribute with a unique value on the **\<xsd:schema>** element, and then use **#idvalue** to reference the inline schema.</span></span> <span data-ttu-id="b381c-120">O atributo **ID** é idêntico em comportamento para o **SQL: ID** ({urn: schemas-microsoft-com: XML-SQL} ID) usado em esquemas XDR.</span><span class="sxs-lookup"><span data-stu-id="b381c-120">The **id** attribute is identical in behavior to the **sql:id** ({urn:schemas-microsoft-com:xml-sql}id) used in XDR schemas.</span></span>  
  
 <span data-ttu-id="b381c-121">Por exemplo, o seguinte modelo especifica dois esquemas anotados embutidos:</span><span class="sxs-lookup"><span data-stu-id="b381c-121">For example, the following template specifies two inline-annotated schemas:</span></span>  
  
```  
<ROOT xmlns:sql='urn:schemas-microsoft-com:xml-sql'>  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
        xmlns:ms='urn:schemas-microsoft-com:mapping-schema'  
        id='InLineSchema1' sql:is-mapping-schema='1'>  
  <xsd:element name='Employees' ms:relation='HumanResources.Employee'>  
    <xsd:complexType>  
      <xsd:attribute name='LoginID'   
                     type='xsd:string'/>  
      <xsd:attribute name='Title'   
                     type='xsd:string'/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
  
<xsd:schema xmlns:xsd='http://www.w3.org/2001/XMLSchema'  
        xmlns:ms='urn:schemas-microsoft-com:mapping-schema'  
        id='InLineSchema2' sql:is-mapping-schema='1'>  
  <xsd:element name='Contacts' ms:relation='Person.Contact'>  
    <xsd:complexType>  
  
      <xsd:attribute name='ContactID'   
                     type='xsd:string' />  
      <xsd:attribute name='FirstName'   
                     type='xsd:string' />  
      <xsd:attribute name='LastName'   
                     type='xsd:string' />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
  
<sql:xpath-query xmlns:sql='urn:schemas-microsoft-com:xml-sql'   
        mapping-schema='#InLineSchema1'>  
    /Employees[@LoginID='adventure-works\guy1']  
</sql:xpath-query>  
  
<sql:xpath-query xmlns:sql='urn:schemas-microsoft-com:xml-sql'   
        mapping-schema='#InLineSchema2'>  
    /Contacts[@ContactID='1']  
</sql:xpath-query>  
</ROOT>  
```  
  
 <span data-ttu-id="b381c-122">O modelo também especifica duas consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="b381c-122">The template also specifies two XPath queries.</span></span> <span data-ttu-id="b381c-123">Cada um dos **\<xpath-query>** elementos identifica exclusivamente o esquema de mapeamento especificando o `mapping-schema` atributo.</span><span class="sxs-lookup"><span data-stu-id="b381c-123">Each of the **\<xpath-query>** elements uniquely identifies the mapping schema by specifying the `mapping-schema` attribute.</span></span>  
  
 <span data-ttu-id="b381c-124">Quando você especifica um esquema embutido no modelo, a `sql:is-mapping-schema` Anotação também deve ser especificada no **\<xsd:schema>** elemento.</span><span class="sxs-lookup"><span data-stu-id="b381c-124">When you specify an inline schema in the template, the `sql:is-mapping-schema` annotation must also be specified on the **\<xsd:schema>** element.</span></span> <span data-ttu-id="b381c-125">A anotação `sql:is-mapping-schema` adota um valor Booleano (0=false, 1=true).</span><span class="sxs-lookup"><span data-stu-id="b381c-125">The `sql:is-mapping-schema` takes a Boolean value (0=false, 1=true).</span></span> <span data-ttu-id="b381c-126">Um esquema embutido com **SQL: is-Mapping-Schema = "1"** é tratado como esquema anotado embutido e não é retornado no documento XML.</span><span class="sxs-lookup"><span data-stu-id="b381c-126">An inline schema with **sql:is-mapping-schema="1"** is treated as inline annotated schema and is not returned in the XML document.</span></span>  
  
 <span data-ttu-id="b381c-127">A anotação `sql:is-mapping-schema` pertence ao namespace de modelo `urn:schemas-microsoft-com:xml-sql`.</span><span class="sxs-lookup"><span data-stu-id="b381c-127">The `sql:is-mapping-schema` annotation belongs to the template namespace `urn:schemas-microsoft-com:xml-sql`.</span></span>  
  
 <span data-ttu-id="b381c-128">Para testar este exemplo, salve o modelo (InlineSchemaTemplate.xml) em um diretório local e, em seguida, crie e use o Script de Teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="b381c-128">To test this example, save the template (InlineSchemaTemplate.xml) in a local directory and then create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span> <span data-ttu-id="b381c-129">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="b381c-129">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="b381c-130">Além de especificar o `mapping-schema` atributo no **\<sql:xpath-query>** elemento em um modelo (quando há uma consulta XPath) ou no **\<updg:sync>** elemento em um updategram, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="b381c-130">In addition to specifying the `mapping-schema` attribute on the **\<sql:xpath-query>** element in a template (when there is an XPath query), or on **\<updg:sync>** element in an updategram, you can do the following:</span></span>  
  
-   <span data-ttu-id="b381c-131">Especifique o `mapping-schema` atributo no **\<ROOT>** elemento (declaração global) no modelo.</span><span class="sxs-lookup"><span data-stu-id="b381c-131">Specify the `mapping-schema` attribute on the **\<ROOT>** element (global declaration) in the template.</span></span> <span data-ttu-id="b381c-132">Este esquema de mapeamento se torna o esquema padrão que será usado por todos os XPaths e nós de diagrama de atualização que não têm nenhuma anotação `mapping-schema` explícita.</span><span class="sxs-lookup"><span data-stu-id="b381c-132">This mapping schema then becomes the default schema that will be used by all XPath and updategram nodes that have no explicit `mapping-schema` annotation.</span></span>  
  
-   <span data-ttu-id="b381c-133">Especificar o atributo `mapping schema` usando o objeto `Command` do ADO.</span><span class="sxs-lookup"><span data-stu-id="b381c-133">Specify the `mapping schema` attribute by using the ADO `Command` object.</span></span>  
  
 <span data-ttu-id="b381c-134">O `mapping-schema` atributo especificado no **\<xpath-query>** **\<updg:sync>** elemento ou tem a precedência mais alta; o objeto ADO `Command` tem a precedência mais baixa.</span><span class="sxs-lookup"><span data-stu-id="b381c-134">The `mapping-schema` attribute that is specified on the **\<xpath-query>** or **\<updg:sync>** element has the highest precedence; the ADO `Command` object has the lowest precedence.</span></span>  
  
 <span data-ttu-id="b381c-135">Observe que, se você especificar uma consulta XPath em um modelo e não especificar um esquema de mapeamento no qual a consulta XPath é executada, a consulta XPath será tratada como uma consulta de tipo **dbobject** .</span><span class="sxs-lookup"><span data-stu-id="b381c-135">Note that if you specify an XPath query in a template and do not specify a mapping schema against which the XPath query is executed, the XPath query is treated as a **dbobject** type query.</span></span> <span data-ttu-id="b381c-136">Por exemplo, considere este modelo:</span><span class="sxs-lookup"><span data-stu-id="b381c-136">For example, consider this template:</span></span>  
  
```  
<sql:xpath-query   
     xmlns:sql="urn:schemas-microsoft-com:xmlsql">  
          Production.ProductPhoto[@ProductPhotoID='100']/@LargePhoto  
</sql:xpath-query>  
```  
  
 <span data-ttu-id="b381c-137">O modelo especifica uma consulta Xpath, mas não especifica um esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="b381c-137">The template specifies an XPath query but it does not specify a mapping schema.</span></span> <span data-ttu-id="b381c-138">Portanto, essa consulta é tratada como uma consulta de tipo **dbobject** em que Production. ProductPhoto é o nome da tabela e @ProductPhotoID = ' 100 ' é um predicado que localiza uma foto do produto com o valor de ID de 100.</span><span class="sxs-lookup"><span data-stu-id="b381c-138">Therefore, this query is treated as a **dbobject** type query in which Production.ProductPhoto is the table name and @ProductPhotoID='100' is a predicate that finds a product photo with the ID value of 100.</span></span> <span data-ttu-id="b381c-139">@LargePhotoé a coluna da qual recuperar o valor.</span><span class="sxs-lookup"><span data-stu-id="b381c-139">@LargePhoto is the column from which to retrieve the value.</span></span>  
  
  
