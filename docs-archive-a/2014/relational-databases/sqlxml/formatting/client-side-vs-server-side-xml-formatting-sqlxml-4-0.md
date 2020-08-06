---
title: Formatação XML do lado do cliente versus do servidor (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- NESTED mode
- FOR XML clause, formatting
- client-side XML formatting
- server-side XPath
- server-side XML formatting
- AUTO mode
- client-side XPath
ms.assetid: f807ab7a-c5f8-4e61-9b00-23aebfabc47e
author: rothja
ms.author: jroth
ms.openlocfilehash: fa155fc6d346cb90de54e5599aca1c296623faa7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575715"
---
# <a name="client-side-vs-server-side-xml-formatting-sqlxml-40"></a><span data-ttu-id="df25a-102">Lado do cliente e Formatação XML do lado do servidor (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="df25a-102">Client-side vs. Server-side XML Formatting (SQLXML 4.0)</span></span>
  <span data-ttu-id="df25a-103">Este tópico descreve as diferenças gerais entre a formatação XML no lado cliente e no lado servidor no SQLXML.</span><span class="sxs-lookup"><span data-stu-id="df25a-103">This topic describes the general differences between client-side and server-side XML formatting in SQLXML.</span></span>  
  
## <a name="multiple-rowset-queries-not-supported-in-client-side-formatting"></a><span data-ttu-id="df25a-104">Várias consultas a conjuntos de linhas sem suporte na formatação no lado do cliente</span><span class="sxs-lookup"><span data-stu-id="df25a-104">Multiple Rowset Queries Not Supported in Client-side Formatting</span></span>  
 <span data-ttu-id="df25a-105">Consultas que geram vários conjuntos de linha não têm suporte quando você usa a formatação XML no lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="df25a-105">Queries that generate multiple rowsets are not supported when you use client-side XML formatting.</span></span> <span data-ttu-id="df25a-106">Por exemplo, suponha que você tenha um diretório virtual em que a formatação no lado do cliente seja especificada.</span><span class="sxs-lookup"><span data-stu-id="df25a-106">For example, assume you have a virtual directory in which you have client-side formatting specified.</span></span> <span data-ttu-id="df25a-107">Considere este modelo de exemplo, que tem duas instruções SELECT em um **\<sql:query>** bloco:</span><span class="sxs-lookup"><span data-stu-id="df25a-107">Consider this sample template, which has two SELECT statements in a **\<sql:query>** block:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query>  
     SELECT FirstName FROM Person.Contact FOR XML Nested;   
     SELECT LastName FROM Person.Contact FOR XML Nested    
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="df25a-108">Você pode executar este modelo em código do aplicativo e um erro será retornado, porque a formatação XML no lado do cliente não dá suporte à formatação de vários conjuntos de linha.</span><span class="sxs-lookup"><span data-stu-id="df25a-108">You can execute this template in application code and an error is returned, because client-side XML formatting does not support formatting of multiple rowsets.</span></span> <span data-ttu-id="df25a-109">Se você especificar as consultas em dois **\<sql:query>** blocos separados, obterá os resultados desejados.</span><span class="sxs-lookup"><span data-stu-id="df25a-109">If you specify the queries in two separate **\<sql:query>** blocks, you will get the desired results.</span></span>  
  
## <a name="timestamp-maps-differently-in-client--vs-server-side-formatting"></a><span data-ttu-id="df25a-110">Carimbo de data e hora mapeia de forma diferente as formatações no lado do cliente e no lado do servidor</span><span class="sxs-lookup"><span data-stu-id="df25a-110">timestamp Maps Differently in Client- vs. Server-side Formatting</span></span>  
 <span data-ttu-id="df25a-111">Na formatação XML no lado do servidor, a coluna do banco de dados do tipo `timestamp` mapeia para o tipo i8 XDR (quando a opção XMLDATA é especificada na consulta).</span><span class="sxs-lookup"><span data-stu-id="df25a-111">In server-side XML formatting, the database column of `timestamp` type maps to the i8 XDR type (when the XMLDATA option is specified in the query).</span></span>  
  
 <span data-ttu-id="df25a-112">Na formatação XML no lado cliente, a coluna do banco de dados do tipo `timestamp` mapeia para o tipo `uri` ou para o tipo XDR `bin.base64` (dependendo se a opção base64 binária é especificada na consulta).</span><span class="sxs-lookup"><span data-stu-id="df25a-112">In client-side XML formatting, the database column of `timestamp` type maps to either the `uri` or the `bin.base64` XDR type (depending on whether the binary base64 option is specified in the query).</span></span> <span data-ttu-id="df25a-113">O `bin.base64` tipo de XDR será útil se você usar os recursos updategram e carregamento em massa, pois esse tipo é convertido para o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `timestamp` tipo.</span><span class="sxs-lookup"><span data-stu-id="df25a-113">The `bin.base64` XDR type is useful if you use the updategram and bulkload features, because this type is converted to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `timestamp` type.</span></span> <span data-ttu-id="df25a-114">Deste modo, as operações de inserção, atualização ou exclusão são bem-sucedidas.</span><span class="sxs-lookup"><span data-stu-id="df25a-114">This way, the insert, update, or delete operation succeeds.</span></span>  
  
## <a name="deep-variants-are-used-in-server-side-formatting"></a><span data-ttu-id="df25a-115">VARIANTs profundas são usadas na formatação no lado do servidor</span><span class="sxs-lookup"><span data-stu-id="df25a-115">Deep VARIANTs Are Used in Server-side Formatting</span></span>  
 <span data-ttu-id="df25a-116">Na formatação no lado do servidor, os tipos profundos de um tipo VARIANT são usados.</span><span class="sxs-lookup"><span data-stu-id="df25a-116">In server-side XML formatting, the deep types of a VARIANT type are used.</span></span> <span data-ttu-id="df25a-117">Se você usar uma formatação XML no lado do cliente, as variantes serão convertidas à cadeia de caracteres Unicode e os subtipos de VARIANT não serão usados.</span><span class="sxs-lookup"><span data-stu-id="df25a-117">If you use client-side XML formatting, the variants are converted to Unicode string, and the subtypes of VARIANT are not used.</span></span>  
  
## <a name="nested-mode-vs-auto-mode"></a><span data-ttu-id="df25a-118">Modo NESTED e modo AUTO</span><span class="sxs-lookup"><span data-stu-id="df25a-118">NESTED Mode vs. AUTO Mode</span></span>  
 <span data-ttu-id="df25a-119">O modo NESTED de FOR XML do lado do cliente é semelhante ao modo AUTO de FOR XML do lado do servidor, com as seguintes exceções:</span><span class="sxs-lookup"><span data-stu-id="df25a-119">The NESTED mode of the client-side FOR XML is similar to the AUTO mode of server-side FOR XML, with the following exceptions:</span></span>  
  
### <a name="when-you-query-views-using-auto-mode-on-the-server-side-the-view-name-is-returned-as-the-element-name-in-the-resulting-xml"></a><span data-ttu-id="df25a-120">Quando você consulta exibições usando o modo AUTO no lado do servidor, o nome da exibição é retornado como o nome do elemento no XML resultante.</span><span class="sxs-lookup"><span data-stu-id="df25a-120">When you query views using AUTO mode on the server-side, the view name is returned as the element name in the resulting XML.</span></span>  
 <span data-ttu-id="df25a-121">Por exemplo, suponha que a exibição a seguir seja criada na tabela Person. Contact no AdventureWorksdatabase:</span><span class="sxs-lookup"><span data-stu-id="df25a-121">For example, assume that the following view is created on the Person.Contact table in the AdventureWorksdatabase:</span></span>  
  
```  
CREATE VIEW ContactView AS (SELECT ContactID as CID,  
                               FirstName  as FName,  
                               LastName  as LName  
                        FROM Person.Contact)  
```  
  
 <span data-ttu-id="df25a-122">O modelo a seguir especifica uma consulta na exibição ContactView e também uma formatação XML no lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="df25a-122">The following template specifies a query against the ContactView view, and also specifies server-side XML formatting:</span></span>  
  
```  
 <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="0">  
    SELECT *  
    FROM   ContactView  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="df25a-123">Quando você executar o modelo, o seguinte XML será retornado:</span><span class="sxs-lookup"><span data-stu-id="df25a-123">When you execute the template, the following XML is returned.</span></span> <span data-ttu-id="df25a-124">(Somente resultados parciais são mostrados.) Observe que os nomes de elemento são os nomes das exibições nas quais a consulta é executada.</span><span class="sxs-lookup"><span data-stu-id="df25a-124">(Only partial results are shown.) Note that the element names are the names of the views against which the query is executed.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <ContactView CID="1" FName="Gustavo" LName="Achong" />   
  <ContactView CID="2" FName="Catherine" LName="Abel" />   
...  
</ROOT>  
```  
  
 <span data-ttu-id="df25a-125">Quando você especifica a formatação XML no lado cliente usando o modo NESTED correspondente, o(s) nome(s) da tabela base são retornados como nome(s) do elemento no XML resultante.</span><span class="sxs-lookup"><span data-stu-id="df25a-125">When you specify client-side XML formatting by using the corresponding NESTED mode, the base table name(s) are returned as the element name(s) in the resulting XML.</span></span> <span data-ttu-id="df25a-126">Por exemplo, o modelo revisado a seguir executa a mesma instrução SELECT, mas a formatação XML é executada no lado do cliente (ou seja, o **XML do lado do cliente** é definido como true no modelo):</span><span class="sxs-lookup"><span data-stu-id="df25a-126">For example, the following revised template executes the same SELECT statement, but the XML formatting is performed on the client-side (that is, **client-side-xml** is set to true in the template):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    SELECT *  
    FROM   ContactView  
    FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="df25a-127">A execução desse modelo produz o seguinte XML:</span><span class="sxs-lookup"><span data-stu-id="df25a-127">Executing this template produces the following XML.</span></span> <span data-ttu-id="df25a-128">Observe que o nome do elemento é o nome da tabela base, nesse caso.</span><span class="sxs-lookup"><span data-stu-id="df25a-128">Note that the element name is the base table name in this case.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact CID="1" FName="Gustavo" LName="Achong" />   
  <Person.Contact CID="2" FName="Catherine" LName="Abel" />   
...  
</ROOT>  
```  
  
### <a name="when-you-use-auto-mode-of-the-server-side-for-xml-the-table-aliases-specified-in-the-query-are-returned-as-element-names-in-the-resulting-xml"></a><span data-ttu-id="df25a-129">Quando você usa o modo AUTO de FOR XML no lado do servidor, os aliases da tabela especificados na consulta são retornados como nomes de elemento no XML resultante.</span><span class="sxs-lookup"><span data-stu-id="df25a-129">When you use AUTO mode of the server-side FOR XML, the table aliases specified in the query are returned as element names in the resulting XML.</span></span>  
 <span data-ttu-id="df25a-130">Por exemplo, considere este modelo:</span><span class="sxs-lookup"><span data-stu-id="df25a-130">For example, consider this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="0">  
    SELECT FirstName as fname,  
           LastName as lname  
    FROM   Person.Contact C  
    FOR XML AUTO  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="df25a-131">A execução do modelo produz o seguinte XML:</span><span class="sxs-lookup"><span data-stu-id="df25a-131">Executing the template produces the following XML:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <C fname="Gustavo" lname="Achong" />   
  <C fname="Catherine" lname="Abel" />   
...  
</ROOT>   
```  
  
 <span data-ttu-id="df25a-132">Quando você usa o modo NESTED de FOR XML no lado do cliente, os nomes da tabela são retornados como nomes do elemento no XML resultante.</span><span class="sxs-lookup"><span data-stu-id="df25a-132">When you use the NESTED mode of the client-side FOR XML, the table names are returned as element names in the resulting XML.</span></span> <span data-ttu-id="df25a-133">(Os aliases de tabela especificados na consulta não são usados.) Por exemplo, considere este modelo:</span><span class="sxs-lookup"><span data-stu-id="df25a-133">(Table aliases that are specified in the query are not used.) For example, consider this template:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <sql:query client-side-xml="1">  
    SELECT FirstName as fname,  
           LastName as lname  
    FROM   Person.Contact C  
    FOR XML NESTED  
  </sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="df25a-134">A execução do modelo produz o seguinte XML:</span><span class="sxs-lookup"><span data-stu-id="df25a-134">Executing the template produces the following XML:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Person.Contact fname="Gustavo" lname="Achong" />   
  <Person.Contact fname="Catherine" lname="Abel" />   
...  
</ROOT>  
```  
  
### <a name="if-you-have-a-query-that-returns-columns-as-dbobject-queries-you-cannot-use-aliases-for-these-columns"></a><span data-ttu-id="df25a-135">Se você tiver uma consulta que retorne colunas como consultas dbobject, não poderá usar aliases para essas colunas.</span><span class="sxs-lookup"><span data-stu-id="df25a-135">If you have a query that returns columns as dbobject queries, you cannot use aliases for these columns.</span></span>  
 <span data-ttu-id="df25a-136">Por exemplo, considere o modelo a seguir, que executa uma consulta que retorna uma ID de funcionário e uma foto.</span><span class="sxs-lookup"><span data-stu-id="df25a-136">For example, consider the following template, which executes a query that returns an employee ID and a photo.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<sql:query client-side-xml="1">  
   SELECT ProductPhotoID, LargePhoto as P  
   FROM   Production.ProductPhoto  
   WHERE  ProductPhotoID=5  
   FOR XML NESTED, elements  
</sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="df25a-137">A execução desse modelo retorna a coluna Photo como consulta dbobject.</span><span class="sxs-lookup"><span data-stu-id="df25a-137">Executing this template returns the Photo column as a dbobject query.</span></span> <span data-ttu-id="df25a-138">Nessa consulta dbobject, `@P` se refere a um nome de coluna que não existe.</span><span class="sxs-lookup"><span data-stu-id="df25a-138">In this dbobject query, `@P` refers to a column name that does not exist.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductPhoto>  
    <ProductPhotoID>5</ProductPhotoID>  
    <LargePhoto>dbobject/Production.ProductPhoto[@ProductPhotoID='5']/@P</LargePhoto>  
  </Production.ProductPhoto>  
</ROOT>  
```  
  
 <span data-ttu-id="df25a-139">Se a formatação XML for feita no servidor (**cliente-XML = "0"**), você poderá usar o alias para as colunas que retornam consultas DBObject nas quais os nomes reais de tabela e coluna são retornados (mesmo que você tenha aliases especificados).</span><span class="sxs-lookup"><span data-stu-id="df25a-139">If the XML formatting is done on the server (**client-side-xml="0"**), you can use the alias for the columns that return dbobject queries in which actual table and column names are returned (even if you have aliases specified).</span></span> <span data-ttu-id="df25a-140">Por exemplo, o modelo a seguir executa uma consulta e a formatação XML é feita no servidor (a opção de **XML do lado do cliente** não é especificada e a opção **executar no cliente** não é selecionada para a raiz virtual).</span><span class="sxs-lookup"><span data-stu-id="df25a-140">For example, the following template executes a query, and the XML formatting is done on the server (the **client-side-xml** option is not specified and the **Run On Client** option is not selected for the virtual root).</span></span> <span data-ttu-id="df25a-141">A consulta também especifica o modo AUTO (não o modo NESTED do lado do cliente).</span><span class="sxs-lookup"><span data-stu-id="df25a-141">The query also specifies AUTO mode (not the client-side NESTED mode).</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<sql:query   
   SELECT ProductPhotoID, LargePhoto as P  
   FROM   Production.ProductPhoto  
   WHERE  ProductPhotoID=5  
   FOR XML AUTO, elements  
</sql:query>  
</ROOT>  
```  
  
 <span data-ttu-id="df25a-142">Quando esse modelo é executado, o seguinte documento XML é retornado (observe que os aliases não são usados na consulta dbobject para a coluna LargePhoto):</span><span class="sxs-lookup"><span data-stu-id="df25a-142">When this template is executed, the following XML document is returned (note that aliases are not used in the dbobject query for the LargePhoto column):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Production.ProductPhoto>  
    <ProductPhotoID>5</ProductPhotoID>  
    <LargePhoto>dbobject/Production.ProductPhoto[@ProductPhotoID='5']/@LargePhoto</LargePhoto>  
  </Production.ProductPhoto>  
</ROOT>  
```  
  
### <a name="client-side-vs-server-side-xpath"></a><span data-ttu-id="df25a-143">XPath do lado do cliente e do lado do servidor</span><span class="sxs-lookup"><span data-stu-id="df25a-143">Client-side vs. Server-side XPath</span></span>  
 <span data-ttu-id="df25a-144">O XPath funciona da mesma forma no lado do cliente e no lado do servidor, exceto por estas diferenças:</span><span class="sxs-lookup"><span data-stu-id="df25a-144">Client-side XPath and server-side XPath work the same except for these differences:</span></span>  
  
-   <span data-ttu-id="df25a-145">As conversões de dados que são aplicadas quando você usa consultas XPath no lado do cliente são diferentes das aplicadas quando você usa consultas XPath no lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="df25a-145">The data conversions that are applied when you use client-side XPath queries are different from those that are applied when you use server-side XPath queries.</span></span> <span data-ttu-id="df25a-146">XPath no lado do cliente usa o modo CAST em vez de CONVERT mode 126.</span><span class="sxs-lookup"><span data-stu-id="df25a-146">Client-side XPath uses CAST instead of CONVERT mode 126.</span></span>  
  
-   <span data-ttu-id="df25a-147">Ao especificar o **cliente-XML = "0"** (false) em um modelo, você está solicitando a formatação XML do lado do servidor.</span><span class="sxs-lookup"><span data-stu-id="df25a-147">When you specify **client-side-xml="0"** (false) in a template, you are requesting server-side XML formatting.</span></span> <span data-ttu-id="df25a-148">Portanto, você não pode especificar FOR XML NESTED porque o servidor não reconhece a opção ANINHADO.</span><span class="sxs-lookup"><span data-stu-id="df25a-148">Therefore, you cannot specify FOR XML NESTED because the server does not recognize the NESTED option.</span></span> <span data-ttu-id="df25a-149">Isso gera um erro.</span><span class="sxs-lookup"><span data-stu-id="df25a-149">This generates an error.</span></span> <span data-ttu-id="df25a-150">Você deve usar os modos AUTO, RAW ou EXPLICIT, reconhecidos pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="df25a-150">You must use the AUTO, RAW, or EXPLICIT modes, which the server does recognize.</span></span>  
  
-   <span data-ttu-id="df25a-151">Ao especificar o **cliente-XML = "1"** (verdadeiro) em um modelo, você está solicitando a formatação XML do lado do cliente.</span><span class="sxs-lookup"><span data-stu-id="df25a-151">When you specify **client-side-xml="1"** (true) in a template, you are requesting client-side XML formatting.</span></span> <span data-ttu-id="df25a-152">Nesse caso, você pode especificar FOR XML NESTED.</span><span class="sxs-lookup"><span data-stu-id="df25a-152">In this case, you can specify FOR XML NESTED.</span></span> <span data-ttu-id="df25a-153">Se você especificar FOR XML AUTO, a formatação XML ocorrerá no lado do servidor, embora o **lado do cliente-XML = "1"** seja especificado no modelo.</span><span class="sxs-lookup"><span data-stu-id="df25a-153">If you specify FOR XML AUTO, the XML formatting occurs on the server side although **client-side-xml="1"** is specified in the template.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="df25a-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="df25a-154">See Also</span></span>  
 <span data-ttu-id="df25a-155">[Considerações sobre segurança de FOR XML &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="df25a-155">[FOR XML Security Considerations &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-xpath-queries/security/for-xml-security-considerations-sqlxml-4-0.md) </span></span>  
 <span data-ttu-id="df25a-156">[Formatação XML do lado do cliente &#40;SQLXML 4,0&#41;](client-side-xml-formatting-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="df25a-156">[Client-side XML Formatting &#40;SQLXML 4.0&#41;](client-side-xml-formatting-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="df25a-157">Formatação XML do lado do servidor &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="df25a-157">Server-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](server-side-xml-formatting-sqlxml-4-0.md)  
  
  
