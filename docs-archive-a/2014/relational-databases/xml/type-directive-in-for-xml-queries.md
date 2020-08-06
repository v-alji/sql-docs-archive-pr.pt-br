---
title: Diretiva TYPE em consultas FOR XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- FOR XML clause, TYPE directive
- TYPE directive
ms.assetid: a3df6c30-1f25-45dc-b5a9-bd0e41921293
author: rothja
ms.author: jroth
ms.openlocfilehash: cddce90718ef5edfcf161ddc6cc52b617825a2e4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583397"
---
# <a name="type-directive-in-for-xml-queries"></a><span data-ttu-id="16a59-102">Diretiva TYPE em consultas FOR XML</span><span class="sxs-lookup"><span data-stu-id="16a59-102">TYPE Directive in FOR XML Queries</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]<span data-ttu-id="16a59-103">o suporte para o [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql) permite solicitar opcionalmente que o resultado de uma consulta for XML seja retornado como `xml` tipo de dados, ESPECIFICANDO a diretiva Type.</span><span class="sxs-lookup"><span data-stu-id="16a59-103">support for the [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql) enables you to optionally request that the result of a FOR XML query be returned as `xml` data type by specifying the TYPE directive.</span></span> <span data-ttu-id="16a59-104">Isso permite processar o resultado de uma consulta FOR XML no servidor.</span><span class="sxs-lookup"><span data-stu-id="16a59-104">This allows you to process the result of a FOR XML query on the server.</span></span> <span data-ttu-id="16a59-105">Por exemplo, você pode especificar um XQuery em relação a ele, atribuir o resultado a uma `xml` variável de tipo ou gravar [consultas for XML aninhadas](use-nested-for-xml-queries.md).</span><span class="sxs-lookup"><span data-stu-id="16a59-105">For example, you can specify an XQuery against it, assign the result to an `xml` type variable, or write [Nested FOR XML queries](use-nested-for-xml-queries.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16a59-106">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retorna dados da instância de tipo de dados XML ao cliente como um resultado das diferentes construções pelo servidor como consultas FOR XML que usam a diretiva TYPE ou onde o tipo de dados `xml` é usado para retornar valores de dados da instância XML das colunas da tabela e dos parâmetros de saída SQL.</span><span class="sxs-lookup"><span data-stu-id="16a59-106">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns XML data type instance data to the client as a result of different server-constructs such as FOR XML queries that use the TYPE directive, or where the `xml` data type is used to return XML instance data values from SQL table columns and output parameters.</span></span> <span data-ttu-id="16a59-107">No código do aplicativo cliente, o provedor ADO.NET solicita que essas informações de tipo de dados sejam enviadas em uma codificação binária do servidor.</span><span class="sxs-lookup"><span data-stu-id="16a59-107">In client application code, the ADO.NET provider requests this XML data type information to be sent in a binary encoding from the server.</span></span> <span data-ttu-id="16a59-108">Porém, se você estiver usando FOR XML sem a diretiva TYPE, os dados XML retornarão como um tipo de cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="16a59-108">However, if you are using FOR XML without the TYPE directive, the XML data comes back as a string type.</span></span> <span data-ttu-id="16a59-109">De qualquer forma, o provedor cliente sempre poderá controlar qualquer formulário de XML.</span><span class="sxs-lookup"><span data-stu-id="16a59-109">In any case, the client provider will always be able to handle either form of XML.</span></span> <span data-ttu-id="16a59-110">Observe que FOR XML de nível superior sem a diretiva TYPE não pode ser usado com cursores.</span><span class="sxs-lookup"><span data-stu-id="16a59-110">Note that top-level FOR XML without the TYPE directive cannot be used with cursors.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="16a59-111">Exemplos</span><span class="sxs-lookup"><span data-stu-id="16a59-111">Examples</span></span>  
 <span data-ttu-id="16a59-112">Os exemplos a seguir ilustram o uso da diretiva TYPE com consultas FOR XML.</span><span class="sxs-lookup"><span data-stu-id="16a59-112">The following examples illustrate the use of the TYPE directive with FOR XML queries.</span></span>  
  
### <a name="retrieving-for-xml-query-results-as-xml-type"></a><span data-ttu-id="16a59-113">Recuperando resultados de consultas FOR XML como tipo xml</span><span class="sxs-lookup"><span data-stu-id="16a59-113">Retrieving FOR XML query results as xml type</span></span>  
 <span data-ttu-id="16a59-114">A consulta a seguir recupera informações de contato de clientes da tabela `Contacts` .</span><span class="sxs-lookup"><span data-stu-id="16a59-114">The following query retrieves customer contact information from the `Contacts` table.</span></span> <span data-ttu-id="16a59-115">Como a diretiva `TYPE` é especificada em `FOR XML`, o resultado é retornado como o tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="16a59-115">Because the `TYPE` directive is specified in `FOR XML`, the result is returned as `xml` type.</span></span>  
  
```  
USE AdventureWorks2012;  
Go  
SELECT BusinessEntityID, FirstName, LastName  
FROM Person.Person  
ORDER BY BusinessEntityID  
FOR XML AUTO, TYPE;  
```  
  
 <span data-ttu-id="16a59-116">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="16a59-116">This is the partial result:</span></span>  
  
 `<Person.Person BusinessEntityID="1" FirstName="Ken" LastName="S??nchez"/>`  
  
 `<Person.Person BusinessEntityID="2" FirstName="Terri" LastName="Duffy"/>`  
  
 `...`  
  
### <a name="assigning-for-xml-query-results-to-an-xml-type-variable"></a><span data-ttu-id="16a59-117">Atribuindo resultados de consultas FOR XML a uma variável de tipo xml</span><span class="sxs-lookup"><span data-stu-id="16a59-117">Assigning FOR XML query results to an xml type variable</span></span>  
 <span data-ttu-id="16a59-118">No exemplo a seguir, um resultado de FOR XML é atribuído a uma variável de tipo `xml`, `@x`.</span><span class="sxs-lookup"><span data-stu-id="16a59-118">In the following example, a FOR XML result is assigned to an `xml` type variable, `@x`.</span></span> <span data-ttu-id="16a59-119">A consulta recupera informações de contato, como `BusinessEntityID` ,, `FirstName` `LastName` e números de telefone adicionais, da `AdditionalContactInfo` coluna de `xml``TYPE` .</span><span class="sxs-lookup"><span data-stu-id="16a59-119">The query retrieves contact information, such as the `BusinessEntityID`, `FirstName`, `LastName`, and additional telephone numbers, from the `AdditionalContactInfo` column of `xml``TYPE`.</span></span> <span data-ttu-id="16a59-120">Como a cláusula `FOR XML` especifica a diretiva `TYPE`, o XML é retornado como o tipo `xml` e é atribuído a uma variável.</span><span class="sxs-lookup"><span data-stu-id="16a59-120">Because the `FOR XML` clause specifies `TYPE` directive, the XML is returned as `xml` type and is assigned to a variable.</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @x xml;  
SET @x = (  
   SELECT BusinessEntityID,   
          FirstName,   
          LastName,   
          AdditionalContactInfo.query('  
declare namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
              //act:telephoneNumber/act:number') as MorePhoneNumbers  
   FROM Person.Person  
   FOR XML AUTO, TYPE);  
SELECT @x;  
GO  
```  
  
### <a name="querying-results-of-a-for-xml-query"></a><span data-ttu-id="16a59-121">Consultando resultados de uma consulta FOR XML</span><span class="sxs-lookup"><span data-stu-id="16a59-121">Querying results of a FOR XML query</span></span>  
 <span data-ttu-id="16a59-122">As consultas FOR XML retornam XML.</span><span class="sxs-lookup"><span data-stu-id="16a59-122">The FOR XML queries return XML.</span></span> <span data-ttu-id="16a59-123">Portanto é possível aplicar métodos de tipo `xml`, como `query()` e `value()`, ao resultado XML retornado por consultas FOR XML.</span><span class="sxs-lookup"><span data-stu-id="16a59-123">Therefore, you can apply `xml` type methods, such as `query()` and `value()`, to the XML result returned by FOR XML queries.</span></span>  
  
 <span data-ttu-id="16a59-124">Na consulta a seguir, o método `query()` do tipo de dados `xml` é usado para consultar o resultado da consulta `FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="16a59-124">In the following query, the `query()` method of the `xml` data type is used to query the result of the `FOR XML` query.</span></span> <span data-ttu-id="16a59-125">Para obter mais informações, veja [Método query&#40;&#41; &#40;tipo de dados xml&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="16a59-125">For more information, see [query&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/query-method-xml-data-type).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
SELECT (SELECT BusinessEntityID, FirstName, LastName, AdditionalContactInfo.query('  
DECLARE namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
DECLARE namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
 //act:telephoneNumber/act:number  
') AS PhoneNumbers  
FROM Person.Person  
FOR XML AUTO, TYPE).query('/Person.Person[1]');  
```  
  
 <span data-ttu-id="16a59-126">A consulta interna `SELECT ... FOR XML` retorna um resultado de tipo `xml` para o qual `SELECT` externo aplica o método `query()` ao tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="16a59-126">The inner `SELECT ... FOR XML` query returns an `xml` type result to which the outer `SELECT` applies the `query()` method to the `xml` type.</span></span> <span data-ttu-id="16a59-127">Observe a diretiva `TYPE` especificada.</span><span class="sxs-lookup"><span data-stu-id="16a59-127">Note the `TYPE` directive specified.</span></span>  
  
 <span data-ttu-id="16a59-128">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="16a59-128">This is the result:</span></span>  
  
 `<Person.Person BusinessEntityID="1" FirstName="Ken" LastName="S??nchez">`  
  
 `<PhoneNumbers>`  
  
 `<act:number xmlns:act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes">111-111-1111</act:number>`  
  
 `<act:number xmlns:act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes">112-111-1111</act:number>`  
  
 `</PhoneNumbers>`  
  
 `</Person.Person>`  
  
 <span data-ttu-id="16a59-129">Na consulta a seguir, o método `value()` do tipo de dados `xml` é usado para recuperar um valor do resultado XML retornado pela consulta `SELECT...FOR XML`.</span><span class="sxs-lookup"><span data-stu-id="16a59-129">In the following query, the `value()` method of the `xml` data type is used to retrieve a value from the XML result returned by the `SELECT...FOR XML` query.</span></span> <span data-ttu-id="16a59-130">Para obter mais informações, veja [Método value&#40;&#41; &#40;tipo de dados XML&#41;](/sql/t-sql/xml/value-method-xml-data-type).</span><span class="sxs-lookup"><span data-stu-id="16a59-130">For more information, see [value&#40;&#41; Method &#40;xml Data Type&#41;](/sql/t-sql/xml/value-method-xml-data-type).</span></span>  
  
```  
USE AdventureWorks2012;  
GO  
DECLARE @FirstPhoneFromAdditionalContactInfo varchar(40);  
SELECT @FirstPhoneFromAdditionalContactInfo =   
 ( SELECT BusinessEntityID, FirstName, LastName, AdditionalContactInfo.query('  
declare namespace aci="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactInfo";  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
   //act:telephoneNumber/act:number  
   ') AS PhoneNumbers  
   FROM Person.Person Contact  
   FOR XML AUTO, TYPE).value('  
declare namespace act="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ContactTypes";  
  /Contact[@BusinessEntityID="1"][1]/PhoneNumbers[1]/act:number[1]', 'varchar(40)'  
 )  
SELECT @FirstPhoneFromAdditionalContactInfo;  
```  
  
 <span data-ttu-id="16a59-131">A expressão de caminho XQuery no método `value()` recupera o primeiro número de telefone de contato de um cliente cujo `BusinessEntityID` é `1`.</span><span class="sxs-lookup"><span data-stu-id="16a59-131">The XQuery path expression in the `value()` method retrieves the first telephone number of a customer contact whose `BusinessEntityID` is `1`.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="16a59-132">Se a diretiva TYPE não estiver especificada, o resultado da consulta FOR XML será retornado como tipo `nvarchar(max)`.</span><span class="sxs-lookup"><span data-stu-id="16a59-132">If the TYPE directive is not specified, the FOR XML query result is returned as type `nvarchar(max)`.</span></span>  
  
### <a name="using-for-xml-query-results-in-insert-update-and-delete-transact-sql-dml"></a><span data-ttu-id="16a59-133">Usando resultados de consulta FOR XML em INSERT, UPDATE e DELETE (DML do Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="16a59-133">Using FOR XML query results in INSERT, UPDATE, and DELETE (Transact-SQL DML)</span></span>  
 <span data-ttu-id="16a59-134">O exemplo a seguir demonstra como consultas FOR XML podem ser usadas em instruções DML (linguagem de manipulação de dados).</span><span class="sxs-lookup"><span data-stu-id="16a59-134">The following example demonstrates how FOR XML queries can be used in Data Manipulation Language (DML) statements.</span></span> <span data-ttu-id="16a59-135">No exemplo, o `FOR XML` retorna uma instância de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="16a59-135">In the example, the `FOR XML` returns an instance of `xml` type.</span></span> <span data-ttu-id="16a59-136">A instrução `INSERT` insere esse XML em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="16a59-136">The `INSERT` statement inserts this XML into a table.</span></span>  
  
```  
CREATE TABLE T1(intCol int, XmlCol xml);  
GO  
INSERT INTO T1   
VALUES(1, '<Root><ProductDescription ProductModelID="1" /></Root>');  
GO  
  
CREATE TABLE T2(XmlCol xml)  
GO  
INSERT INTO T2(XmlCol)   
SELECT (SELECT XmlCol.query('/Root')   
        FROM T1   
        FOR XML AUTO,TYPE);   
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="16a59-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="16a59-137">See Also</span></span>  
 [<span data-ttu-id="16a59-138">FOR XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="16a59-138">FOR XML &#40;SQL Server&#41;</span></span>](../xml/for-xml-sql-server.md)  
  
  
