---
title: Usando anotações em esquemas XSD (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, about annotated XSD schemas
- annotations [SQLXML]
- relationships [SQLXML]
- relationships [SQLXML], hierarchical relationships
- hierarchical relationships [SQLXML]
- mapping schema [SQLXML], scenarios for using
ms.assetid: 78f318a4-7a36-473b-9852-a4bae6940ce5
author: rothja
ms.author: jroth
ms.openlocfilehash: e2be94aa5815593d7a5a2e0c00bcd8849e81484e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573900"
---
# <a name="using-annotations-in-xsd-schemas-sqlxml-40"></a><span data-ttu-id="f9711-102">Usando anotações em esquemas XSD (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="f9711-102">Using Annotations in XSD Schemas (SQLXML 4.0)</span></span>
  <span data-ttu-id="f9711-103">No [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML 4.0, a linguagem de esquema XSD dá suporte a anotações de forma semelhante às anotações introduzidas na linguagem de esquema XDR (XML-Data Reduced).</span><span class="sxs-lookup"><span data-stu-id="f9711-103">In [!INCLUDE[msCoName](../../includes/msconame-md.md)] SQLXML 4.0, the XSD schema language supports annotations in a manner similar to the annotations introduced in the XML-Data Reduced (XDR) schema language.</span></span> <span data-ttu-id="f9711-104">Há anotações adicionais introduzidas no XSD para as quais não há suporte no XDR.</span><span class="sxs-lookup"><span data-stu-id="f9711-104">There are additional annotations introduced in XSD that are not supported in XDR.</span></span>  
  
 <span data-ttu-id="f9711-105">Essas anotações podem ser usadas dentro do esquema XSD para especificar o mapeamento de XML para relacional.</span><span class="sxs-lookup"><span data-stu-id="f9711-105">These annotations can be used within the XSD schema to specify XML-to-relational mapping.</span></span> <span data-ttu-id="f9711-106">Isso inclui o mapeamento entre elementos e atributos no esquema XSD para tabelas (exibições) e colunas nos bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="f9711-106">This includes mapping between elements and attributes in the XSD schema to tables (views) and columns in the databases.</span></span>  
  
 <span data-ttu-id="f9711-107">Se você não especificar as anotações, será utilizado o mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="f9711-107">If you do not specify the annotations, default mapping takes place.</span></span> <span data-ttu-id="f9711-108">Por padrão, um elemento XSD com um tipo complexo é mapeado para um nome de tabela (exibição) no banco de dados especificado, e um elemento ou atributo com um tipo simples é mapeado para a coluna com o mesmo nome que o elemento ou o atributo.</span><span class="sxs-lookup"><span data-stu-id="f9711-108">By default, an XSD element with a complex type maps to a table (view) name in the specified database, and an element or attribute with a simple type maps to the column with the same name as the element or attribute.</span></span>  
  
 <span data-ttu-id="f9711-109">Essas anotações também podem ser usadas para especificar as relações hierárquicas em XML, representando, portanto, as relações no banco de dados, porque um esquema XSD é simplesmente uma exibição de XML do dado relacional.</span><span class="sxs-lookup"><span data-stu-id="f9711-109">These annotations can also be used to specify the hierarchical relationships in XML-thus representing the relationships in the database, because an XSD schema is simply an XML view of relational data.</span></span>  
  
 <span data-ttu-id="f9711-110">Esta seção fornece descrições das anotações que podem ser usadas com esquemas XSD e exemplos de sua utilização.</span><span class="sxs-lookup"><span data-stu-id="f9711-110">This section provides descriptions of the annotations you can use with XSD schemas and examples of their usage.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f9711-111">Todos os exemplos nesta seção especificam consultas XPath simples no esquema XSD anotado descrito em cada exemplo.</span><span class="sxs-lookup"><span data-stu-id="f9711-111">All the examples in this section specify simple XPath queries against the annotated XSD schema described in each example.</span></span> <span data-ttu-id="f9711-112">É presumido que haja familiaridade com a linguagem XPath.</span><span class="sxs-lookup"><span data-stu-id="f9711-112">Familiarity with the XPath language is assumed.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="f9711-113">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="f9711-113">In This Section</span></span>  
 [<span data-ttu-id="f9711-114">Anotações XSD &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-114">XSD Annotations &#40;SQLXML 4.0&#41;</span></span>](xsd-annotations-sqlxml-4-0.md)  
 <span data-ttu-id="f9711-115">Lista as anotações que podem ser usadas com esquemas XSD, suas descrições e as anotações equivalentes para XDR.</span><span class="sxs-lookup"><span data-stu-id="f9711-115">Lists the annotations you can use with XSD schemas, their descriptions, and the equivalent annotations for XDR.</span></span>  
  
 [<span data-ttu-id="f9711-116">Mapeamento padrão de elementos e atributos XSD para tabelas e colunas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-116">Default Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](default-mapping-of-xsd-elements-and-attributes-to-tables-and-columns-sqlxml-4-0.md)  
 <span data-ttu-id="f9711-117">Explica o mapeamento padrão e fornece exemplos de tarefas relacionados a ele.</span><span class="sxs-lookup"><span data-stu-id="f9711-117">Explains default mapping and provides examples of tasks related to default mapping.</span></span>  
  
 [<span data-ttu-id="f9711-118">Mapeamento explícito de elementos e atributos XSD para tabelas e colunas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-118">Explicit Mapping of XSD Elements and Attributes to Tables and Columns &#40;SQLXML 4.0&#41;</span></span>](explicit-mapping-xsd-elements-and-attributes-to-tables-and-columns.md)  
 <span data-ttu-id="f9711-119">Explica o mapeamento explícito com as anotações `sql:relation` e `sql:field` e fornece exemplos.</span><span class="sxs-lookup"><span data-stu-id="f9711-119">Explains explicit mapping with the `sql:relation` and `sql:field` annotations, and provides examples.</span></span>  
  
 [<span data-ttu-id="f9711-120">Especificando relações usando SQL: relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-120">Specifying Relationships Using sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-relationships-using-sql-relationship-sqlxml-4-0.md)  
 <span data-ttu-id="f9711-121">Descreve e fornece exemplos da anotação `sql:relationship`.</span><span class="sxs-lookup"><span data-stu-id="f9711-121">Describes and provides examples of the `sql:relationship` annotation.</span></span>  
  
 [<span data-ttu-id="f9711-122">Especificando o atributo SQL: inverso em SQL: relationship &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-122">Specifying the sql:inverse Attribute on sql:relationship &#40;SQLXML 4.0&#41;</span></span>](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md)  
 <span data-ttu-id="f9711-123">Descreve a anotação `sql:inverse`.</span><span class="sxs-lookup"><span data-stu-id="f9711-123">Describes the `sql:inverse` annotation.</span></span>  
  
 [<span data-ttu-id="f9711-124">Criando elementos constantes usando SQL: is-constant &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-124">Creating Constant Elements Using sql:is-constant &#40;SQLXML 4.0&#41;</span></span>](creating-constant-elements-using-sql-is-constant-sqlxml-4-0.md)  
 <span data-ttu-id="f9711-125">Descreve e fornece exemplos da anotação `sql:is-constant`.</span><span class="sxs-lookup"><span data-stu-id="f9711-125">Describes and provides examples of the `sql:is-constant` annotation.</span></span>  
  
 [<span data-ttu-id="f9711-126">Excluindo elementos de esquema do documento XML resultante usando SQL: mapeado &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-126">Excluding Schema Elements from the Resulting XML Document Using sql:mapped &#40;SQLXML 4.0&#41;</span></span>](excluding-schema-elements-from-the-xml-document-using-sql-mapped.md)  
 <span data-ttu-id="f9711-127">Descreve e fornece exemplos da anotação `sql:mapped`.</span><span class="sxs-lookup"><span data-stu-id="f9711-127">Describes and provides examples of the `sql:mapped` annotation.</span></span>  
  
 [<span data-ttu-id="f9711-128">Filtrando valores usando SQL: limit-field e SQL: limit-value &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-128">Filtering Values Using sql:limit-field and sql:limit-value &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sql-limit-field-and-sql-limit-value.md)  
 <span data-ttu-id="f9711-129">Descreve e fornece exemplos das anotações `sql:limit-field` e `sql:limit-value`.</span><span class="sxs-lookup"><span data-stu-id="f9711-129">Describes and provides examples of the `sql:limit-field` and `sql:limit-value` annotations.</span></span>  
  
 [<span data-ttu-id="f9711-130">Identificando colunas de chave usando SQL: campos de chave &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-130">Identifying Key Columns Using sql:key-fields &#40;SQLXML 4.0&#41;</span></span>](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md)  
 <span data-ttu-id="f9711-131">Descreve e fornece exemplos da anotação `sql:key-fields`.</span><span class="sxs-lookup"><span data-stu-id="f9711-131">Describes and provides examples of the `sql:key-fields` annotation.</span></span>  
  
 [<span data-ttu-id="f9711-132">Especificando um namespace de destino usando o atributo targetNamespace &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-132">Specifying a Target Namespace Using the targetNamespace Attribute &#40;SQLXML 4.0&#41;</span></span>](specifying-a-target-namespace-using-the-targetnamespace-attribute-sqlxml-4-0.md)  
 <span data-ttu-id="f9711-133">Descreve e fornece exemplos do atributo **targetNamespace** .</span><span class="sxs-lookup"><span data-stu-id="f9711-133">Describes and provides examples of the **targetNamespace** attribute.</span></span>  
  
 [<span data-ttu-id="f9711-134">Criando atributos de tipo ID, IDREF e IDREFS válidos usando SQL: prefix &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-134">Creating Valid ID, IDREF, and IDREFS Type Attributes Using sql:prefix &#40;SQLXML 4.0&#41;</span></span>](creating-valid-id-idref-and-idrefs-type-attributes-using-sql-prefix-sqlxml-4-0.md)  
 <span data-ttu-id="f9711-135">Descreve e fornece exemplos da anotação `sql:prefix`.</span><span class="sxs-lookup"><span data-stu-id="f9711-135">Describes and provides examples of the `sql:prefix` annotation.</span></span>  
  
 [<span data-ttu-id="f9711-136">Coerção de tipo de dados e a anotação sql: DataType &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-136">Data Type Coercions and the sql:datatype Annotation &#40;SQLXML 4.0&#41;</span></span>](data-type-coercions-and-the-sql-datatype-annotation-sqlxml-4-0.md)  
 <span data-ttu-id="f9711-137">Descreve e fornece exemplos da anotação `sql:datatype`.</span><span class="sxs-lookup"><span data-stu-id="f9711-137">Describes and provides examples of the `sql:datatype` annotation.</span></span>  
  
 [<span data-ttu-id="f9711-138">Mapeando tipos de dados XSD para tipos de dados XPath &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-138">Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md)  
 <span data-ttu-id="f9711-139">Fornece uma tabela que compara tipos de dados XSD, XDR e XPath e lista as conversões relevantes do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f9711-139">Provides a table that compares XSD, XDR, and XPath datatypes and lists the relevant [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conversions.</span></span>  
  
 [<span data-ttu-id="f9711-140">Criando seções CDATA usando SQL: use-cdata &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-140">Creating CDATA Sections Using sql:use-cdata &#40;SQLXML 4.0&#41;</span></span>](creating-cdata-sections-using-sql-use-cdata-sqlxml-4-0.md)  
 <span data-ttu-id="f9711-141">Descreve e fornece exemplos da anotação `sql:use-data`.</span><span class="sxs-lookup"><span data-stu-id="f9711-141">Describes and provides examples of the `sql:use-data` annotation.</span></span>  
  
 [<span data-ttu-id="f9711-142">Solicitando referências de URL a dados de BLOB usando SQL: encode &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-142">Requesting URL References to BLOB Data Using sql:encode &#40;SQLXML 4.0&#41;</span></span>](requesting-url-references-to-blob-data-using-sql-encode-sqlxml-4-0.md)  
 <span data-ttu-id="f9711-143">Descreve e fornece exemplos da anotação `sql:encode`.</span><span class="sxs-lookup"><span data-stu-id="f9711-143">Describes and provides examples of the `sql:encode` annotation.</span></span>  
  
 [<span data-ttu-id="f9711-144">Recuperando dados não consumidos usando o SQL: overflow-field &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-144">Retrieving Unconsumed Data Using the sql:overflow-field &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/annotation-interpretation-sql-overflow-field.md)  
 <span data-ttu-id="f9711-145">Descreve e fornece exemplos da anotação `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="f9711-145">Describes and provides examples of the `sql:overflow-field` annotation.</span></span>  
  
 [<span data-ttu-id="f9711-146">Ocultando elementos e atributos usando sql:hide</span><span class="sxs-lookup"><span data-stu-id="f9711-146">Hiding Elements and Attributes by Using sql:hide</span></span>](hiding-elements-and-attributes-by-using-sql-hide.md)  
 <span data-ttu-id="f9711-147">Descreve e fornece exemplos da anotação `sql:hide`.</span><span class="sxs-lookup"><span data-stu-id="f9711-147">Describes and provides examples of the `sql:hide` annotation.</span></span>  
  
 [<span data-ttu-id="f9711-148">Usando as anotações sql:identity e sql:guid</span><span class="sxs-lookup"><span data-stu-id="f9711-148">Using the sql:identity and sql:guid Annotations</span></span>](using-the-sql-identity-and-sql-guid-annotations.md)  
 <span data-ttu-id="f9711-149">Descreve e fornece exemplos das anotações `sql:identity` e `sql:guid`.</span><span class="sxs-lookup"><span data-stu-id="f9711-149">Describes and provides examples of the `sql:identity` and `sql:guid` annotations.</span></span>  
  
 [<span data-ttu-id="f9711-150">Especificando a profundidade em relações recursivas usando sql:max-depth</span><span class="sxs-lookup"><span data-stu-id="f9711-150">Specifying Depth in Recursive Relationships by Using sql:max-depth</span></span>](specifying-depth-in-recursive-relationships-by-using-sql-max-depth.md)  
 <span data-ttu-id="f9711-151">Descreve e fornece exemplos da anotação `sql:max-depth`.</span><span class="sxs-lookup"><span data-stu-id="f9711-151">Describes and provides examples of the `sql:max-depth` annotation.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f9711-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f9711-152">See Also</span></span>  
 [<span data-ttu-id="f9711-153">Considerações de segurança de esquema anotadas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="f9711-153">Annotated Schema Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../sqlxml-annotated-xsd-schemas-xpath-queries/security/annotated-schema-security-considerations-sqlxml-4-0.md)  
  
  
