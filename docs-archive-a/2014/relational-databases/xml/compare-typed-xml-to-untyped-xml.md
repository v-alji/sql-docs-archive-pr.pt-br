---
title: Comparar XML tipado com XML não tipado | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- xml data type [SQL Server], variables
- parameters [XML in SQL Server]
- facets [XML in SQL Server]
- xml data type [SQL Server], columns
- untyped XML
- xml data type [SQL Server], typed xml
- XML [SQL Server], typed
- variables [XML in SQL Server], creating
- xml data type [SQL Server], untyped xml
- columns [XML in SQL Server], creating
- typed XML
- document mode processing [SQL Server]
- XML [SQL Server], untyped
- xml data type [SQL Server], parameters
ms.assetid: 4bc50af9-2f7d-49df-bb01-854d080c72c7
author: rothja
ms.author: jroth
ms.openlocfilehash: fae9ca930bd8741a1332b61c8272f2133590483e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679744"
---
# <a name="compare-typed-xml-to-untyped-xml"></a><span data-ttu-id="27def-102">Comparar XML digitado com XML não digitado</span><span class="sxs-lookup"><span data-stu-id="27def-102">Compare Typed XML to Untyped XML</span></span>
  <span data-ttu-id="27def-103">É possível criar variáveis, parâmetros e colunas do tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="27def-103">You can create variables, parameters, and columns of the `xml` type.</span></span> <span data-ttu-id="27def-104">Opcionalmente, é possível associar uma coleção de esquemas XML com uma variável, parâmetro ou coluna de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="27def-104">You can optionally associate a collection of XML schemas with a variable, parameter, or column of `xml` type.</span></span> <span data-ttu-id="27def-105">Nesse caso, a `xml` instância de tipo de dados é *chamada tipada*.</span><span class="sxs-lookup"><span data-stu-id="27def-105">In this case, the `xml` data type instance is called *typed*.</span></span> <span data-ttu-id="27def-106">Caso contrário, a instância XML é chamada *sem-tipo*.</span><span class="sxs-lookup"><span data-stu-id="27def-106">Otherwise, the XML instance is called *untyped*.</span></span>  
  
## <a name="well-formed-xml-and-the-xml-data-type"></a><span data-ttu-id="27def-107">XML bem formado e o tipo de dados xml</span><span class="sxs-lookup"><span data-stu-id="27def-107">Well-formed XML and the xml Data Type</span></span>  
 <span data-ttu-id="27def-108">O tipo de dados `xml` implementa o tipo de dados `xml` padrão ISO.</span><span class="sxs-lookup"><span data-stu-id="27def-108">The `xml` data type implements the ISO standard `xml` data type.</span></span> <span data-ttu-id="27def-109">Portanto ele pode armazenar documentos bem formados em XML versão 1.0 e também os chamados fragmentos de conteúdo XML com nós de texto e um número arbitrário de elementos de nível superior em uma coluna XML sem-tipo.</span><span class="sxs-lookup"><span data-stu-id="27def-109">Therefore, it can store well-formed XML version 1.0 documents and also so-called XML content fragments with text nodes and an arbitrary number of top-level elements in an untyped XML column.</span></span> <span data-ttu-id="27def-110">Os sistema verifica se os dados estão bem formados, se não requerem que a coluna esteja associada a esquemas XML e rejeita dados que não são bem formados no sentido estendido.</span><span class="sxs-lookup"><span data-stu-id="27def-110">The system checks that the data is well-formed, does not require the column to be bound to XML schemas, and rejects data that is not well-formed in the extended sense.</span></span> <span data-ttu-id="27def-111">Isso também é verdadeiro para variáveis e parâmetros XML sem-tipo.</span><span class="sxs-lookup"><span data-stu-id="27def-111">This is true also of untyped XML variables and parameters.</span></span>  
  
## <a name="xml-schemas"></a><span data-ttu-id="27def-112">Esquemas XML</span><span class="sxs-lookup"><span data-stu-id="27def-112">XML Schemas</span></span>  
 <span data-ttu-id="27def-113">Um esquema XML fornece o seguinte:</span><span class="sxs-lookup"><span data-stu-id="27def-113">An XML schema provides the following:</span></span>  
  
-   <span data-ttu-id="27def-114">**Restrições de validação.**</span><span class="sxs-lookup"><span data-stu-id="27def-114">**Validation constraints.**</span></span> <span data-ttu-id="27def-115">Sempre que uma instância xml com tipo é atribuída ou modificada, o SQL Server a valida.</span><span class="sxs-lookup"><span data-stu-id="27def-115">Whenever a typed xml instance is assigned to or modified, SQL Server validates the instance.</span></span>  
  
-   <span data-ttu-id="27def-116">**Informações sobre tipos de dados.**</span><span class="sxs-lookup"><span data-stu-id="27def-116">**Data type information.**</span></span> <span data-ttu-id="27def-117">Os esquemas fornecem informações sobre os tipos de atributos e elementos na instância de tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="27def-117">Schemas provide information about the types of attributes and elements in the `xml` data type instance.</span></span> <span data-ttu-id="27def-118">As informações de tipo fornecem semântica operacional mais precisa aos valores contidos na instância do que é possível com `xml` sem-tipo.</span><span class="sxs-lookup"><span data-stu-id="27def-118">The type information provides more precise operational semantics to the values contained in the instance than is possible with untyped `xml`.</span></span> <span data-ttu-id="27def-119">Por exemplo, podem ser executadas operações aritméticas decimais em um valor decimal, mas não em um valor de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="27def-119">For example, decimal arithmetic operations can be performed on a decimal value, but not on a string value.</span></span> <span data-ttu-id="27def-120">Por causa disso, o armazenamento de XML com tipo pode ser feito de maneira significativamente mais compacta do que o XML sem-tipo.</span><span class="sxs-lookup"><span data-stu-id="27def-120">Because of this, typed XML storage can be made significantly more compact than untyped XML.</span></span>  
  
## <a name="choosing-typed-or-untyped-xml"></a><span data-ttu-id="27def-121">Escolhendo XML com tipo ou sem-tipo</span><span class="sxs-lookup"><span data-stu-id="27def-121">Choosing Typed or Untyped XML</span></span>  
 <span data-ttu-id="27def-122">Use tipo de dados `xml` sem-tipo nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="27def-122">Use untyped `xml` data type in the following situations:</span></span>  
  
-   <span data-ttu-id="27def-123">Você não tem um esquema para obter os dados XML.</span><span class="sxs-lookup"><span data-stu-id="27def-123">You do not have a schema for your XML data.</span></span>  
  
-   <span data-ttu-id="27def-124">Você tem esquemas, mas não quer que o servidor valide os dados.</span><span class="sxs-lookup"><span data-stu-id="27def-124">You have schemas, but you do not want the server to validate the data.</span></span> <span data-ttu-id="27def-125">Algumas vezes, esse é o caso quando um aplicativo executa validação do lado do cliente antes de armazenar os dados no servidor ou armazena temporariamente os dados XML que são inválidos de acordo com o esquema ou usa componentes de esquema que não têm suporte no servidor.</span><span class="sxs-lookup"><span data-stu-id="27def-125">This is sometimes the case when an application performs client-side validation before storing the data at the server, or temporarily stores XML data that is invalid according to the schema, or uses schema components that are not supported at the server.</span></span>  
  
 <span data-ttu-id="27def-126">Use `xml` tipo de dados tipado nas seguintes situações:</span><span class="sxs-lookup"><span data-stu-id="27def-126">Use typed `xml` data type in the following situations:</span></span>  
  
-   <span data-ttu-id="27def-127">Você tem esquemas para os dados XML e quer que o servidor valide os dados XML de acordo com os esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="27def-127">You have schemas for your XML data and you want the server to validate your XML data according to the XML schemas.</span></span>  
  
-   <span data-ttu-id="27def-128">Você quer usufruir de otimizações de consulta e de armazenamento com base em informações de tipo.</span><span class="sxs-lookup"><span data-stu-id="27def-128">You want to take advantage of storage and query optimizations based on type information.</span></span>  
  
-   <span data-ttu-id="27def-129">Você quer usufruir melhor de informações de tipo durante a compilação de suas consultas.</span><span class="sxs-lookup"><span data-stu-id="27def-129">You want to take better advantage of type information during compilation of your queries.</span></span>  
  
 <span data-ttu-id="27def-130">Colunas, parâmetros e variáveis de XML com tipo podem armazenar conteúdo ou documentos XML.</span><span class="sxs-lookup"><span data-stu-id="27def-130">Typed XML columns, parameters, and variables can store XML documents or content.</span></span> <span data-ttu-id="27def-131">No entanto é necessário especificar com um sinalizador se você está armazenando um documento ou conteúdo no momento da declaração.</span><span class="sxs-lookup"><span data-stu-id="27def-131">However, you have to specify with a flag whether you are storing a document or content at the time of declaration.</span></span> <span data-ttu-id="27def-132">Além disso, você precisa fornecer a coleção de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="27def-132">Additionally, you have to provide the collection of XML schemas.</span></span> <span data-ttu-id="27def-133">Especifique DOCUMENT se cada instância XML tiver exatamente um elemento de nível superior.</span><span class="sxs-lookup"><span data-stu-id="27def-133">Specify DOCUMENT if each XML instance has exactly one top-level element.</span></span> <span data-ttu-id="27def-134">Caso contrário, use CONTENT.</span><span class="sxs-lookup"><span data-stu-id="27def-134">Otherwise, use CONTENT.</span></span> <span data-ttu-id="27def-135">O compilador de consultas usa o sinalizador DOCUMENT em verificações de tipo durante a compilação de consultas para deduzir elementos singleton de nível superior.</span><span class="sxs-lookup"><span data-stu-id="27def-135">The query compiler uses the DOCUMENT flag in type checks during query compilation to infer singleton top-level elements.</span></span>  
  
## <a name="creating-typed-xml"></a><span data-ttu-id="27def-136">Criando XML com tipo</span><span class="sxs-lookup"><span data-stu-id="27def-136">Creating Typed XML</span></span>  
 <span data-ttu-id="27def-137">Antes `xml` de criar variáveis, parâmetros ou colunas tipados, primeiro você deve registrar a coleção de esquema XML usando [CREATE XML schema Collection &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="27def-137">Before you can create typed `xml` variables, parameters, or columns, you must first register the XML schema collection by using [CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span></span> <span data-ttu-id="27def-138">Em seguida, você pode associar a coleção de esquema XML com variáveis, parâmetros ou colunas do tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="27def-138">You can then associate the XML schema collection with variables, parameters, or columns of the `xml` data type.</span></span>  
  
 <span data-ttu-id="27def-139">Nos exemplos a seguir, uma convenção de nomenclatura de duas partes é usada para especificar o nome da coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="27def-139">In the following examples, a two-part naming convention is used for specifying the XML schema collection name.</span></span> <span data-ttu-id="27def-140">A primeira parte é o nome do esquema e a segunda parte é o nome da coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="27def-140">The first part is the schema name, and the second part is the XML schema collection name.</span></span>  
  
### <a name="example-associating-a-schema-collection-with-an-xml-type-variable"></a><span data-ttu-id="27def-141">Exemplo: Associando uma coleção de esquemas com uma variável do tipo xml</span><span class="sxs-lookup"><span data-stu-id="27def-141">Example: Associating a Schema Collection with an xml Type Variable</span></span>  
 <span data-ttu-id="27def-142">O exemplo a seguir cria uma `xml` variável de tipo e associa uma coleção de esquema a ela.</span><span class="sxs-lookup"><span data-stu-id="27def-142">The following example creates an`xml` type variable and associates a schema collection with it.</span></span> <span data-ttu-id="27def-143">A coleção de esquema especificada no exemplo já está importada no banco de dados **AdventureWorks** .</span><span class="sxs-lookup"><span data-stu-id="27def-143">The schema collection specified in the example is already imported in the **AdventureWorks** database.</span></span>  
  
```  
DECLARE @x xml (Production.ProductDescriptionSchemaCollection);   
```  
  
### <a name="example-specifying-a-schema-for-an-xml-type-column"></a><span data-ttu-id="27def-144">Exemplo: Especificando um esquema para uma coluna do tipo xml</span><span class="sxs-lookup"><span data-stu-id="27def-144">Example: Specifying a Schema for an xml Type Column</span></span>  
 <span data-ttu-id="27def-145">O exemplo a seguir cria uma tabela com uma coluna de tipo `xml` e especifica um esquema para a coluna:</span><span class="sxs-lookup"><span data-stu-id="27def-145">The following example creates a table with an `xml` type column and specifies a schema for the column:</span></span>  
  
```  
CREATE TABLE T1(  
 Col1 int,   
 Col2 xml (Production.ProductDescriptionSchemaCollection)) ;  
```  
  
### <a name="example-passing-an-xml-type-parameter-to-a-stored-procedure"></a><span data-ttu-id="27def-146">Exemplo: Passando um parâmetro de tipo xml para um procedimento armazenado</span><span class="sxs-lookup"><span data-stu-id="27def-146">Example: Passing an xml Type Parameter to a Stored Procedure</span></span>  
 <span data-ttu-id="27def-147">O exemplo a seguir passa um parâmetro de tipo `xml` para um procedimento armazenado e especifica um esquema para a variável:</span><span class="sxs-lookup"><span data-stu-id="27def-147">The following example passes an `xml` type parameter to a stored procedure and specifies a schema for the variable:</span></span>  
  
```  
CREATE PROCEDURE SampleProc   
  @ProdDescription xml (Production.ProductDescriptionSchemaCollection)   
AS   
...  
```  
  
 <span data-ttu-id="27def-148">Observe o seguinte sobre a coleção de esquema XML:</span><span class="sxs-lookup"><span data-stu-id="27def-148">Note the following about the XML schema collection:</span></span>  
  
-   <span data-ttu-id="27def-149">Uma coleção de esquema XML está disponível apenas no banco de dados no qual ela foi registrada usando [Criando uma coleção de esquema XML](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="27def-149">An XML schema collection is available only in the database in which it was registered by using [Creating an XML Schema Collection](/sql/t-sql/statements/create-xml-schema-collection-transact-sql).</span></span>  
  
-   <span data-ttu-id="27def-150">Se você converter de um tipo de dados de cadeia de caracteres em `xml` com tipo, a análise também executará validação e classificação de tipo com base nos namespaces do esquema XML na coleção especificada.</span><span class="sxs-lookup"><span data-stu-id="27def-150">If you cast from a string to a typed `xml` data type, the parsing also performs validation and typing, based on the XML schema namespaces in the collection specified.</span></span>  
  
-   <span data-ttu-id="27def-151">Você pode converter de um tipo de dados `xml` com tipo em um tipo de dados `xml` sem-tipo e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="27def-151">You can cast from a typed `xml` data type to an untyped `xml` data type, and vice versa.</span></span>  
  
 <span data-ttu-id="27def-152">Para obter mais informações sobre outras maneiras de gerar XML no SQL Server, consulte [Criar instâncias de dados XML](create-instances-of-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="27def-152">For more information about other ways to generate XML in SQL Server, see [Create Instances of XML Data](create-instances-of-xml-data.md).</span></span> <span data-ttu-id="27def-153">Depois que o XML é gerado, ele pode ser atribuído a uma variável de tipo de dados `xml` ou armazenado em colunas de tipo `xml` para processamento adicional.</span><span class="sxs-lookup"><span data-stu-id="27def-153">After XML is generated, it can be assigned either to an `xml` data type variable or stored in `xml` type columns for additional processing.</span></span>  
  
 <span data-ttu-id="27def-154">Na hierarquia de tipo de dados, o tipo de dados `xml` aparece abaixo dos tipos de dados `sql_variant` e definidos pelo usuário, mas acima de qualquer tipo interno.</span><span class="sxs-lookup"><span data-stu-id="27def-154">In the data type hierarchy, the `xml` data type appears below `sql_variant` and user-defined types, but above any of the built-in types.</span></span>  
  
### <a name="example-specifying-facets-to-constrain-a-typed-xml-column"></a><span data-ttu-id="27def-155">Exemplo: Especificando facetas para restringir uma coluna xml tipada</span><span class="sxs-lookup"><span data-stu-id="27def-155">Example: Specifying Facets to Constrain a Typed xml Column</span></span>  
 <span data-ttu-id="27def-156">Para colunas `xml` com tipo, é possível restringir a coluna para permitir que apenas elementos únicos de nível superior de cada instância sejam armazenados nela.</span><span class="sxs-lookup"><span data-stu-id="27def-156">For typed `xml` columns, you can constrain the column to allow only single, top-level elements for each instance stored in it.</span></span> <span data-ttu-id="27def-157">Isso é feito especificando a faceta opcional `DOCUMENT` ao criar uma tabela, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="27def-157">You do this by specifying the optional `DOCUMENT` facet when a table is created, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T(Col1 xml   
   (DOCUMENT Production.ProductDescriptionSchemaCollection));  
GO  
DROP TABLE T;  
GO  
```  
  
 <span data-ttu-id="27def-158">Por padrão, instâncias armazenadas na coluna `xml` com tipo são armazenadas como conteúdo XML e não como documentos XML.</span><span class="sxs-lookup"><span data-stu-id="27def-158">By default, instances stored in the typed `xml` column are stored as XML content and not as XML documents.</span></span> <span data-ttu-id="27def-159">Isto permite o seguinte:</span><span class="sxs-lookup"><span data-stu-id="27def-159">This allows for the following:</span></span>  
  
-   <span data-ttu-id="27def-160">Zero ou muitos elementos de nível superior</span><span class="sxs-lookup"><span data-stu-id="27def-160">Zero or many top-level elements</span></span>  
  
-   <span data-ttu-id="27def-161">Nós de texto em elementos de nível superior</span><span class="sxs-lookup"><span data-stu-id="27def-161">Text nodes in top-level elements</span></span>  
  
 <span data-ttu-id="27def-162">Você também pode especificar explicitamente esse comportamento adicionando a faceta `CONTENT` , conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="27def-162">You can also explicitly specify this behavior by adding `CONTENT` facet, as shown in the following example:</span></span>  
  
```  
CREATE TABLE T(Col1 xml(CONTENT Production.ProductDescriptionSchemaCollection));  
GO -- Default  
```  
  
 <span data-ttu-id="27def-163">Observe que você pode especificar as facetas opcionais DOCUMENT/CONTENT em qualquer lugar em que define tipo `xml` (xml com tipo).</span><span class="sxs-lookup"><span data-stu-id="27def-163">Note that you can specify the optional DOCUMENT/CONTENT facets anywhere you define `xml` type (typed xml).</span></span> <span data-ttu-id="27def-164">Quando você cria uma variável `xml` com tipo, pode adicionar a faceta DOCUMENT/CONTENT, conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="27def-164">For example, when you create a typed `xml` variable, you can add the DOCUMENT/CONTENT facet, as shown in the following:</span></span>  
  
```  
declare @x xml (DOCUMENT Production.ProductDescriptionSchemaCollection);  
```  
  
## <a name="document-type-definition-dtd"></a><span data-ttu-id="27def-165">DTD (Definição de Tipo de Documento)</span><span class="sxs-lookup"><span data-stu-id="27def-165">Document Type Definition (DTD)</span></span>  
 <span data-ttu-id="27def-166">As colunas, variáveis e parâmetros de tipo de dados `xml`podem ter o tipo definido usando esquema XML, mas não usando DTD.</span><span class="sxs-lookup"><span data-stu-id="27def-166">The `xml` data type columns, variables, and parameters can be typed by using XML schema, but not by using DTD.</span></span> <span data-ttu-id="27def-167">No entanto DTD embutido pode ser usado para XML com tipo e sem-tipo para fornecer valores padrão e para substituir referências a entidades com seus formulários expandidos.</span><span class="sxs-lookup"><span data-stu-id="27def-167">However, inline DTD can be used for both untyped and typed XML to supply default values and to replace entity references with their expanded form.</span></span>  
  
 <span data-ttu-id="27def-168">É possível converter documentos de esquema DTD em XML usando ferramentas de terceiros e carregar os esquemas XML no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="27def-168">You can convert DTDs to XML schema documents by using third-party tools, and load the XML schemas into the database.</span></span>  
  
## <a name="upgrading-typed-xml-from-sql-server-2005"></a><span data-ttu-id="27def-169">Atualizando XML com tipo a partir do SQL Server 2005</span><span class="sxs-lookup"><span data-stu-id="27def-169">Upgrading Typed XML from SQL Server 2005</span></span>  
 [!INCLUDE[ssKatmai](../../includes/sskatmai-md.md)] <span data-ttu-id="27def-170">fez várias extensões ao suporte do Esquema XML, incluindo suporte para validação incerta, manipulação melhorada de dados das instâncias **xs:date**, **xs:time** e **xs:dateTime** e suporte adicionado para tipos de lista e de união.</span><span class="sxs-lookup"><span data-stu-id="27def-170">made several extensions to the XML Schema support, including support for lax validation, improved handling of **xs:date**, **xs:time** and **xs:dateTime** instance data, and added support for list and union types.</span></span> <span data-ttu-id="27def-171">Na maior parte dos casos, as alterações não afetam a experiência de atualização.</span><span class="sxs-lookup"><span data-stu-id="27def-171">In most cases the changes do not affect the upgrade experience.</span></span> <span data-ttu-id="27def-172">No entanto, se você usou uma coleção de Esquemas XML no [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] que permitiu valores do tipo **xs:date**, **xs:time**ou **xs:dateTime** (ou qualquer subtipo), as seguintes etapas de atualização ocorrerão quando você anexar o banco de dados do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] a uma versão posterior do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="27def-172">However if you used an XML Schema collection in [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] that allowed values of type **xs:date**, **xs:time**, or **xs:dateTime** (or any subtype) then the following upgrade steps occur when you attach your [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] database to a later version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]:</span></span>  
  
1.  <span data-ttu-id="27def-173">Para cada coluna XML que recebe tipo com uma Coleção de Esquema XML que contém elementos ou atributos que recebem o tipo de **xs:anyType**, **xs:anySimpleType**, **xs:date** ou qualquer um de seus subtipos, **xs:time** ou qualquer um de seus subtipos, ou **xs:dateTime** ou qualquer um de seus subtipos, ou são de tipo de união ou de lista contendo qualquer um desses tipos, ocorre o seguinte:</span><span class="sxs-lookup"><span data-stu-id="27def-173">For every XML column, that is typed with an XML Schema Collection that contains elements or attributes that are typed as either **xs:anyType**, **xs:anySimpleType**, **xs:date** or any of its subtypes, **xs:time** or any subtype thereof, or **xs:dateTime** or any of its subtypes, or are union or list types containing any of these types the following occurs:</span></span>  
  
    1.  <span data-ttu-id="27def-174">Todos os índices XML da coluna serão desabilitados.</span><span class="sxs-lookup"><span data-stu-id="27def-174">All XML indices on the column will be disabled.</span></span>  
  
    2.  <span data-ttu-id="27def-175">Todos os valores do [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] continuarão a ser representados no fuso horário Z, pois foram normalizados para o fuso horário Z.</span><span class="sxs-lookup"><span data-stu-id="27def-175">All [!INCLUDE[ssVersion2005](../../includes/ssversion2005-md.md)] values will continue to be represented in the Z timezone, because they have been normalized to the Z timezone.</span></span>  
  
    3.  <span data-ttu-id="27def-176">Quaisquer valores de **xs:date** ou **xs:dateTime** menores que 1º de janeiro do ano 1 resultarão em um erro de runtime quando o índice for reconstruído ou uma instrução XQuery ou XML-DML for executada em relação ao tipo de dados XML que contém esse valor.</span><span class="sxs-lookup"><span data-stu-id="27def-176">Any **xs:date** or **xs:dateTime** values that are smaller than January 1st of year 1 will lead to a runtime error when the index gets rebuild or an XQuery or XML-DML statements gets executed against the XML data type containing that value.</span></span>  
  
2.  <span data-ttu-id="27def-177">Quaisquer anos negativos nas facetas **xs:date** ou **xs:dateTime** ou valores padrão em uma coleção de esquema XML serão atualizados automaticamente para o menor valor permitido pelo tipo **xs:date** ou **xs:dateTime** (por exemplo, 0001-01-01T00:00:00.0000000Z para **xs:dateTime**).</span><span class="sxs-lookup"><span data-stu-id="27def-177">Any negative years in **xs:date** or **xs:dateTime** facets or default values in an XML Schema collection will automatically be updated to the smallest value allowed by the base **xs:date** or **xs:dateTime** type (e.g., 0001-01-01T00:00:00.0000000Z for **xs:dateTime**).</span></span>  
  
 <span data-ttu-id="27def-178">Observe que você ainda pode usar uma instrução select SQL simples para recuperar o tipo de dados XML inteiro, mesmo que ele contenha anos negativos.</span><span class="sxs-lookup"><span data-stu-id="27def-178">Note that you can still use a simple SQL select statement to retrieve the whole XML data type, even if it contains negative years.</span></span> <span data-ttu-id="27def-179">É recomendável substituir anos negativos por um ano dentro do intervalo com suporte recente ou alterar o tipo do elemento ou atributo para **xs:string**.</span><span class="sxs-lookup"><span data-stu-id="27def-179">It is recommended that you replace negative years with a year within the newly supported range or change the type of the element or attribute to **xs:string**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="27def-180">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="27def-180">See Also</span></span>  
 <span data-ttu-id="27def-181">[Criar instâncias de dados XML](create-instances-of-xml-data.md) </span><span class="sxs-lookup"><span data-stu-id="27def-181">[Create Instances of XML Data](create-instances-of-xml-data.md) </span></span>  
 <span data-ttu-id="27def-182">[Métodos de tipos de dados xml](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="27def-182">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="27def-183">[Linguagem de modificação de dados XML &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span><span class="sxs-lookup"><span data-stu-id="27def-183">[XML Data Modification Language &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span></span>  
 [<span data-ttu-id="27def-184">Dados XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="27def-184">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
