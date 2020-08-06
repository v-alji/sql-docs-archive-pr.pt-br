---
title: Mapeamento explícito de elementos e atributos XSD para tabelas e colunas (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit schema mapping [SQLXML]
- XPath queries [SQLXML], annotated XSD schemas in queries
- sql:field
- row mapping [SQLXML]
- attribute mapping [SQLXML], explicit mapping
- field annotation
- XSD schemas [SQLXML], mapping attributes and elements
- names [SQLXML]
- relation annotation
- table/view mapping [SQLXML], explicit mapping
- sql:relation
- mapping schema [SQLXML], explicit mapping
- annotated XSD schemas, mapping attributes and elements
- column mapping [SQLXML]
- element mapping [SQLXML], explicit mapping
- table mapping [SQLXML], explicit mapping
- element/attribute mapping [SQLXML]
ms.assetid: 7a5ebeb6-7322-4141-a307-ebcf95976146
author: rothja
ms.author: jroth
ms.openlocfilehash: f3400682b5f28835ca039912aab058691929a6c3
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570556"
---
# <a name="explicit-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-40"></a><span data-ttu-id="665aa-102">Mapeamento explícito de atributos e elementos XSD em tabelas e colunas (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="665aa-102">Explicit Mapping of XSD Elements and Attributes to Tables and Columns (SQLXML 4.0)</span></span>
  <span data-ttu-id="665aa-103">Ao usar um esquema XSD para fornecer uma exibição XML do banco de dados relacional, os elementos e atributos do esquema devem ser mapeados em tabelas e colunas do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="665aa-103">When using an XSD schema to provide an XML view of the relational database , the elements and attributes of the schema must be mapped to tables and columns of the database.</span></span> <span data-ttu-id="665aa-104">As linhas na tabela/exibição do banco de dados serão mapeadas em elementos no documento XML.</span><span class="sxs-lookup"><span data-stu-id="665aa-104">The rows in the database table/view will map to elements in the XML document.</span></span> <span data-ttu-id="665aa-105">Os valores de coluna no banco de dados são mapeados em atributos ou elementos.</span><span class="sxs-lookup"><span data-stu-id="665aa-105">The column values in the database map to attributes or elements.</span></span>  
  
 <span data-ttu-id="665aa-106">Quando são especificadas consultas XPath com relação ao esquema XSD anotado, os dados dos elementos e atributos no esquema são recuperados das tabelas e colunas nas quais eles são mapeados.</span><span class="sxs-lookup"><span data-stu-id="665aa-106">When XPath queries are specified against the annotated XSD schema, the data for the elements and attributes in the schema is retrieved from the tables and columns to which they map.</span></span> <span data-ttu-id="665aa-107">Para obter um único valor do banco de dados, o mapeamento especificado no esquema XSD deve ter especificação de campo e relação.</span><span class="sxs-lookup"><span data-stu-id="665aa-107">To obtain a single value from the database, the mapping specified in the XSD schema must have both relation and field specification.</span></span> <span data-ttu-id="665aa-108">Se o nome de um elemento/atributo não for igual ao nome na tabela/exibição ou coluna na qual ele é mapeado, as anotações `sql:relation` e `sql:field` são usadas para especificar o mapeamento entre um elemento ou atributo em um documento XML e a tabela (exibição) ou coluna em um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="665aa-108">If the name of an element/attribute is not the same name as the table/view or column name to which it maps, the `sql:relation` and `sql:field` annotations are used to specify the mapping between an element or attribute in an XML document and the table (view) or column in a database.</span></span>  
  
## <a name="sql-relation"></a><span data-ttu-id="665aa-109">sql-relation</span><span class="sxs-lookup"><span data-stu-id="665aa-109">sql-relation</span></span>  
 <span data-ttu-id="665aa-110">A anotação `sql:relation` é adicionada para mapear um nó XML do esquema XSD em uma tabela do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="665aa-110">The `sql:relation` annotation is added to map an XML node in the XSD schema to a database table.</span></span> <span data-ttu-id="665aa-111">O nome de uma tabela (exibição) é especificado como o valor da anotação `sql:relation`.</span><span class="sxs-lookup"><span data-stu-id="665aa-111">The name of a table (view) is specified as the value of the `sql:relation` annotation.</span></span>  
  
 <span data-ttu-id="665aa-112">Quando `sql:relation` é especificado em um elemento, o escopo dessa anotação se aplica a todos os atributos e elementos filho que são descritos na definição de tipo complexo desse elemento, fornecendo assim um atalho ao escrever anotações.</span><span class="sxs-lookup"><span data-stu-id="665aa-112">When `sql:relation` is specified on an element, the scope of this annotation applies to all attributes and child elements that are described in the complex type definition of that element, therefore providing a shortcut in writing annotations.</span></span>  
  
 <span data-ttu-id="665aa-113">A `sql:relation` Anotação também é útil quando os identificadores válidos no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não são válidos em XML.</span><span class="sxs-lookup"><span data-stu-id="665aa-113">The `sql:relation` annotation is also useful when identifiers that are valid in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] are not valid in XML.</span></span> <span data-ttu-id="665aa-114">Por exemplo, "Pedido de Vendas" é um nome de tabela válido no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], mas não no XML.</span><span class="sxs-lookup"><span data-stu-id="665aa-114">For example, "Order Details" is a valid table name in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] but not in XML.</span></span> <span data-ttu-id="665aa-115">Nesses casos, a anotação `sql:relation` pode ser usada para especificar o mapeamento, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="665aa-115">In such cases, the `sql:relation` annotation can be used to specify the mapping, for example:</span></span>  
  
```  
<xsd:element name="OD" sql:relation="[Order Details]">  
```  
  
## <a name="sql-field"></a><span data-ttu-id="665aa-116">sql-field</span><span class="sxs-lookup"><span data-stu-id="665aa-116">sql-field</span></span>  
 <span data-ttu-id="665aa-117">A anotação `sql-field` mapeia um elemento ou atributo em uma coluna do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="665aa-117">The `sql-field` annotation maps an element or attribute to a database column.</span></span> <span data-ttu-id="665aa-118">A anotação `sql:field` é adicionada para mapear um nó XML do esquema em uma coluna do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="665aa-118">The `sql:field` annotation is added to map an XML node in the schema to a database column.</span></span> <span data-ttu-id="665aa-119">Não é possível especificar `sql:field` em um elemento com conteúdo vazio.</span><span class="sxs-lookup"><span data-stu-id="665aa-119">You cannot specify `sql:field` on an empty content element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="665aa-120">Exemplos</span><span class="sxs-lookup"><span data-stu-id="665aa-120">Examples</span></span>  
 <span data-ttu-id="665aa-121">Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="665aa-121">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="665aa-122">Para obter mais informações, consulte [Requirements for running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="665aa-122">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlrelation-and-sqlfield-annotations"></a><span data-ttu-id="665aa-123">a.</span><span class="sxs-lookup"><span data-stu-id="665aa-123">A.</span></span> <span data-ttu-id="665aa-124">Especificando as anotações sql:relation e sql:field</span><span class="sxs-lookup"><span data-stu-id="665aa-124">Specifying the sql:relation and sql:field annotations</span></span>  
 <span data-ttu-id="665aa-125">Neste exemplo, o esquema XSD consiste em um **\<Contact>** elemento de tipo complexo com **\<FName>** elementos filho e e **\<LName>** o atributo **ContactID** .</span><span class="sxs-lookup"><span data-stu-id="665aa-125">In this example, the XSD schema consists of an **\<Contact>** element of complex type with **\<FName>** and **\<LName>** child elements and the **ContactID** attribute.</span></span>  
  
 <span data-ttu-id="665aa-126">A `sql:relation` anotação mapeia o **\<Contact>** elemento para a tabela Person. Contact no banco de dados AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="665aa-126">The `sql:relation` annotation maps the **\<Contact>** element to the Person.Contact table in the AdventureWorks database.</span></span> <span data-ttu-id="665aa-127">A `sql:field` anotação mapeia o **\<FName>** elemento para a coluna FirstName e o **\<LName>** elemento para a coluna LastName.</span><span class="sxs-lookup"><span data-stu-id="665aa-127">The `sql:field` annotation maps the **\<FName>** element to the FirstName column and the **\<LName>** element to the LastName column.</span></span>  
  
 <span data-ttu-id="665aa-128">Nenhuma anotação foi especificada para o atributo **ContactID** .</span><span class="sxs-lookup"><span data-stu-id="665aa-128">No annotation is specified for the **ContactID** attribute.</span></span> <span data-ttu-id="665aa-129">Isso resulta em um mapeamento padrão do atributo na coluna com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="665aa-129">This results in a default mapping of the attribute to the column with the same name.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Contact" sql:relation="Person.Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"  
                     sql:field="FirstName"   
                     type="xsd:string" />   
        <xsd:element name="LName"    
                     sql:field="LastName"    
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ContactID"   
                       type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="665aa-130">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="665aa-130">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="665aa-131">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="665aa-131">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="665aa-132">Salve o arquivo como MySchema-annotated.xml.</span><span class="sxs-lookup"><span data-stu-id="665aa-132">Save the file as MySchema-annotated.xml.</span></span>  
  
2.  <span data-ttu-id="665aa-133">Copie o seguinte modelo abaixo e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="665aa-133">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="665aa-134">Salve o arquivo como MySchema-annotatedT.xml no mesmo diretório em que você salvou MySchema-annotated.xml.</span><span class="sxs-lookup"><span data-stu-id="665aa-134">Save the file as MySchema-annotatedT.xml in the same directory where you saved MySchema-annotated.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="MySchema-annotated.xml">  
        /Contact  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="665aa-135">O caminho do diretório especificado para o esquema de mapeamento (MySchema-annotated.xml) é relativo ao diretório no qual o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="665aa-135">The directory path specified for the mapping schema (MySchema-annotated.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="665aa-136">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="665aa-136">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\MySchema-annotated.xml"  
    ```  
  
3.  <span data-ttu-id="665aa-137">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="665aa-137">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="665aa-138">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="665aa-138">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="665aa-139">Este é o conjunto de resultados parcial:</span><span class="sxs-lookup"><span data-stu-id="665aa-139">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
 <Contact ContactID="1">   
    <FName>Gustavo</FName>   
    <LName>Achong</LName>   
 </Contact>   
  .....  
</ROOT>  
```  
  
  
