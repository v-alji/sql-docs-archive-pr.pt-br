---
title: 'Coerção de tipo de dados e a anotação sql: DataType (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- mapping data types [SQLXML]
- type attribute
- sql:datatype
- data types [SQLXML], converting
- annotated XSD schemas, mapping data types
- xsd:type
- datatype annotation
- converting data types [SQLXML]
- data types [SQLXML], mapping data types
- XSD schemas [SQLXML], mapping data types
ms.assetid: db192105-e8aa-4392-b812-9d727918c005
author: rothja
ms.author: jroth
ms.openlocfilehash: 22f1b0af93e3b596d74bc107ab6947b9855a2cf6
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573907"
---
# <a name="data-type-coercions-and-the-sqldatatype-annotation-sqlxml-40"></a><span data-ttu-id="5aee0-102">Coerções de tipo de dados e a anotação de sql:datatype (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="5aee0-102">Data Type Coercions and the sql:datatype Annotation (SQLXML 4.0)</span></span>
  <span data-ttu-id="5aee0-103">Em um esquema XSD, o atributo `xsd:type` especifica o tipo de dados XSD de um elemento ou atributo.</span><span class="sxs-lookup"><span data-stu-id="5aee0-103">In an XSD schema, the `xsd:type` attribute specifies the XSD data type of an element or attribute.</span></span> <span data-ttu-id="5aee0-104">Quando um esquema XSD é usado para extrair dados do banco de dados, o tipo de dados especificado é usado para formatar os dados.</span><span class="sxs-lookup"><span data-stu-id="5aee0-104">When an XSD schema is used to extract data from the database, the data type specified is used to format the data.</span></span>  
  
 <span data-ttu-id="5aee0-105">Além de especificar um tipo XSD em um esquema, você pode especificar também um tipo de dados do Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando a anotação `sql:datatype`.</span><span class="sxs-lookup"><span data-stu-id="5aee0-105">In addition to specifying an XSD type in a schema, you can also specify a Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type by using the `sql:datatype` annotation.</span></span> <span data-ttu-id="5aee0-106">Os atributos `xsd:type` e `sql:datatype` controlam o mapeamento entre os tipos de dados XSD e os tipos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5aee0-106">The `xsd:type` and `sql:datatype` attributes control the mapping between XSD data types and [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types.</span></span>  
  
## <a name="xsdtype-attribute"></a><span data-ttu-id="5aee0-107">Atributo xsd:type</span><span class="sxs-lookup"><span data-stu-id="5aee0-107">xsd:type Attribute</span></span>  
 <span data-ttu-id="5aee0-108">Você pode usar o atributo `xsd:type` para especificar o tipo de dados de XML de um atributo ou elemento que mapeia para uma coluna.</span><span class="sxs-lookup"><span data-stu-id="5aee0-108">You can use the `xsd:type` attribute to specify the XML data type of an attribute or element that maps to a column.</span></span> <span data-ttu-id="5aee0-109">O `xsd:type` afeta o documento que é retornado do servidor e também a consulta XPath que é executada.</span><span class="sxs-lookup"><span data-stu-id="5aee0-109">The `xsd:type` affects the document that is returned from the server and also the XPath query that is executed.</span></span> <span data-ttu-id="5aee0-110">Quando uma consulta XPath é executada sobre um esquema de mapeamento que contenha `xsd:type`, XPath usa o tipo de dados especificado ao processar a consulta.</span><span class="sxs-lookup"><span data-stu-id="5aee0-110">When an XPath query is executed against a mapping schema that contains `xsd:type`, XPath uses the specified data type when it processes the query.</span></span> <span data-ttu-id="5aee0-111">Para obter mais informações sobre como o XPath usa `xsd:type` , consulte [mapeando tipos de dados XSD para tipos de dados XPath &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5aee0-111">For more information about how XPath uses `xsd:type`, see [Mapping XSD Data Types to XPath Data Types &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/xpath-data-types-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="5aee0-112">Em um documento retornado, todos os tipos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] são convertidos em representações de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="5aee0-112">In a returned document, all [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types are converted into string representations.</span></span> <span data-ttu-id="5aee0-113">Alguns tipos de dados exigem conversões adicionais.</span><span class="sxs-lookup"><span data-stu-id="5aee0-113">Some data types require additional conversions.</span></span> <span data-ttu-id="5aee0-114">A tabela a seguir lista as conversões que são usadas para obter vários valores `xsd:type`.</span><span class="sxs-lookup"><span data-stu-id="5aee0-114">The following table lists the conversions that are used for various `xsd:type` values.</span></span>  
  
|<span data-ttu-id="5aee0-115">Tipo de dados XSD</span><span class="sxs-lookup"><span data-stu-id="5aee0-115">XSD data type</span></span>|<span data-ttu-id="5aee0-116">Conversão do SQL Server</span><span class="sxs-lookup"><span data-stu-id="5aee0-116">SQL Server conversion</span></span>|  
|-------------------|---------------------------|  
|<span data-ttu-id="5aee0-117">Boolean</span><span class="sxs-lookup"><span data-stu-id="5aee0-117">Boolean</span></span>|<span data-ttu-id="5aee0-118">CONVERT(bit, COLUMN)</span><span class="sxs-lookup"><span data-stu-id="5aee0-118">CONVERT(bit, COLUMN)</span></span>|  
|<span data-ttu-id="5aee0-119">Data</span><span class="sxs-lookup"><span data-stu-id="5aee0-119">Date</span></span>|<span data-ttu-id="5aee0-120">LEFT(CONVERT(nvarchar(4000), COLUMN, 126), 10)</span><span class="sxs-lookup"><span data-stu-id="5aee0-120">LEFT(CONVERT(nvarchar(4000), COLUMN, 126), 10)</span></span>|  
|<span data-ttu-id="5aee0-121">decimal</span><span class="sxs-lookup"><span data-stu-id="5aee0-121">decimal</span></span>|<span data-ttu-id="5aee0-122">CONVERT(money, COLUMN)</span><span class="sxs-lookup"><span data-stu-id="5aee0-122">CONVERT(money, COLUMN)</span></span>|  
|<span data-ttu-id="5aee0-123">id/idref/idrefs</span><span class="sxs-lookup"><span data-stu-id="5aee0-123">id/idref/idrefs</span></span>|<span data-ttu-id="5aee0-124">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span><span class="sxs-lookup"><span data-stu-id="5aee0-124">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span></span>|  
|<span data-ttu-id="5aee0-125">nmtoken/nmtokens</span><span class="sxs-lookup"><span data-stu-id="5aee0-125">nmtoken/nmtokens</span></span>|<span data-ttu-id="5aee0-126">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span><span class="sxs-lookup"><span data-stu-id="5aee0-126">id-prefix + CONVERT(nvarchar(4000), COLUMN, 126)</span></span>|  
|<span data-ttu-id="5aee0-127">Hora</span><span class="sxs-lookup"><span data-stu-id="5aee0-127">Time</span></span>|<span data-ttu-id="5aee0-128">SUBSTRING(CONVERT(nvarchar(4000), COLUMN, 126), 1+CHARINDEX(N'T', CONVERT(nvarchar(4000), COLUMN, 126)), 24)</span><span class="sxs-lookup"><span data-stu-id="5aee0-128">SUBSTRING(CONVERT(nvarchar(4000), COLUMN, 126), 1+CHARINDEX(N'T', CONVERT(nvarchar(4000), COLUMN, 126)), 24)</span></span>|  
|<span data-ttu-id="5aee0-129">Todos os outros</span><span class="sxs-lookup"><span data-stu-id="5aee0-129">All others</span></span>|<span data-ttu-id="5aee0-130">Nenhuma conversão adicional</span><span class="sxs-lookup"><span data-stu-id="5aee0-130">No additional conversion</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="5aee0-131">Alguns dos valores retornados pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] podem não ser compatíveis com os tipos de dados XML que são especificados usando `xsd:type`, seja porque a conversão não é possível (por exemplo, converter "XYZ" em um tipo de dados `decimal`) ou porque o valor excede o intervalo desse tipo de dados (por exemplo, -100000 convertido em um tipo `UnsignedShort` XSD).</span><span class="sxs-lookup"><span data-stu-id="5aee0-131">Some of the values returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] might not be compatible with the XML data types that are specified by using `xsd:type`, either because the conversion is not possible (for example, converting "XYZ" to a `decimal` data type) or because the value exceeds the range of that data type (for example, -100000 converted to an `UnsignedShort` XSD type).</span></span> <span data-ttu-id="5aee0-132">Conversões de tipo incompatíveis podem resultar em documentos XML que não são válidos ou em erros do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5aee0-132">Incompatible type conversions might result in XML documents that are not valid, or in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] errors.</span></span>  
  
## <a name="mapping-from-sql-server-data-types-to-xsd-data-types"></a><span data-ttu-id="5aee0-133">Mapeando dos tipos de dados do SQL Server para os tipos de dados XSD</span><span class="sxs-lookup"><span data-stu-id="5aee0-133">Mapping from SQL Server Data Types to XSD Data Types</span></span>  
 <span data-ttu-id="5aee0-134">A seguinte tabela mostra um mapeamento óbvio de tipos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para tipos de dados XSD.</span><span class="sxs-lookup"><span data-stu-id="5aee0-134">The following table shows an obvious mapping from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types to XSD data types.</span></span> <span data-ttu-id="5aee0-135">Se você souber o tipo do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], esta tabela fornecerá o tipo XSD correspondente que você pode especificar no esquema XSD.</span><span class="sxs-lookup"><span data-stu-id="5aee0-135">If you know the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] type, this table provides the corresponding XSD type that you can specify in the XSD schema.</span></span>  
  
|<span data-ttu-id="5aee0-136">Tipo de dados do SQL Server</span><span class="sxs-lookup"><span data-stu-id="5aee0-136">SQL Server data type</span></span>|<span data-ttu-id="5aee0-137">Tipo de dados XSD</span><span class="sxs-lookup"><span data-stu-id="5aee0-137">XSD data type</span></span>|  
|--------------------------|-------------------|  
|`bigint`|`long`|  
|`binary`|`base64Binary`|  
|`bit`|`boolean`|  
|`char`|`string`|  
|`datetime`|`dateTime`|  
|`decimal`|`decimal`|  
|`float`|`double`|  
|`image`|`base64Binary`|  
|`int`|`int`|  
|`money`|`decimal`|  
|`nchar`|`string`|  
|`ntext`|`string`|  
|`nvarchar`|`string`|  
|`numeric`|`decimal`|  
|`real`|`float`|  
|`smalldatetime`|`dateTime`|  
|`smallint`|`short`|  
|`smallmoney`|`decimal`|  
|`sql_variant`|`string`|  
|`sysname`|`string`|  
|`text`|`string`|  
|`timestamp`|`dateTime`|  
|`tinyint`|`unsignedByte`|  
|`varbinary`|`base64Binary`|  
|`varchar`|`string`|  
|`uniqueidentifier`|`string`|  
  
## <a name="sqldatatype-annotation"></a><span data-ttu-id="5aee0-138">Anotação sql:datatype</span><span class="sxs-lookup"><span data-stu-id="5aee0-138">sql:datatype Annotation</span></span>  
 <span data-ttu-id="5aee0-139">A anotação `sql:datatype` é usada para especificar o tipo de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]; essa anotação deve ser especificada quando:</span><span class="sxs-lookup"><span data-stu-id="5aee0-139">The `sql:datatype` annotation is used to specify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type; this annotation must be specified when:</span></span>  
  
-   <span data-ttu-id="5aee0-140">Você está carregando em massa em uma `dateTime` [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] coluna de um XSD `dateTime` , `date` ou `time` tipo.</span><span class="sxs-lookup"><span data-stu-id="5aee0-140">You are bulk loading into a `dateTime`[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column from an XSD `dateTime`, `date`, or `time` type.</span></span> <span data-ttu-id="5aee0-141">Neste caso, você deve identificar o tipo de dados de coluna do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando `sql:datatype="dateTime"`.</span><span class="sxs-lookup"><span data-stu-id="5aee0-141">In this case, you must identify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] column data type by using `sql:datatype="dateTime"`.</span></span> <span data-ttu-id="5aee0-142">Esta regra também se aplica a diagramas de atualização.</span><span class="sxs-lookup"><span data-stu-id="5aee0-142">This rule also applies to updategrams.</span></span>  
  
-   <span data-ttu-id="5aee0-143">Você está carregando em massa em uma coluna do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `uniqueidentifier` tipo e o valor XSD é um GUID que inclui chaves ({e}).</span><span class="sxs-lookup"><span data-stu-id="5aee0-143">You are bulk loading into a column of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] `uniqueidentifier` type and the XSD value is a GUID that includes braces ({ and }).</span></span> <span data-ttu-id="5aee0-144">Quando você especificar `sql:datatype="uniqueidentifier"`, as chaves são removidas do valor antes que ele seja inserido na coluna.</span><span class="sxs-lookup"><span data-stu-id="5aee0-144">When you specify `sql:datatype="uniqueidentifier"`, the braces are removed from the value before it is inserted in the column.</span></span> <span data-ttu-id="5aee0-145">Se `sql:datatype` não for especificado, o valor será enviado com as chaves e a inserção ou atualização falhará.</span><span class="sxs-lookup"><span data-stu-id="5aee0-145">If `sql:datatype` is not specified, the value is sent with the braces, and the insert or update fails.</span></span>  
  
-   <span data-ttu-id="5aee0-146">O tipo de dados XML `base64Binary` é mapeado para vários tipos de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (`binary`, `image` ou `varbinary`).</span><span class="sxs-lookup"><span data-stu-id="5aee0-146">The XML data type `base64Binary` maps to various [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data types (`binary`, `image`, or `varbinary`).</span></span> <span data-ttu-id="5aee0-147">Para mapear o tipo de dados XML `base64Binary` para um tipo de dados específico do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], use a anotação `sql:datatype`.</span><span class="sxs-lookup"><span data-stu-id="5aee0-147">To map the XML data type `base64Binary` to a specific [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type, use the `sql:datatype` annotation.</span></span> <span data-ttu-id="5aee0-148">Essa anotação especifica o tipo de dados explícito do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] da coluna para a qual o atributo é mapeado.</span><span class="sxs-lookup"><span data-stu-id="5aee0-148">This annotation specifies the explicit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type of the column to which the attribute maps.</span></span> <span data-ttu-id="5aee0-149">Isto é útil quando os dados estão sendo armazenados nos bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="5aee0-149">This is useful when data is being stored in the databases.</span></span> <span data-ttu-id="5aee0-150">Especificando a anotação `sql:datatype`, você pode identificar o tipo de dados [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] explícito.</span><span class="sxs-lookup"><span data-stu-id="5aee0-150">By specifying the `sql:datatype` annotation, you can identify the explicit [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type.</span></span>  
  
 <span data-ttu-id="5aee0-151">Geralmente é recomendável que você especifique `sql:datatype` no esquema.</span><span class="sxs-lookup"><span data-stu-id="5aee0-151">It is generally recommended that you specify `sql:datatype` in the schema.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="5aee0-152">Exemplos</span><span class="sxs-lookup"><span data-stu-id="5aee0-152">Examples</span></span>  
 <span data-ttu-id="5aee0-153">Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="5aee0-153">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="5aee0-154">Para obter mais informações, consulte [Requirements for running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="5aee0-154">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-xsdtype"></a><span data-ttu-id="5aee0-155">a.</span><span class="sxs-lookup"><span data-stu-id="5aee0-155">A.</span></span> <span data-ttu-id="5aee0-156">Especificando xsd:type</span><span class="sxs-lookup"><span data-stu-id="5aee0-156">Specifying xsd:type</span></span>  
 <span data-ttu-id="5aee0-157">Este exemplo mostra como um tipo XSD `date` que é especificado usando o atributo `xsd:type` no esquema afeta o documento de XML resultante.</span><span class="sxs-lookup"><span data-stu-id="5aee0-157">This example shows how an XSD `date` type that is specified by using the `xsd:type` attribute in the schema affects the resulting XML document.</span></span> <span data-ttu-id="5aee0-158">O esquema fornece uma exibição XML da tabela Sales.SalesOrderHeader no banco de dados AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="5aee0-158">The schema provides an XML view of the Sales.SalesOrderHeader table in the AdventureWorks database.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader">  
     <xsd:complexType>  
       <xsd:attribute name="SalesOrderID" type="xsd:string" />   
       <xsd:attribute name="CustomerID"   type="xsd:string" />   
       <xsd:attribute name="OrderDate"    type="xsd:date" />   
       <xsd:attribute name="DueDate"  />   
       <xsd:attribute name="ShipDate"  type="xsd:time" />   
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="5aee0-159">Nesse esquema de XSD, há três atributos que retornam um valor de data de [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="5aee0-159">In this XSD schema, there are three attributes that return a date value from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="5aee0-160">Quando o esquema:</span><span class="sxs-lookup"><span data-stu-id="5aee0-160">When the schema:</span></span>  
  
-   <span data-ttu-id="5aee0-161">Especifica `xsd:type=date` no atributo **DataDoPedido** , a parte de data do valor retornado por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o atributo **DataDoPedido** é exibido.</span><span class="sxs-lookup"><span data-stu-id="5aee0-161">Specifies `xsd:type=date` on the **OrderDate** attribute, the date part of the value returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the **OrderDate** attribute is displayed.</span></span>  
  
-   <span data-ttu-id="5aee0-162">Especifica `xsd:type=time` no atributo **ShipDate** , a parte de hora do valor retornado pelo [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para o atributo **ShipDate** é exibido.</span><span class="sxs-lookup"><span data-stu-id="5aee0-162">Specifies `xsd:type=time` on the **ShipDate** attribute, the time part of the value that is returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] for the **ShipDate** attribute is displayed.</span></span>  
  
-   <span data-ttu-id="5aee0-163">Não especifica `xsd:type` no atributo **DueDate** , o mesmo valor que é retornado por [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] é exibido.</span><span class="sxs-lookup"><span data-stu-id="5aee0-163">Does not specify `xsd:type` on the **DueDate** attribute, the same value that is returned by [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is displayed.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="5aee0-164">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="5aee0-164">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="5aee0-165">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="5aee0-165">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="5aee0-166">Salve o arquivo como xsdType.xml.</span><span class="sxs-lookup"><span data-stu-id="5aee0-166">Save the file as xsdType.xml.</span></span>  
  
2.  <span data-ttu-id="5aee0-167">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="5aee0-167">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="5aee0-168">Salve o arquivo como xsdTypeT.xml no mesmo diretório onde você salvou xsdType.xml.</span><span class="sxs-lookup"><span data-stu-id="5aee0-168">Save the file as xsdTypeT.xml in the same directory where you saved xsdType.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="xsdType.xml">  
        /Order  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="5aee0-169">O caminho de diretório especificado para o esquema de mapeamento (xsdType.xml) é relativo ao diretório onde o modelo está salvo.</span><span class="sxs-lookup"><span data-stu-id="5aee0-169">The directory path specified for the mapping schema (xsdType.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="5aee0-170">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="5aee0-170">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\xsdType.xml"  
    ```  
  
3.  <span data-ttu-id="5aee0-171">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="5aee0-171">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="5aee0-172">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="5aee0-172">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="5aee0-173">Este é o conjunto de resultados parcial:</span><span class="sxs-lookup"><span data-stu-id="5aee0-173">Here is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="43659"   
         CustomerID="676"   
         OrderDate="2001-07-01"   
         DueDate="2001-07-13T00:00:00"   
         ShipDate="00:00:00" />   
  <Order SalesOrderID="43660"   
         CustomerID="117"   
         OrderDate="2001-07-01"   
         DueDate="2001-07-13T00:00:00"   
         ShipDate="00:00:00" />   
 ...  
</ROOT>  
```  
  
 <span data-ttu-id="5aee0-174">Este é o esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="5aee0-174">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  
<ElementType name="Order" sql:relation="Sales.SalesOrderHeader">  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="CustomerID"  />  
    <AttributeType name="OrderDate" dt:type="date" />  
    <AttributeType name="DueDate" />  
    <AttributeType name="ShipDate" dt:type="time" />  
  
    <attribute type="SalesOrderID" sql:field="OrderID" />  
    <attribute type="CustomerID" sql:field="CustomerID" />  
    <attribute type="OrderDate" sql:field="OrderDate" />  
    <attribute type="DueDate" sql:field="DueDate" />  
    <attribute type="ShipDate" sql:field="ShipDate" />  
</ElementType>  
</Schema>  
```  
  
### <a name="b-specifying-sql-data-type-using-sqldatatype"></a><span data-ttu-id="5aee0-175">B.</span><span class="sxs-lookup"><span data-stu-id="5aee0-175">B.</span></span> <span data-ttu-id="5aee0-176">Especificando o tipo de dados de SQL usando sql:datatype</span><span class="sxs-lookup"><span data-stu-id="5aee0-176">Specifying SQL data type using sql:datatype</span></span>  
 <span data-ttu-id="5aee0-177">Para obter um exemplo de trabalho, veja exemplos de carregamento em massa de exemplo G em [XML em lotes &#40;SQLXML 4,0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/xml-bulk-load-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="5aee0-177">For a working sample, see Example G in [XML Bulk Load Examples &#40;SQLXML 4.0&#41;](../sqlxml-annotated-xsd-schemas-xpath-queries/bulk-load-xml/xml-bulk-load-examples-sqlxml-4-0.md).</span></span> <span data-ttu-id="5aee0-178">Nesse exemplo, um valor de GUID que inclui "{" e "}" é carregado em massa.</span><span class="sxs-lookup"><span data-stu-id="5aee0-178">In this example, a GUID value including "{" and "}" is bulk loaded.</span></span> <span data-ttu-id="5aee0-179">O esquema nesse exemplo especifica `sql:datatype` para identificar o tipo de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como `uniqueidentifier`.</span><span class="sxs-lookup"><span data-stu-id="5aee0-179">The schema in this example specifies `sql:datatype` to identify the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data type as `uniqueidentifier`.</span></span> <span data-ttu-id="5aee0-180">Esse exemplo ilustra quando deve ser especificado `sql:datatype` no esquema.</span><span class="sxs-lookup"><span data-stu-id="5aee0-180">This example illustrate when `sql:datatype` must be specified in the schema.</span></span>  
  
  
