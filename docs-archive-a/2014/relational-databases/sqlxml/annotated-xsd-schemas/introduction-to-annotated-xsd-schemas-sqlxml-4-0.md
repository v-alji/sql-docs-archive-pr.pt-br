---
title: Introdução aos esquemas XSD anotados (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/07/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces [SQLXML], annotated XSD schemas
- mapping schema [SQLXML], about mapping schema
- views [SQLXML]
- valid XSD schemas [SQLXML]
- annotations [SQLXML]
- XSD schemas [SQLXML], creating XML views
- annotated XSD schemas, creating XML views
- minimum XSD schema
- annotated XSD schemas, examples
- XML views [SQLXML]
ms.assetid: 15282db1-65c4-43be-bdb7-e9ef49cb33a2
author: rothja
ms.author: jroth
ms.openlocfilehash: b91be71569daa9e5bf4143be9f652617ba7c5b01
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575724"
---
# <a name="introduction-to-annotated-xsd-schemas-sqlxml-40"></a><span data-ttu-id="0c569-102">Introdução a esquemas XSD anotados (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="0c569-102">Introduction to Annotated XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="0c569-103">É possível criar exibições XML de dados relacionais usando a linguagem XSD.</span><span class="sxs-lookup"><span data-stu-id="0c569-103">You can create XML views of relational data by using the XML Schema Definition (XSD) language.</span></span> <span data-ttu-id="0c569-104">Dessa forma, essas exibições podem ser consultadas por meio de consultas em linguagem XPath.</span><span class="sxs-lookup"><span data-stu-id="0c569-104">These views can then be queried by using XML Path language (XPath) queries.</span></span> <span data-ttu-id="0c569-105">Isso é semelhante à criação de exibições usando instruções CREATE VIEW e especificando consultas SQL com base na exibição.</span><span class="sxs-lookup"><span data-stu-id="0c569-105">This is similar to creating views by using CREATE VIEW statements and then specifying SQL queries against the view.</span></span>  
  
 <span data-ttu-id="0c569-106">Um esquema XML descreve a estrutura de um documento XML, além das várias restrições referentes aos dados do documento.</span><span class="sxs-lookup"><span data-stu-id="0c569-106">An XML schema describes the structure of an XML document and also describes the various constraints on the data in the document.</span></span> <span data-ttu-id="0c569-107">Quando você especifica as consultas XPath com base no esquema, a estrutura do documento XML retornado é determinada pelo esquema que serve de base para a consulta XPath executada.</span><span class="sxs-lookup"><span data-stu-id="0c569-107">When you specify XPath queries against the schema, the structure of the XML document returned is determined by the schema against which the XPath query is executed.</span></span>  
  
 <span data-ttu-id="0c569-108">Em um esquema XSD, o **\<xsd:schema>** elemento inclui todo o esquema; todas as declarações de elemento devem estar contidas dentro **\<xsd:schema>** do elemento.</span><span class="sxs-lookup"><span data-stu-id="0c569-108">In an XSD schema, the **\<xsd:schema>** element encloses the entire schema; all element declarations must be contained within the **\<xsd:schema>** element.</span></span> <span data-ttu-id="0c569-109">Você pode descrever atributos que definem o namespace no qual reside o esquema e os namespaces que são usados no esquema como propriedades do **\<xsd:schema>** elemento.</span><span class="sxs-lookup"><span data-stu-id="0c569-109">You can describe attributes that define the namespace in which the schema resides and the namespaces that are used in the schema as properties of the **\<xsd:schema>** element.</span></span>  
  
 <span data-ttu-id="0c569-110">Um esquema XSD válido deve conter o **\<xsd:schema>** elemento definido da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="0c569-110">A valid XSD schema must contain the **\<xsd:schema>** element defined as follows:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<!-- additional schema definitions here -->  
</xsd:schema>  
```  
  
 <span data-ttu-id="0c569-111">O **\<xsd:schema>** elemento é derivado da especificação de namespace de esquema XML em http://www.w3.org/2001/XMLSchema .</span><span class="sxs-lookup"><span data-stu-id="0c569-111">The **\<xsd:schema>** element is derived from the XML Schema namespace specification at http://www.w3.org/2001/XMLSchema.</span></span>  
  
## <a name="annotations-to-the-xsd-schema"></a><span data-ttu-id="0c569-112">Anotações para o esquema XSD</span><span class="sxs-lookup"><span data-stu-id="0c569-112">Annotations to the XSD Schema</span></span>  
 <span data-ttu-id="0c569-113">É possível usar um esquema XSD com anotações que descrevam o mapeamento para um banco de dados, consultem o banco de dados e retornem os resultados na forma de um documento XML.</span><span class="sxs-lookup"><span data-stu-id="0c569-113">You can use an XSD schema with annotations that describe the mapping to a database, query the database, and return the results in the form of an XML document.</span></span> <span data-ttu-id="0c569-114">São fornecidas anotações para mapear um esquema XSD para tabelas e colunas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="0c569-114">Annotations are provided to map an XSD schema to database tables and columns.</span></span> <span data-ttu-id="0c569-115">As consultas XPath podem ser especificadas com base na exibição XML criada pelo esquema XSD para consultar o banco de dados e obter os resultados como um XML.</span><span class="sxs-lookup"><span data-stu-id="0c569-115">XPath queries can be specified against the XML view created by the XSD schema to query the database and obtain results as an XML.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c569-116">No [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, a linguagem XSD oferece suporte a anotações introduzidas com a linguagem XDR no [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)].</span><span class="sxs-lookup"><span data-stu-id="0c569-116">In [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0, the XSD schema language supports the annotations introduced with annotated XML-Data Reduced (XDR) schema language in [!INCLUDE[ssVersion2000](../../../includes/ssversion2000-md.md)].</span></span> <span data-ttu-id="0c569-117">A XDR anotada está preterida no SQLXML 4.0.</span><span class="sxs-lookup"><span data-stu-id="0c569-117">Annotated XDR is deprecated in SQLXML 4.0.</span></span>  
  
 <span data-ttu-id="0c569-118">No contexto do banco de dados relacional, é útil mapear o esquema XSD arbitrário para um armazenamento relacional.</span><span class="sxs-lookup"><span data-stu-id="0c569-118">In the context of the relational database, it is useful to map the arbitrary XSD schema to a relational store.</span></span> <span data-ttu-id="0c569-119">Uma maneira de fazer isso é anotar o esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="0c569-119">One way to achieve this is to annotate the XSD schema.</span></span> <span data-ttu-id="0c569-120">Um esquema XSD com as anotações é conhecido como um esquema de *mapeamento*, que fornece informações sobre como os dados XML serão mapeados para a Relational Store.</span><span class="sxs-lookup"><span data-stu-id="0c569-120">An XSD schema with the annotations is referred to as a *mapping schema*, which provides information pertaining to how XML data is to be mapped to the relational store.</span></span> <span data-ttu-id="0c569-121">Um esquema de mapeamento é, com efeito, uma exibição XML dos dados relacionais.</span><span class="sxs-lookup"><span data-stu-id="0c569-121">A mapping schema is, in effect, an XML view of the relational data.</span></span> <span data-ttu-id="0c569-122">Esses mapeamentos podem ser usados para recuperar dados relacionais como um documento XML.</span><span class="sxs-lookup"><span data-stu-id="0c569-122">These mappings can be used to retrieve relational data as an XML document.</span></span>  
  
## <a name="namespace-for-annotations"></a><span data-ttu-id="0c569-123">Namespace para anotações</span><span class="sxs-lookup"><span data-stu-id="0c569-123">Namespace for Annotations</span></span>  
 <span data-ttu-id="0c569-124">Em um esquema XSD, as anotações são especificadas usando o namespace **urn: schemas-microsoft-com: Mapping-Schema**.</span><span class="sxs-lookup"><span data-stu-id="0c569-124">In an XSD schema, annotations are specified by using the namespace **urn:schemas-microsoft-com:mapping-schema**.</span></span> <span data-ttu-id="0c569-125">Conforme mostrado no exemplo a seguir, a maneira mais fácil de especificar o namespace é especificá-lo na **\<xsd:schema>** marca.</span><span class="sxs-lookup"><span data-stu-id="0c569-125">As shown in the following example, the easiest way to specify the namespace is to specify it in the **\<xsd:schema>** tag.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
...  
</xsd:schema>  
```  
  
 <span data-ttu-id="0c569-126">O prefixo de namespace usado é arbitrário.</span><span class="sxs-lookup"><span data-stu-id="0c569-126">The namespace prefix that is used is arbitrary.</span></span> <span data-ttu-id="0c569-127">Nesta documentação, o prefixo **SQL** é usado para denotar o namespace Annotation e distinguir as anotações nesse namespace deles em outros namespaces.</span><span class="sxs-lookup"><span data-stu-id="0c569-127">In this documentation, the **sql** prefix is used to denote the annotation namespace and to distinguish annotations in this namespace from those in other namespaces.</span></span>  
  
## <a name="example-of-an-annotated-xsd-schema"></a><span data-ttu-id="0c569-128">Exemplo de um esquema XSD anotado</span><span class="sxs-lookup"><span data-stu-id="0c569-128">Example of an Annotated XSD Schema</span></span>  
 <span data-ttu-id="0c569-129">No exemplo a seguir, o esquema XSD consiste em um **\<Person.Contact>** elemento.</span><span class="sxs-lookup"><span data-stu-id="0c569-129">In the following example, the XSD schema consists of an **\<Person.Contact>** element.</span></span> <span data-ttu-id="0c569-130">O **\<Employee>** elemento tem um atributo **ContactID** e **\<FirstName>** os **\<LastName>** elementos filho:</span><span class="sxs-lookup"><span data-stu-id="0c569-130">The **\<Employee>** element has a **ContactID** attribute and **\<FirstName>** and **\<LastName>** child elements:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema">  
  <xsd:element name="Contact" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="FName"    
                     type="xsd:string" />   
        <xsd:element name="LName"  
                     type="xsd:string" />  
     </xsd:sequence>  
        <xsd:attribute name="ConID" type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="0c569-131">As anotações são adicionadas ao esquema XSD para mapear seus elementos e atributos para as tabelas e colunas do banco de dados:</span><span class="sxs-lookup"><span data-stu-id="0c569-131">Annotations are added to this XSD schema to map its elements and attributes to the database tables and columns:</span></span>  
  
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
        <xsd:attribute name="ConID"   
                       sql:field="ContactID"   
                       type="xsd:integer" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="0c569-132">No esquema de mapeamento, o **\<Contact>** elemento é mapeado para a tabela Person. Contact no banco de dados AdventureWorks de exemplo usando a `sql:relation` anotação.</span><span class="sxs-lookup"><span data-stu-id="0c569-132">In the mapping schema, the **\<Contact>** element is mapped to the Person.Contact table in the sample AdventureWorks database by using the `sql:relation` annotation.</span></span> <span data-ttu-id="0c569-133">Os atributos ConID, FName e LName são mapeados para as colunas ContactID, FirstName e LastName na tabela Person.Contact usando as anotações `sql:field`.</span><span class="sxs-lookup"><span data-stu-id="0c569-133">The attributes ConID, FName, and LName are mapped to the ContactID, FirstName, and LastName columns in the Person.Contact table by using the `sql:field` annotations.</span></span>  
  
 <span data-ttu-id="0c569-134">Esse esquema XSD anotado fornece a exibição XML dos dados relacionais.</span><span class="sxs-lookup"><span data-stu-id="0c569-134">This annotated XSD schema provides the XML view of the relational data.</span></span> <span data-ttu-id="0c569-135">Essa exibição XML pode ser consultada usando a linguagem XPath.</span><span class="sxs-lookup"><span data-stu-id="0c569-135">This XML view can be queried using the XPath language.</span></span> <span data-ttu-id="0c569-136">Uma consulta XPath retorna um documento XML como resultado, e não o conjunto de linhas retornado pelas consultas SQL.</span><span class="sxs-lookup"><span data-stu-id="0c569-136">An XPath query returns an XML document as a result, instead of the rowset that is returned by SQL queries.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="0c569-137">No esquema de mapeamento, a diferenciação de maiúsculas e minúsculas nos valores relacionais especificados (como, por exemplo, o nome da tabela e o nome da coluna) depende do uso das configurações de ordenação de maiúsculas e minúsculas pelo SQL Server.</span><span class="sxs-lookup"><span data-stu-id="0c569-137">In the mapping schema, case-sensitivity for the specified relational values (such as table name and column name) depends upon if SQL Server is using case-sensitive collation settings.</span></span> <span data-ttu-id="0c569-138">Para obter mais informações, consulte [Suporte a ordenações e a Unicode](../../collations/collation-and-unicode-support.md).</span><span class="sxs-lookup"><span data-stu-id="0c569-138">For more information, see [Collation and Unicode Support](../../collations/collation-and-unicode-support.md).</span></span>  
  
## <a name="other-resources"></a><span data-ttu-id="0c569-139">Outros recursos</span><span class="sxs-lookup"><span data-stu-id="0c569-139">Other Resources</span></span>  
 <span data-ttu-id="0c569-140">Você pode encontrar mais informações sobre as linguagens XSD (XML Schema Definition), XPath (XML Path) e XSLT (Linguagem XSL Transformations) nos seguintes sites:</span><span class="sxs-lookup"><span data-stu-id="0c569-140">You can find more information about XML Schema Definition language (XSD), XML Path language (XPath), and Extensible Stylesheet Language Transformations (XSLT) at the following Web sites:</span></span>  
  
-   <span data-ttu-id="0c569-141">Esquema XML parte 0: Primer, recomendação do W3C (http://www.w3.org/TR/xmlschema-0/)</span><span class="sxs-lookup"><span data-stu-id="0c569-141">XML Schema Part 0: Primer, W3C Recommendation (http://www.w3.org/TR/xmlschema-0/)</span></span>  
  
-   <span data-ttu-id="0c569-142">Esquema XML parte 1: estruturas, recomendação do W3C (http://www.w3.org/TR/xmlschema-1/)</span><span class="sxs-lookup"><span data-stu-id="0c569-142">XML Schema Part 1: Structures, W3C Recommendation (http://www.w3.org/TR/xmlschema-1/)</span></span>  
  
-   <span data-ttu-id="0c569-143">Esquema XML parte 2: tipos de texto, recomendação do W3C (http://www.w3.org/TR/xmlschema-2/)</span><span class="sxs-lookup"><span data-stu-id="0c569-143">XML Schema Part 2:Datatypes, W3C Recommendation (http://www.w3.org/TR/xmlschema-2/)</span></span>  
  
-   <span data-ttu-id="0c569-144">Linguagem de caminho XML (XPath) (http://www.w3.org/TR/xpath)</span><span class="sxs-lookup"><span data-stu-id="0c569-144">XML Path Language (XPath) (http://www.w3.org/TR/xpath)</span></span>  
  
-   <span data-ttu-id="0c569-145">Transformações XSL (XSLT) (http://www.w3.org/TR/xslt)</span><span class="sxs-lookup"><span data-stu-id="0c569-145">XSL Transformations (XSLT) (http://www.w3.org/TR/xslt)</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="0c569-146">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="0c569-146">See Also</span></span>  
 <span data-ttu-id="0c569-147">[Considerações de segurança de esquema anotadas &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="0c569-147">[Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="0c569-148">Esquemas XDR anotados &#40;preteridos no SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="0c569-148">Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;</span></span>](annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md)  
  
  
