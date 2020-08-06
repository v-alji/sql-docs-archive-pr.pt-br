---
title: Criar instâncias de dados XML | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- type casting string instances [XML in SQL Server]
- XML [SQL Server], typed
- xml data type [SQL Server], generating instances
- casting string instances [XML in SQL Server]
- typed XML
- generating XML instances [SQL Server]
- XML [SQL Server], generating instances
- white space [XML in SQL Server]
ms.assetid: dbd6c06f-db6e-44a7-855a-6a55bf374907
author: rothja
ms.author: jroth
ms.openlocfilehash: c857b9ebbe559de34fdac925642f9270d9cbf936
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686203"
---
# <a name="create-instances-of-xml-data"></a><span data-ttu-id="bb9a1-102">Criar instâncias de dados XML</span><span class="sxs-lookup"><span data-stu-id="bb9a1-102">Create Instances of XML Data</span></span>
  <span data-ttu-id="bb9a1-103">Este tópico descreve como gerar instâncias XML.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-103">This topic describes how to generate XML instances.</span></span>  
  
 <span data-ttu-id="bb9a1-104">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], você pode gerar instâncias XML das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-104">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], you can generate XML instances in the following ways:</span></span>  
  
-   <span data-ttu-id="bb9a1-105">Instâncias de cadeia de caracteres de conversão de tipos.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-105">Type casting string instances.</span></span>  
  
-   <span data-ttu-id="bb9a1-106">Usando a instrução SELECT com a cláusula FOR XML.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-106">Using the SELECT statement with the FOR XML clause.</span></span>  
  
-   <span data-ttu-id="bb9a1-107">Usando atribuições de constantes.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-107">Using constant assignments.</span></span>  
  
-   <span data-ttu-id="bb9a1-108">Usando carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-108">Using bulk load.</span></span>  
  
## <a name="type-casting-string-and-binary-instances"></a><span data-ttu-id="bb9a1-109">Instâncias de cadeia de caracteres de conversão de tipos e binárias</span><span class="sxs-lookup"><span data-stu-id="bb9a1-109">Type Casting String and Binary Instances</span></span>  
 <span data-ttu-id="bb9a1-110">Você pode analisar qualquer um dos [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tipos de dados de cadeia de caracteres, como [**n**] [**var**]**Char**, **[n] Text**, **varbinary**e **Image**, no `xml` tipo de dados por conversão (CAST) ou convertendo (Convert) a cadeia de caracteres para o `xml` tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-110">You can parse any of the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] string data types, such as [**n**][**var**]**char**, **[n]text**, **varbinary**,and **image**, into the `xml` data type by casting (CAST) or converting (CONVERT) the string to the `xml` data type.</span></span> <span data-ttu-id="bb9a1-111">XML sem-tipo é verificado para confirmar se está bem formado.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-111">Untyped XML is checked to confirm that it is well formed.</span></span> <span data-ttu-id="bb9a1-112">Se houver um esquema associado ao `xml` tipo, a validação também será executada.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-112">If there is a schema associated with the `xml` type, validation is also performed.</span></span> <span data-ttu-id="bb9a1-113">Para obter mais informações, consulte [Comparar XML digitado com XML não digitado](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bb9a1-113">For more information, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
 <span data-ttu-id="bb9a1-114">Documentos de XML podem ser codificados com diferentes codificações (por exemplo, UTF-8, UTF-16, Windows-1252).</span><span class="sxs-lookup"><span data-stu-id="bb9a1-114">XML documents can be encoded with different encodings (for example, UTF-8, UTF-16, windows-1252).</span></span> <span data-ttu-id="bb9a1-115">O seguinte descreve as regras de como os tipos de origem de cadeia de caracteres e binários interagem com a codificação do documento XML e como o analisador se comporta.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-115">The following outlines the rules on how the string and binary source types interact with the XML document encoding and how the parser behaves.</span></span>  
  
 <span data-ttu-id="bb9a1-116">Como **nvarchar** pressupõe uma codificação Unicode de dois bytes, como UTF-16 ou UCS-2, o analisador XML tratará o valor da cadeia de caracteres como um documento ou fragmento XML codificado em Unicode de dois bytes.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-116">Since **nvarchar** assumes a two-byte unicode encoding such as UTF-16 or UCS-2, the XML parser will treat the string value as a two-byte Unicode encoded XML document or fragment.</span></span> <span data-ttu-id="bb9a1-117">Isso indica que o documento XML precisa ser codificado em uma codificação Unicode bem como ser compatível com o tipo de dados da origem</span><span class="sxs-lookup"><span data-stu-id="bb9a1-117">This means that the XML document needs to be encoded in a two-byte Unicode encoding as well to be compatible with the source data type.</span></span> <span data-ttu-id="bb9a1-118">Um documento XML codificado em UTF-16 pode ter uma BOM (marca de ordem de byte), mas isso não é necessário, pois o contexto do tipo de origem torna claro que ele pode ser apenas um documento codificado em Unicode de dois bytes.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-118">A UTF-16 encoded XML document can have a UTF-16 byte order mark (BOM), but it does not need to, since the context of the source type makes it clear that it can only be a two-byte Unicode encoded document.</span></span>  
  
 <span data-ttu-id="bb9a1-119">O conteúdo de uma cadeia de caracteres **varchar** é tratado como um documento/fragmento XML codificado em um byte pelo analisador XML.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-119">The content of a **varchar** string is treated as a one-byte encoded XML document/fragment by the XML parser.</span></span> <span data-ttu-id="bb9a1-120">Como a cadeia de caracteres de origem **varchar** tem uma página de código associada, o analisador usará essa página de código para a codificação, se nenhuma codificação explícita for especificada no próprio XML. Se uma instância XML tiver uma BOM ou uma declaração de codificação, a BOM ou declaração precisará ser consistente com a página de código, caso contrário o analisador relatará um erro.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-120">Since the **varchar** source string has a code page associated, the parser will use that code page for the encoding if no explicit encoding is specified in the XML itself If an XML instance has a BOM or an encoding declaration, the BOM or declaration needs to be consistent with the code page, otherwise the parser will report an error.</span></span>  
  
 <span data-ttu-id="bb9a1-121">O conteúdo de **varbinary** é tratado como um fluxo de codepoint que é passado diretamente ao analisador XML.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-121">The content of **varbinary** is treated as a codepoint stream that is passed directly to the XML parser.</span></span> <span data-ttu-id="bb9a1-122">Assim, o documento ou fragmento XML precisa fornecer a BOM ou outras informações embutidas de codificação.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-122">Thus, the XML document or fragment needs to provide the BOM or other encoding information inline.</span></span> <span data-ttu-id="bb9a1-123">O analisador examinará o fluxo apenas para determinar a codificação.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-123">The parser will only look at the stream to determine the encoding.</span></span> <span data-ttu-id="bb9a1-124">Isso significa que XML codificado em UTF-16 precisa fornecer a BOM de UTF-16 e que uma instância sem BOM e sem uma codificação de declaração será interpretada como UTF-8.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-124">This means that UTF-16 encoded XML needs to provide the UTF-16 BOM and an instance without BOM and without a declaration encoding will be interpreted as UTF-8.</span></span>  
  
 <span data-ttu-id="bb9a1-125">Se a codificação do documento XML não for conhecida antecipadamente e os dados forem passados como cadeias de caracteres ou binários em vez de dados XML antes da conversão em XML, será recomendável tratar os dados como **varbinary**.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-125">If the encoding of the XML document is not known in advance and the data is passed as string or binary data instead of XML data before casting to XML, it is recommended to treat the data as **varbinary**.</span></span> <span data-ttu-id="bb9a1-126">Por exemplo, ao ler dados de um arquivo XML usando OpenRowset(), deve-se especificar os dados a serem lidos como um valor **varbinary(max)** :</span><span class="sxs-lookup"><span data-stu-id="bb9a1-126">For example, when reading data from an XML file using OpenRowset(), one should specify the data to be read as a **varbinary(max)** value:</span></span>  
  
```  
select CAST(x as XML)   
from OpenRowset(BULK 'filename.xml', SINGLE_BLOB) R(x)  
```  
  
 [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="bb9a1-127">representa XML internamente em uma representação binária eficiente que usa codificação UTF-16.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-127">internally represents XML in an efficient binary representation that uses UTF-16 encoding.</span></span> <span data-ttu-id="bb9a1-128">A codificação fornecida pelo usuário não é preservada, mas é considerada durante o processo de análise.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-128">User-provided encoding is not preserved, but is considered during the parse process.</span></span>  
  
### <a name="type-casting-clr-user-defined-types"></a><span data-ttu-id="bb9a1-129">Tipos de dado CLR definidos pelo usuário para conversão de tipo</span><span class="sxs-lookup"><span data-stu-id="bb9a1-129">Type Casting CLR user-defined types</span></span>  
 <span data-ttu-id="bb9a1-130">Se um tipo de dado CLR definido pelo usuário tiver uma serialização XML, as instâncias daquele tipo poderão ser convertidas explicitamente em um tipo de dados XML.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-130">If a CLR user-defined type has an XML Serialization, instances of that type can be explicitly cast to an XML datatype.</span></span> <span data-ttu-id="bb9a1-131">Para obter mais detalhes sobre serialização XML de um tipo da dado CLR definido pelo usuário, consulte [Serialização XML de objetos de banco de dados CLR](../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md).</span><span class="sxs-lookup"><span data-stu-id="bb9a1-131">For more details about the XML serialization of a CLR user-defined typed, see [XML Serialization from CLR Database Objects](../../database-engine/dev-guide/xml-serialization-from-clr-database-objects.md).</span></span>  
  
### <a name="white-space-handling-in-typed-xml"></a><span data-ttu-id="bb9a1-132">Tratamento de espaço em branco em XML com tipo</span><span class="sxs-lookup"><span data-stu-id="bb9a1-132">White Space Handling in Typed XML</span></span>  
 <span data-ttu-id="bb9a1-133">No [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], espaço em branco dentro do conteúdo do elemento será considerado insignificante se ele ocorrer dentro de uma sequência de dados de caracteres de apenas espaço em branco delimitada por marcação, como marcas de início e de fim, e não tiver a entidade definida.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-133">In [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], white space inside element content is considered insignificant if it occurs inside a sequence of white-space-only character data delimited by markup, such as begin or end tags, and is not entitized.</span></span> <span data-ttu-id="bb9a1-134">(Seções de CDATA são ignoradas.) Esse tratamento de espaço em branco é diferente de como o espaço em branco é descrito na especificação do XML 1.0 publicada pelo World Wide Web Consortium (W3C).</span><span class="sxs-lookup"><span data-stu-id="bb9a1-134">(CDATA sections are ignored.) This handling of white space handling is different from how white space is described in the XML 1.0 specification published by the World Wide Web Consortium (W3C).</span></span> <span data-ttu-id="bb9a1-135">Isso é porque o analisador XML no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] reconhece apenas um número limitado de subconjuntos de DTD, conforme definido no XML 1.0.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-135">This is because the XML parser in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] recognizes only a limited number of DTD subsets, as defined in XML 1.0.</span></span> <span data-ttu-id="bb9a1-136">Para obter mais informações sobre os subconjuntos de DTD limitados que têm suporte no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [CAST e CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bb9a1-136">For more information about the limited DTD subsets supported in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
 <span data-ttu-id="bb9a1-137">Por padrão, o analisador XML descarta espaço em branco insignificante quando converte dados de cadeia de caracteres em XML se uma das seguintes situações for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-137">By default, the XML parser discards insignificant white space when it converts string data to XML if either of the following is true:</span></span>  
  
-   <span data-ttu-id="bb9a1-138">`The xml:space` o atributo não está definido em um elemento ou em seus elementos ancestrais.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-138">`The xml:space` attribute is not defined on an element or its ancestor elements.</span></span>  
  
-   <span data-ttu-id="bb9a1-139">O atributo `xml:space` em efeito em um elemento ou em um de seus elementos ancestrais tem o valor de padrão.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-139">The `xml:space` attribute in effect on an element, or one of its ancestor elements, has the value of default.</span></span>  
  
 <span data-ttu-id="bb9a1-140">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-140">For example:</span></span>  
  
```  
declare @x xml  
set @x = '<root>      <child/>     </root>'  
select @x   
```  
  
 <span data-ttu-id="bb9a1-141">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-141">This is the result:</span></span>  
  
```  
<root><child/></root>  
```  
  
 <span data-ttu-id="bb9a1-142">Porém, é possível alterar esse comportamento.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-142">However, you can change this behavior.</span></span> <span data-ttu-id="bb9a1-143">Para preservar espaço em branco para uma instância DT XML, use o operador CONVERT e seu parâmetro opcional *style* definido como um valor de 1.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-143">To preserve white space for an xml DT instance, use the CONVERT operator and its optional *style* parameter set to a value of 1.</span></span> <span data-ttu-id="bb9a1-144">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-144">For example:</span></span>  
  
```  
SELECT CONVERT(xml, N'<root>      <child/>     </root>', 1)  
```  
  
 <span data-ttu-id="bb9a1-145">Se o parâmetro *style* não for usado ou seu valor estiver definido como 0, espaço em branco insignificante não será preservado para a conversão da instância DT xml.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-145">If the *style* parameter is either not used or its value is set to 0, insignificant white space is not preserved for the conversion of the xml DT instance.</span></span> <span data-ttu-id="bb9a1-146">Para obter mais informações sobre como usar o operador CONVERT e seu parâmetro *style* ao converter dados de cadeia de caracteres em instâncias DT xml, consulte [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="bb9a1-146">For more information about how to use the CONVERT operator and its *style* parameter when converting string data to xml DT instances, see [CAST and CONVERT &#40;Transact-SQL&#41;](/sql/t-sql/functions/cast-and-convert-transact-sql).</span></span>  
  
### <a name="example-cast-a-string-value-to-typed-xml-and-assign-it-to-a-column"></a><span data-ttu-id="bb9a1-147">Exemplo: Converter um valor de cadeia de caracteres em xml tipado e atribuí-lo a uma coluna</span><span class="sxs-lookup"><span data-stu-id="bb9a1-147">Example: Cast a string value to typed xml and assign it to a column</span></span>  
 <span data-ttu-id="bb9a1-148">O exemplo a seguir converte uma variável de cadeia de caracteres que contém um fragmento XML para o `xml` tipo de dados e, em seguida, armazena-a na `xml` coluna tipo:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-148">The following example casts a string variable that contains an XML fragment to the `xml` data type and then stores it in the `xml` type column:</span></span>  
  
```  
CREATE TABLE T(c1 int primary key, c2 xml)  
go  
DECLARE  @s varchar(100)  
SET @s = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
```  
  
 <span data-ttu-id="bb9a1-149">A seguinte operação de inserção implicitamente converte de uma cadeia de caracteres para o `xml` tipo:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-149">The following insert operation implicitly converts from a string to the `xml` type:</span></span>  
  
```  
INSERT INTO T VALUES (3, @s)   
```  
  
 <span data-ttu-id="bb9a1-150">Você pode converter explicitamente () a cadeia de caracteres para o `xml` tipo:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-150">You can explicitly cast() the string to the `xml` type:</span></span>  
  
```  
INSERT INTO T VALUES (3, cast (@s as xml))  
```  
  
 <span data-ttu-id="bb9a1-151">Ou é possível usar convert(), conforme mostrado a seguir:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-151">Or you can use convert(), as shown in the following:</span></span>  
  
```  
INSERT INTO T VALUES (3, convert (xml, @s))   
```  
  
### <a name="example-convert-a-string-to-typed-xml-and-assign-it-to-a-variable"></a><span data-ttu-id="bb9a1-152">Exemplo: Converter uma cadeia de caracteres em xml tipado e atribuí-lo a uma variável</span><span class="sxs-lookup"><span data-stu-id="bb9a1-152">Example: Convert a string to typed xml and assign it to a variable</span></span>  
 <span data-ttu-id="bb9a1-153">No exemplo a seguir, uma cadeia de caracteres é convertida em `xml` tipo e atribuída a uma variável do `xml` tipo de dados:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-153">In the following example, a string is converted to `xml` type and assigned to a variable of the `xml` data type:</span></span>  
  
```  
declare @x xml  
declare  @s varchar(100)  
SET @s = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
set @x =convert (xml, @s)  
select @x  
```  
  
## <a name="using-the-select-statement-with-a-for-xml-clause"></a><span data-ttu-id="bb9a1-154">Usando a instrução SELECT com a cláusula FOR XML</span><span class="sxs-lookup"><span data-stu-id="bb9a1-154">Using the SELECT Statement with a FOR XML Clause</span></span>  
 <span data-ttu-id="bb9a1-155">É possível usar a cláusula FOR XML em uma instrução SELECT para retornar resultados como XML.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-155">You can use the FOR XML clause in a SELECT statement to return results as XML.</span></span> <span data-ttu-id="bb9a1-156">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-156">For example:</span></span>  
  
```  
DECLARE @xmlDoc xml  
SET @xmlDoc = (SELECT Column1, Column2  
               FROM   Table1, Table2  
               WHERE   Some condition  
               FOR XML AUTO)  
 ...  
```  
  
 <span data-ttu-id="bb9a1-157">A instrução SELECT retorna um fragmento XML textual que é então analisado durante a atribuição para a `xml` variável de tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-157">The SELECT statement returns a textual XML fragment that is then parsed during the assignment to the `xml` data type variable.</span></span>  
  
 <span data-ttu-id="bb9a1-158">Você também pode usar a [diretiva Type](type-directive-in-for-xml-queries.md) na cláusula for XML que retorna diretamente um resultado de consulta for XML como `xml` tipo:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-158">You can also use the [TYPE directive](type-directive-in-for-xml-queries.md) in the FOR XML clause that directly returns a FOR XML query result as `xml` type:</span></span>  
  
```  
Declare @xmlDoc xml  
SET @xmlDoc = (SELECT ProductModelID, Name  
               FROM   Production.ProductModel  
               WHERE  ProductModelID=19  
               FOR XML AUTO, TYPE)  
SELECT @xmlDoc  
```  
  
 <span data-ttu-id="bb9a1-159">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-159">This is the result:</span></span>  
  
```  
<Production.ProductModel ProductModelID="19" Name="Mountain-100" />...  
```  
  
 <span data-ttu-id="bb9a1-160">No exemplo a seguir, o resultado digitado `xml` de uma consulta for XML é inserido em uma `xml` coluna de tipo:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-160">In the following example, the typed `xml` result of a FOR XML query is inserted into an `xml` type column:</span></span>  
  
```  
CREATE TABLE T1 (c1 int, c2 xml)  
go  
INSERT T1(c1, c2)  
SELECT 1, (SELECT ProductModelID, Name  
           FROM Production.ProductModel  
           WHERE ProductModelID=19  
           FOR XML AUTO, TYPE)  
SELECT * FROM T1  
go  
```  
  
 <span data-ttu-id="bb9a1-161">Para obter mais informações sobre FOR XML, consulte [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bb9a1-161">For more information about FOR XML, see [FOR XML &#40;SQL Server&#41;](for-xml-sql-server.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="bb9a1-162">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retorna instâncias de tipo de dados `xml`ao cliente como um resultado das diferentes construções do servidor como consultas FOR XML que usam a diretiva TYPE ou onde o tipo de dados `xml` é usado para retornar XML de colunas, variáveis e parâmetros de saída SQL.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-162">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns `xml` data type instances to the client as a result of different server constructs such as FOR XML queries that use the TYPE directive, or where the `xml` data type is used to return XML from SQL columns, variables, and output parameters.</span></span> <span data-ttu-id="bb9a1-163">No código do aplicativo cliente, o provedor ADO.NET solicita que essas informações de tipo de dados `xml` sejam enviadas em uma codificação binária do servidor.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-163">In client application code, the ADO.NET provider requests that this `xml` data type information be sent in a binary encoding from the server.</span></span> <span data-ttu-id="bb9a1-164">Porém, se você estiver usando FOR XML sem a diretiva TYPE, os dados XML retornarão como um tipo de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-164">However, if you are using FOR XML without the TYPE directive, the XML data returns as a string type.</span></span> <span data-ttu-id="bb9a1-165">De qualquer forma, o provedor cliente sempre poderá controlar qualquer formulário de XML.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-165">In any case, the client provider will always be able to handle either form of XML.</span></span>  
  
## <a name="using-constant-assignments"></a><span data-ttu-id="bb9a1-166">Usando atribuições de constantes</span><span class="sxs-lookup"><span data-stu-id="bb9a1-166">Using Constant Assignments</span></span>  
 <span data-ttu-id="bb9a1-167">Uma constante de cadeia de caracteres pode ser usada onde uma instância do `xml` tipo de dados é esperada.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-167">A string constant can be used where an instance of the `xml` data type is expected.</span></span> <span data-ttu-id="bb9a1-168">Isso é o mesmo que uma CAST implícita de cadeia de caracteres em XML.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-168">This is the same as an implied CAST of string to XML.</span></span> <span data-ttu-id="bb9a1-169">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-169">For example:</span></span>  
  
```  
DECLARE @xmlDoc xml  
SET @xmlDoc = '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>'   
-- Or  
SET @xmlDoc = N'<?xml version="1.0" encoding="ucs-2"?><doc/>'  
```  
  
 <span data-ttu-id="bb9a1-170">O exemplo anterior converte implicitamente a cadeia de caracteres no `xml` tipo de dados e a atribui a uma `xml` variável de tipo.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-170">The previous example implicitly converts the string to the `xml` data type and assigns it to an `xml` type variable.</span></span>  
  
 <span data-ttu-id="bb9a1-171">O exemplo a seguir insere uma cadeia de caracteres constante em uma `xml` coluna de tipo:</span><span class="sxs-lookup"><span data-stu-id="bb9a1-171">The following example inserts a constant string into an `xml` type column:</span></span>  
  
```  
CREATE TABLE T(c1 int primary key, c2 xml)  
INSERT INTO T VALUES (3, '<Cust><Fname>Andrew</Fname><Lname>Fuller</Lname></Cust>')   
```  
  
> [!NOTE]  
>  <span data-ttu-id="bb9a1-172">Para XML com tipo, o XML é validado em relação ao esquema especificado.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-172">For typed XML, the XML is validated against the specified schema.</span></span> <span data-ttu-id="bb9a1-173">Para obter mais informações, consulte [Comparar XML digitado com XML não digitado](compare-typed-xml-to-untyped-xml.md).</span><span class="sxs-lookup"><span data-stu-id="bb9a1-173">For more information, see [Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md).</span></span>  
  
## <a name="using-bulk-load"></a><span data-ttu-id="bb9a1-174">Usando carregamento em massa</span><span class="sxs-lookup"><span data-stu-id="bb9a1-174">Using Bulk Load</span></span>  
 <span data-ttu-id="bb9a1-175">A funcionalidade [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) aprimorada permite carregar documentos XML em massa no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-175">The enhanced [OPENROWSET (Transact-SQL)](/sql/t-sql/functions/openrowset-transact-sql) functionality allows you to bulk load XML documents in the database.</span></span> <span data-ttu-id="bb9a1-176">Você pode carregar em massa instâncias XML de arquivos para as `xml` colunas de tipo no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-176">You can bulk load XML instances from files into the `xml` type columns in the database.</span></span> <span data-ttu-id="bb9a1-177">Para obter exemplos de funcionamento, consulte [Exemplos de importação e exportação em massa de documentos XML &#40;SQL Server&#41;](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="bb9a1-177">For working samples, see [Examples of Bulk Import and Export of XML Documents &#40;SQL Server&#41;](../import-export/examples-of-bulk-import-and-export-of-xml-documents-sql-server.md).</span></span> <span data-ttu-id="bb9a1-178">Para obter mais informações sobre carregamento de documentos XML, consulte [Carregar dados XML](load-xml-data.md).</span><span class="sxs-lookup"><span data-stu-id="bb9a1-178">For more information about loading XML documents, see [Load XML Data](load-xml-data.md).</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="bb9a1-179">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="bb9a1-179">In This Section</span></span>  
  
|<span data-ttu-id="bb9a1-180">Tópico</span><span class="sxs-lookup"><span data-stu-id="bb9a1-180">Topic</span></span>|<span data-ttu-id="bb9a1-181">Descrição</span><span class="sxs-lookup"><span data-stu-id="bb9a1-181">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="bb9a1-182">Recuperar e consultar dados XML</span><span class="sxs-lookup"><span data-stu-id="bb9a1-182">Retrieve and Query XML Data</span></span>](retrieve-and-query-xml-data.md)|<span data-ttu-id="bb9a1-183">Descreve as partes de instâncias XML que não são preservadas quando são armazenadas em bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="bb9a1-183">Describes the parts of XML instances that are not preserved when they are stored in databases.</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="bb9a1-184">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="bb9a1-184">See Also</span></span>  
 <span data-ttu-id="bb9a1-185">[Comparar XML digitado com XML não digitado](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="bb9a1-185">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="bb9a1-186">[Métodos de tipos de dados xml](/sql/t-sql/xml/xml-data-type-methods) </span><span class="sxs-lookup"><span data-stu-id="bb9a1-186">[xml Data Type Methods](/sql/t-sql/xml/xml-data-type-methods) </span></span>  
 <span data-ttu-id="bb9a1-187">[Linguagem de modificação de dados XML &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span><span class="sxs-lookup"><span data-stu-id="bb9a1-187">[XML Data Modification Language &#40;XML DML&#41;](/sql/t-sql/xml/xml-data-modification-language-xml-dml) </span></span>  
 [<span data-ttu-id="bb9a1-188">Dados XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="bb9a1-188">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
