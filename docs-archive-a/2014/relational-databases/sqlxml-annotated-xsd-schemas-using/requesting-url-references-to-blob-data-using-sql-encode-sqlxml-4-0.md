---
title: 'Solicitando referências de URL a dados de BLOB usando SQL: encode (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:encode
- encode annotation
- URL references to BLOB data [SQLXML]
- references to BLOB data [SQLXML]
- annotated XSD schemas, URL references to BLOB data
- requesting URL references to BLOB data
- BLOBs, URL references
- Base 64-encoded format
ms.assetid: 2f8cd93b-c636-462b-8291-167197233ee0
author: rothja
ms.author: jroth
ms.openlocfilehash: 8a9f5edcfab4a9d7307327d97bc2099c78c666c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582373"
---
# <a name="requesting-url-references-to-blob-data-using-sqlencode-sqlxml-40"></a><span data-ttu-id="72020-102">Solicitando referências URL a dados BLOB usando sql:encode (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="72020-102">Requesting URL References to BLOB Data Using sql:encode (SQLXML 4.0)</span></span>
  <span data-ttu-id="72020-103">Em um esquema XSD anotado, quando um atributo (ou elemento) é mapeado para uma coluna BLOB no Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], os dados são retornados no formato codificado na base 64 no XML.</span><span class="sxs-lookup"><span data-stu-id="72020-103">In an annotated XSD schema, when an attribute (or element) is mapped to a BLOB column in Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], the data is returned in Base 64-encoded format within XML.</span></span>  
  
 <span data-ttu-id="72020-104">Caso queira que uma referência aos dados (um URI) seja retornada e que possa ser usada posteriormente para recuperar os dados BLOB em um formato binário, especifique a anotação `sql:encode`.</span><span class="sxs-lookup"><span data-stu-id="72020-104">If you want a reference to the data (a URI) to be returned that can be used later to retrieve the BLOB data in a binary format, specify the `sql:encode` annotation.</span></span> <span data-ttu-id="72020-105">Você pode especificar `sql:encode` em um atributo ou elemento de tipo simples.</span><span class="sxs-lookup"><span data-stu-id="72020-105">You can specify `sql:encode` on an attribute or element of simple type.</span></span>  
  
 <span data-ttu-id="72020-106">Especifique a anotação `sql:encode` para indicar que deve ser retornada uma URL para o campo em vez do valor do campo.</span><span class="sxs-lookup"><span data-stu-id="72020-106">Specify the `sql:encode` annotation to indicate that a URL to the field should be returned instead of the value of the field.</span></span> <span data-ttu-id="72020-107">`sql:encode` depende da chave primária para gerar uma seleção singleton na URL.</span><span class="sxs-lookup"><span data-stu-id="72020-107">`sql:encode` depends on the primary key to generate a singleton select in the URL.</span></span> <span data-ttu-id="72020-108">A chave primária pode ser especificada usando a `sql:key-fields` anotação.</span><span class="sxs-lookup"><span data-stu-id="72020-108">The primary key can be specified using the `sql:key-fields` annotation.</span></span>  
  
 <span data-ttu-id="72020-109">À anotação `sql:encode` é possível atribuir o valor "url" ou "default".</span><span class="sxs-lookup"><span data-stu-id="72020-109">The `sql:encode` annotation can be assigned the "url" or the "default" value.</span></span> <span data-ttu-id="72020-110">Um valor "default" retorna dados codificados na base 64.</span><span class="sxs-lookup"><span data-stu-id="72020-110">A value of "default" returns data in Base 64-encoded format.</span></span>  
  
 <span data-ttu-id="72020-111">A anotação `sql:encode` não pode ser usada com `sql:use-cdata` ou nos tipos de atributo ID, IDREF, IDREFS, NMTOKEN ou NMTOKENS.</span><span class="sxs-lookup"><span data-stu-id="72020-111">The `sql:encode` annotation cannot be used with `sql:use-cdata` or on the ID, IDREF, IDREFS, NMTOKEN, or NMTOKENS attribute types.</span></span> <span data-ttu-id="72020-112">Ele também não pode ser usado com atributo XSD **fixo** .</span><span class="sxs-lookup"><span data-stu-id="72020-112">It can also not be used with XSD **fixed** attribute.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="72020-113">As colunas de tipo BLOB não podem ser usadas como parte de uma chave ou chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="72020-113">BLOB-type columns cannot be used as a part of a key or foreign key.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="72020-114">Exemplos</span><span class="sxs-lookup"><span data-stu-id="72020-114">Examples</span></span>  
 <span data-ttu-id="72020-115">Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="72020-115">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="72020-116">Para obter mais informações, consulte [Requirements for running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="72020-116">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlencode-to-obtain-a-url-reference-to-blob-data"></a><span data-ttu-id="72020-117">a.</span><span class="sxs-lookup"><span data-stu-id="72020-117">A.</span></span> <span data-ttu-id="72020-118">Especificando sql:encode para obter uma referência URL aos dados BLOB</span><span class="sxs-lookup"><span data-stu-id="72020-118">Specifying sql:encode to obtain a URL reference to BLOB data</span></span>  
 <span data-ttu-id="72020-119">Neste exemplo, o esquema de mapeamento especifica `sql:encode` no atributo **LargePhoto** para recuperar a referência de URI para uma foto de produto específica (em vez de recuperar os dados binários no formato codificado em base 64).</span><span class="sxs-lookup"><span data-stu-id="72020-119">In this example, the mapping schema specifies `sql:encode` on the **LargePhoto** attribute to retrieve the URI reference to a specific product photo (instead of retrieving the binary data in Base 64-encoded format).</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="ProductPhoto" sql:relation="Production.ProductPhoto"   
               sql:key-fields="ProductPhotoID" >  
   <xsd:complexType>  
      <xsd:attribute name="ProductPhotoID"  type="xsd:int"  />  
     <xsd:attribute name="LargePhoto" type="xsd:string" sql:encode="url" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="72020-120">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="72020-120">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="72020-121">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="72020-121">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="72020-122">Salve o arquivo como sqlEncode.xml.</span><span class="sxs-lookup"><span data-stu-id="72020-122">Save the file as sqlEncode.xml.</span></span>  
  
2.  <span data-ttu-id="72020-123">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="72020-123">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="72020-124">Salve o arquivo como sqlEncodeT.xml no mesmo diretório onde você salvou sqlEncode.xml.</span><span class="sxs-lookup"><span data-stu-id="72020-124">Save the file as sqlEncodeT.xml in the same directory where you saved sqlEncode.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sqlEncode.xml">  
            /ProductPhoto[@ProductPhotoID=100]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="72020-125">O caminho de diretório especificado para o esquema de mapeamento (sqlEncode.xml) é relativo ao diretório onde o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="72020-125">The directory path specified for the mapping schema (sqlEncode.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="72020-126">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="72020-126">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\sqlEncode.xml"  
    ```  
  
3.  <span data-ttu-id="72020-127">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="72020-127">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="72020-128">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="72020-128">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="72020-129">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="72020-129">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <ProductPhoto ProductPhotoID="100"  
                 LargePhoto="dbobject/Production.ProductPhoto[@ProductPhotoID="100"]/@LargePhoto" />   
</ROOT>  
```  
  
  
