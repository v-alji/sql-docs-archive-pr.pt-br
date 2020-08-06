---
title: Definir a serialização de dados XML| Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- entitization rules [XML in SQL Server]
- serialization
- reparsing serialized XML structures
- encoding [XML in SQL Server]
- XML [SQL Server], serialization
- xml data type [SQL Server], serialization
- typed XML
ms.assetid: 42b0b5a4-bdd6-4a60-b451-c87f14758d4b
author: rothja
ms.author: jroth
ms.openlocfilehash: df87dddd9fd4cf067125314c9d798eaa42523576
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583402"
---
# <a name="define-the-serialization-of-xml-data"></a><span data-ttu-id="4fc84-102">Definir a serialização de dados XML</span><span class="sxs-lookup"><span data-stu-id="4fc84-102">Define the Serialization of XML Data</span></span>
  <span data-ttu-id="4fc84-103">Ao converter tipos de dados xml explícita ou implicitamente em uma cadeia de caracteres SQL ou tipo binário, o conteúdo do tipo de dados xml será serializado de acordo com as regras descritas neste tópico.</span><span class="sxs-lookup"><span data-stu-id="4fc84-103">When casting the xml data type explicitly or implicitly to a SQL string or binary type, the content of the xml data type will be serialized according to the rules outlined in this topic.</span></span>  
  
## <a name="serialization-encoding"></a><span data-ttu-id="4fc84-104">Codificação de serialização</span><span class="sxs-lookup"><span data-stu-id="4fc84-104">Serialization Encoding</span></span>  
 <span data-ttu-id="4fc84-105">Se o tipo de destino SQL for VARBINARY, o resultado será serializado em UTF-16 com uma marca de ordem de 16 bytes UTF na frente, mas sem uma declaração XML.</span><span class="sxs-lookup"><span data-stu-id="4fc84-105">If the SQL target type is VARBINARY, the result is serialized in UTF-16 with a UTF-16-byte order mark in front, but without an XML declaration.</span></span> <span data-ttu-id="4fc84-106">Se o tipo de destino for muito pequeno, será retornado um erro.</span><span class="sxs-lookup"><span data-stu-id="4fc84-106">If the target type is too small, an error is raised.</span></span>  
  
 <span data-ttu-id="4fc84-107">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4fc84-107">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as VARBINARY(MAX))  
```  
  
 <span data-ttu-id="4fc84-108">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="4fc84-108">This is the result:</span></span>  
  
```  
0xFFFE3C0094032F003E00  
```  
  
 <span data-ttu-id="4fc84-109">Se o tipo de destino SQL for NVARCHAR ou NCHAR, o resultado será serializado em UTF-16 sem a marca de ordem de bytes na frente e sem uma declaração XML.</span><span class="sxs-lookup"><span data-stu-id="4fc84-109">If the SQL target type is NVARCHAR or NCHAR, the result is serialized in UTF-16 without the byte order mark in front and without an XML declaration.</span></span> <span data-ttu-id="4fc84-110">Se o tipo de destino for muito pequeno, será retornado um erro.</span><span class="sxs-lookup"><span data-stu-id="4fc84-110">If the target type is too small, an error is raised.</span></span>  
  
 <span data-ttu-id="4fc84-111">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4fc84-111">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as NVARCHAR(MAX))  
```  
  
 <span data-ttu-id="4fc84-112">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="4fc84-112">This is the result:</span></span>  
  
```  
<Δ/>  
```  
  
 <span data-ttu-id="4fc84-113">Se o tipo de destino SQL for VARCHAR ou NCHAR, o resultado será serializado na codificação correspondente à página de código de ordenação do banco de dados sem uma marca de ordem de bytes ou declaração XML.</span><span class="sxs-lookup"><span data-stu-id="4fc84-113">If the SQL target type is VARCHAR or NCHAR, the result is serialized in the encoding that corresponds to the database's collation code page without a byte order mark or XML declaration.</span></span> <span data-ttu-id="4fc84-114">Se o tipo de destino for muito pequeno ou se o valor não puder ser mapeado para a página de código de ordenação de destino, será retornado um erro.</span><span class="sxs-lookup"><span data-stu-id="4fc84-114">If the target type is too small or the value cannot be mapped to the target collation code page, an error is raised.</span></span>  
  
 <span data-ttu-id="4fc84-115">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4fc84-115">For example:</span></span>  
  
```sql
select CAST(CAST(N'<Δ/>' as XML) as VARCHAR(MAX))  
```  
  
 <span data-ttu-id="4fc84-116">Isso pode resultar em um erro se a página de código do agrupamento atual não puder representar o caractere Unicode & # x10300;, ou ele irá representá-lo na codificação específica.</span><span class="sxs-lookup"><span data-stu-id="4fc84-116">This may result in an error, if the current collation's code page cannot represent the Unicode character &#x10300;, or it will represent it in the specific encoding.</span></span>  
  
 <span data-ttu-id="4fc84-117">Ao retornar resultados XML para o lado do cliente, os dados serão enviados em codificação UTF-16.</span><span class="sxs-lookup"><span data-stu-id="4fc84-117">When returning XML results to the client side, the data will be sent in UTF-16 encoding.</span></span> <span data-ttu-id="4fc84-118">O provedor do lado do cliente exporá os dados de acordo com as regras de sua API.</span><span class="sxs-lookup"><span data-stu-id="4fc84-118">The client-side provider will then expose the data according to its API rules.</span></span>  
  
## <a name="serialization-of-the-xml-structures"></a><span data-ttu-id="4fc84-119">Serialização das estruturas XML</span><span class="sxs-lookup"><span data-stu-id="4fc84-119">Serialization of the XML Structures</span></span>  
 <span data-ttu-id="4fc84-120">O conteúdo de um tipo de dados **xml** é serializado da maneira normal.</span><span class="sxs-lookup"><span data-stu-id="4fc84-120">The content of an **xml** data type is serialized in the usual way.</span></span> <span data-ttu-id="4fc84-121">Especificamente, nós de elemento são mapeados para marcação de elemento e nós de texto são mapeados para conteúdo de texto.</span><span class="sxs-lookup"><span data-stu-id="4fc84-121">Specifically, element nodes are mapped to element markup, and text nodes are mapped to text content.</span></span> <span data-ttu-id="4fc84-122">No entanto, as circunstâncias nas quais a entidade dos caracteres é definida e a maneira como valores atômicos digitados são serializados são descritas nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="4fc84-122">However, the circumstances under which characters are entitized and how typed atomic values are serialized are described in the following sections.</span></span>  
  
## <a name="entitization-of-xml-characters-during-serialization"></a><span data-ttu-id="4fc84-123">Definição da entidade de caracteres XML durante a serialização</span><span class="sxs-lookup"><span data-stu-id="4fc84-123">Entitization of XML Characters During Serialization</span></span>  
 <span data-ttu-id="4fc84-124">Cada estrutura XML serializada deve poder ser reanalisada.</span><span class="sxs-lookup"><span data-stu-id="4fc84-124">Every serialized XML structure should be capable of being reparsed.</span></span> <span data-ttu-id="4fc84-125">Portanto alguns caracteres precisam ser serializados de uma maneira de definição de entidade para preservar a capacidade de viagem de ida e volta dos caracteres durante a fase de normalização do analisador XML.</span><span class="sxs-lookup"><span data-stu-id="4fc84-125">Therefore, some characters have to be serialized in an entitized way to preserve the round-trip capability of the characters through the XML parser's normalization phase .</span></span> <span data-ttu-id="4fc84-126">No entanto a entidade de alguns caracteres precisa ser definida para que o documento seja bem formado e portanto possa ser analisado.</span><span class="sxs-lookup"><span data-stu-id="4fc84-126">However, some characters have to be entitized so that the document is well-formed and, therefore, able to be parsed.</span></span> <span data-ttu-id="4fc84-127">As regras de definição de entidade aplicáveis durante a serialização são as seguintes:</span><span class="sxs-lookup"><span data-stu-id="4fc84-127">Following are the entitization rules that apply during serialization:</span></span>  
  
-   <span data-ttu-id="4fc84-128">Os caracteres &, \<, and > são sempre definidos como &amp;, &lt; e &gt; respectivamente, se ocorrem dentro de um valor de atributo ou conteúdo de elemento.</span><span class="sxs-lookup"><span data-stu-id="4fc84-128">The characters &, \<, and > are always entitized to &amp;, &lt;, and &gt; respectively, if they occur inside an attribute value or element content.</span></span>  
  
-   <span data-ttu-id="4fc84-129">Como o SQL Server usa aspas (U+0022) para incluir valores de atributos, a entidade de aspas em valores de atributos é definida como &quot;.</span><span class="sxs-lookup"><span data-stu-id="4fc84-129">Because SQL Server uses a quotation mark (U+0022) for enclosing attribute values, the quotation mark in attribute values is entitized as &quot;.</span></span>  
  
-   <span data-ttu-id="4fc84-130">A entidade de um par substituto é definida como uma referência de caractere numérico único na conversão no servidor apenas.</span><span class="sxs-lookup"><span data-stu-id="4fc84-130">A surrogate pair is entitized as a single numeric character reference, when casting on the server only.</span></span> <span data-ttu-id="4fc84-131">Por exemplo, a entidade do par substituto U+D800 U+DF00 é definida como a referência de caractere numérico &\#x00010300;.</span><span class="sxs-lookup"><span data-stu-id="4fc84-131">For example the surrogate pair U+D800 U+DF00 is entitized to the numeric character reference &\#x00010300;.</span></span>  
  
-   <span data-ttu-id="4fc84-132">Para proteger uma TABULAÇÃO (U+0009) e um avanço de linha (LF, U+000A) contra normalização durante a análise, suas entidades são definidas como suas referências de caractere numérico &\#x9; e &\#xA; respectivamente, dentro de valores de atributos.</span><span class="sxs-lookup"><span data-stu-id="4fc84-132">To protect a TAB (U+0009) and a linefeed (LF, U+000A) from being normalized during parsing, they are entitized to their numeric character references &\#x9; and &\#xA; respectively, inside attribute values.</span></span>  
  
-   <span data-ttu-id="4fc84-133">Para evitar que um retorno de carro (CR, U+000D) seja normalizado durante a análise, a entidade é definida como sua referência de caractere numérico, &\#xD; dentro dos valores de atributos e do conteúdo de elemento.</span><span class="sxs-lookup"><span data-stu-id="4fc84-133">To prevent a carriage return (CR, U+000D) from being normalized during parsing, it is entitized to its numeric character reference, &\#xD; inside both attribute values and element content.</span></span>  
  
-   <span data-ttu-id="4fc84-134">Para proteger nós de texto que contêm apenas espaço em branco, a entidade de um dos caracteres de espaço em branco, geralmente o último, é definida como sua referência de caractere numérico.</span><span class="sxs-lookup"><span data-stu-id="4fc84-134">To protect text nodes that only contain white space, one of the white-space characters, generally the last one, is entitized as its numeric character reference.</span></span> <span data-ttu-id="4fc84-135">Dessa maneira, a reanálise preserva o nó de texto do caractere em branco, independentemente da configuração do tratamento do espaço em branco durante a análise.</span><span class="sxs-lookup"><span data-stu-id="4fc84-135">In this way, reparsing preserves the white-space text node, regardless of the setting of the white-space handling during parsing.</span></span>  
  
 <span data-ttu-id="4fc84-136">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4fc84-136">For example:</span></span>  
  
```sql
declare @u NVARCHAR(50)  
set @u = N'<a a="  
    '+NCHAR(0xD800)+NCHAR(0xDF00)+N'>">   '+NCHAR(0xA)+N'</a>'  
select CAST(CONVERT(XML,@u,1) as NVARCHAR(50))  
```  
  
 <span data-ttu-id="4fc84-137">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="4fc84-137">This is the result:</span></span>  
  
```  
<a a="  
    𐌀>">     
</a>  
```  
  
 <span data-ttu-id="4fc84-138">Se não desejar aplicar a regra de proteção do último caractere em branco, você poderá usar a opção explícita 1 de CONVERT ao converter de **xml** em uma cadeia de caracteres ou em um tipo binário.</span><span class="sxs-lookup"><span data-stu-id="4fc84-138">If you do not want to apply the last white-space protection rule, you can use the explicit CONVERT option 1 when casting from **xml** to a string or binary type.</span></span> <span data-ttu-id="4fc84-139">Por exemplo, para evitar a definição de entidade, você pode fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="4fc84-139">For example, to avoid entitization, you can do the following:</span></span>  
  
```sql
select CONVERT(NVARCHAR(50), CONVERT(XML, '<a>   </a>', 1), 1)  
```  
  
 <span data-ttu-id="4fc84-140">Observe que, o [Método query() (tipo de dados xml)](/sql/t-sql/xml/query-method-xml-data-type) resulta em uma instância de tipo de dados xml.</span><span class="sxs-lookup"><span data-stu-id="4fc84-140">Note that, the [query() Method (xml Data Type)](/sql/t-sql/xml/query-method-xml-data-type) results in an xml data type instance.</span></span> <span data-ttu-id="4fc84-141">Portanto qualquer resultado do método **query()** que seja convertido em um tipo de cadeia de caracteres ou binário tem a entidade definida de acordo com as regras descritas anteriormente.</span><span class="sxs-lookup"><span data-stu-id="4fc84-141">Therefore, any result of the **query()** method that is cast to a string or binary type is entitized according to the previously described rules.</span></span> <span data-ttu-id="4fc84-142">Para obter os valores da cadeia de caracteres que não têm a entidade definida, use o [Método value() (tipo de dados xml)](/sql/t-sql/xml/value-method-xml-data-type) .</span><span class="sxs-lookup"><span data-stu-id="4fc84-142">If you want to obtain the string values that are not entitized, you should use the [value() Method (xml Data Type)](/sql/t-sql/xml/value-method-xml-data-type) instead.</span></span> <span data-ttu-id="4fc84-143">O seguinte é um exemplo de uso do método **query()** :</span><span class="sxs-lookup"><span data-stu-id="4fc84-143">Following is an example of using the **query()** method:</span></span>  
  
```sql
declare @x xml  
set @x = N'<a>This example contains an entitized char: <.</a>'  
select @x.query('/a/text()')  
```  
  
 <span data-ttu-id="4fc84-144">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="4fc84-144">This is the result:</span></span>  
  
```  
This example contains an entitized char: <.  
```  
  
 <span data-ttu-id="4fc84-145">O seguinte é um exemplo de uso do método **value()** :</span><span class="sxs-lookup"><span data-stu-id="4fc84-145">Following is an example of using the **value()** method:</span></span>  
  
```sql
select @x.value('(/a/text())[1]', 'nvarchar(100)')  
```  
  
 <span data-ttu-id="4fc84-146">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="4fc84-146">This is the result:</span></span>  
  
```  
This example contains an entitized char: <.  
```  
  
## <a name="serializing-a-typed-xml-data-type"></a><span data-ttu-id="4fc84-147">Serializando um tipo de dados xml com tipo</span><span class="sxs-lookup"><span data-stu-id="4fc84-147">Serializing a Typed xml Data Type</span></span>  
 <span data-ttu-id="4fc84-148">Uma instância de tipo de dados **xml** com tipo contém valores com tipo de acordo com seus tipos de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="4fc84-148">A typed **xml** data type instance contains values that are typed according to their XML schema types.</span></span> <span data-ttu-id="4fc84-149">Esses valores são serializados de acordo com seu tipo de esquema XML no mesmo formato que a conversão de Xquery para procedimentos xs:string.</span><span class="sxs-lookup"><span data-stu-id="4fc84-149">These values are serialized according to their XML schema type in the same format as the XQuery cast to xs:string produces.</span></span> <span data-ttu-id="4fc84-150">Para obter mais informações, veja [Regras de conversão de tipo em XQuery](/sql/xquery/type-casting-rules-in-xquery).</span><span class="sxs-lookup"><span data-stu-id="4fc84-150">For more information, see [Type Casting Rules in XQuery](/sql/xquery/type-casting-rules-in-xquery).</span></span>  
  
 <span data-ttu-id="4fc84-151">Por exemplo, o valor de xs:double 1.34e1 é serializado como 13.4 conforme mostrado no exemplo a seguir:</span><span class="sxs-lookup"><span data-stu-id="4fc84-151">For example, the xs:double value 1.34e1 is serialized to 13.4 as shown in the following example:</span></span>  
  
```sql
declare @x xml  
set @x =''  
select CAST(@x.query('1.34e1') as nvarchar(50))  
```  
  
 <span data-ttu-id="4fc84-152">Isso retorna o valor da cadeia de caracteres 13.4.</span><span class="sxs-lookup"><span data-stu-id="4fc84-152">This returns the string value 13.4.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="4fc84-153">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="4fc84-153">See Also</span></span>  
 <span data-ttu-id="4fc84-154">[Regras de conversão de tipo em XQuery](/sql/xquery/type-casting-rules-in-xquery) </span><span class="sxs-lookup"><span data-stu-id="4fc84-154">[Type Casting Rules in XQuery](/sql/xquery/type-casting-rules-in-xquery) </span></span>  
 [<span data-ttu-id="4fc84-155">CAST e CONVERT &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="4fc84-155">CAST and CONVERT &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/functions/cast-and-convert-transact-sql)  
  
  
