---
title: 'Criando seções CDATA usando SQL: use-cdata (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- markup characters [SQLXML]
- special characters [SQLXML]
- use-cdata annotation
- plain text [SQLXML]
- CDATA sections
- escaping blocks of text [SQLXML]
- annotated XSD schemas, CDATA sections
- sql:use-cdata
ms.assetid: 26d2b9dc-f857-44ff-bcd4-aaf64ff809d0
author: rothja
ms.author: jroth
ms.openlocfilehash: c0ba0787efbda400590a75f0f3529e3df8819e41
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582381"
---
# <a name="creating-cdata-sections-using-sqluse-cdata-sqlxml-40"></a><span data-ttu-id="e7dc5-102">Criando seções CDATA usando sql:use-cdata (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e7dc5-102">Creating CDATA Sections Using sql:use-cdata (SQLXML 4.0)</span></span>
  <span data-ttu-id="e7dc5-103">Em XML, as seções CDATA são usadas para sair de blocos de texto que contenham caracteres que seriam reconhecidos como caracteres de marcação.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-103">In XML, CDATA sections are used to escape blocks of text that contain characters that would otherwise be recognized as markup characters.</span></span>  
  
 <span data-ttu-id="e7dc5-104">Um banco de dados no Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] às vezes pode conter caracteres que são tratados como caracteres de marcação pelo analisador XML; por exemplo, colchetes angulares ( \< and > ), o símbolo de menor que ou-igual a (<=) e o e comercial (&) são tratados como caracteres de marcação.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-104">A database in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can sometimes contain characters that are treated as markup characters by the XML parser; for example, angle brackets (\< and >), the less-than-or-equal-to symbol (<=), and the ampersand (&) are treated as markup characters.</span></span> <span data-ttu-id="e7dc5-105">No entanto, é possível quebrar esse tipo de caracteres especiais em uma seção CDATA para impedi-los de serem tratados como caracteres de marcação.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-105">However, you can wrap this type of special characters in a CDATA section to prevent them from being treated as markup characters.</span></span> <span data-ttu-id="e7dc5-106">O texto na seção CDATA é tratado pelo analisador XML como texto sem-formatação.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-106">The text within the CDATA section is treated by the XML parser as plain text.</span></span>  
  
 <span data-ttu-id="e7dc5-107">A anotação `sql:use-cdata` é usada para especificar se os dados retornados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] devem ser colocados em uma seção CDATA (ou seja, ela indica se o valor de uma coluna especificada por `sql:field` deve estar em uma seção CDATA).</span><span class="sxs-lookup"><span data-stu-id="e7dc5-107">The `sql:use-cdata` annotation is used to specify that the data returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] should be wrapped in a CDATA section (that is, it indicates whether the value from a column that is specified by `sql:field` should be enclosed in a CDATA section).</span></span> <span data-ttu-id="e7dc5-108">A anotação `sql:use-cdata` só pode ser especificada em elementos que mapeiam para uma coluna de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-108">The `sql:use-cdata` annotation can be specified only on elements that map to a database column.</span></span>  
  
 <span data-ttu-id="e7dc5-109">A anotação `sql:use-cdata` usa um valor Booliano (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="e7dc5-109">The `sql:use-cdata` annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="e7dc5-110">Os valores aceitáveis são 0, 1, true e false.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-110">The acceptable values are 0, 1, true, and false.</span></span>  
  
 <span data-ttu-id="e7dc5-111">Essa anotação não pode ser usada com `sql:url-encode` ou nos tipos de atributo ID, IDREF, IDREFS, NMTOKEN e NMTOKENS.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-111">This annotation cannot be used with `sql:url-encode` or on the ID, IDREF, IDREFS, NMTOKEN, and NMTOKENS attribute types.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e7dc5-112">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e7dc5-112">Examples</span></span>  
 <span data-ttu-id="e7dc5-113">Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-113">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="e7dc5-114">Para obter mais informações, consulte [Requirements for running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="e7dc5-114">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqluse-cdata-on-an-element"></a><span data-ttu-id="e7dc5-115">a.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-115">A.</span></span> <span data-ttu-id="e7dc5-116">Especificando sql:use-cdata em um elemento</span><span class="sxs-lookup"><span data-stu-id="e7dc5-116">Specifying sql:use-cdata on an element</span></span>  
 <span data-ttu-id="e7dc5-117">No esquema a seguir, `sql:use-cdata` é definido como 1 (true) para o **\<AddressLine1>** dentro do **\<Address>** elemento.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-117">In the following schema, `sql:use-cdata` is set to 1 (True) for the **\<AddressLine1>** within the **\<Address>** element.</span></span> <span data-ttu-id="e7dc5-118">Como resultado, os dados são retornados em uma seção CDATA.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-118">As a result, the data is returned in a CDATA section.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Address"   
               sql:relation="Person.Address"   
               sql:key-fields="AddressID" >  
   <xsd:complexType>  
        <xsd:sequence>  
          <xsd:element name="AddressID"  type="xsd:string" />  
          <xsd:element name="AddressLine1" type="xsd:string"   
                       sql:use-cdata="1" />  
        </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e7dc5-119">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="e7dc5-119">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e7dc5-120">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-120">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="e7dc5-121">Salve o arquivo como UseCData.xml.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-121">Save the file as UseCData.xml.</span></span>  
  
2.  <span data-ttu-id="e7dc5-122">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-122">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="e7dc5-123">Salve o arquivo como UseCDataT.xml no mesmo diretório em que você salvou UseCData.xml.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-123">Save the file as UseCDataT.xml in the same directory where you saved UseCData.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="UseCData.xml">  
            /Address[AddressID < 11]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e7dc5-124">O caminho de diretório especificado para o esquema de mapeamento (UseCData.xml) é relativo ao diretório onde o modelo está salvo.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-124">The directory path specified for the mapping schema (UseCData.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e7dc5-125">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e7dc5-125">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\UseCData.xml"  
    ```  
  
3.  <span data-ttu-id="e7dc5-126">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e7dc5-126">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e7dc5-127">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e7dc5-127">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e7dc5-128">Este é o conjunto de resultados parcial:</span><span class="sxs-lookup"><span data-stu-id="e7dc5-128">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Address>   
    <AddressID>1</CustomerID>   
    <AddressLine1>   
      <![CDATA[ 1970 Napa Ct.  ]]>   
    </AddressLine1>   
  </Address>  
  <Address>  
    <AddressLine1>   
      <![CDATA[ 9833 Mt. Dias Blv. ]]>   
    </AddressLine1>   
  </Address>  
  ...  
</ROOT>  
```  
  
  
