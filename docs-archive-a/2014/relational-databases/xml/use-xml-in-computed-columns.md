---
title: Usar XML em colunas computadas | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- computed columns, XML
- XML [SQL Server], computed columns
ms.assetid: 1313b889-69b4-4018-9868-0496dd83bf44
author: rothja
ms.author: jroth
ms.openlocfilehash: 33a7549823dc3e4a23cecfa97d7345a6421cb1b4
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678659"
---
# <a name="use-xml-in-computed-columns"></a><span data-ttu-id="3474a-102">Usar XML em colunas computadas</span><span class="sxs-lookup"><span data-stu-id="3474a-102">Use XML in Computed Columns</span></span>
  <span data-ttu-id="3474a-103">Instâncias XML ser exibidas como uma origem de uma coluna computada ou como um tipo de coluna computada.</span><span class="sxs-lookup"><span data-stu-id="3474a-103">XML instances can appear as a source for a computed column, or as a type of computed column.</span></span> <span data-ttu-id="3474a-104">Os exemplos neste tópico mostram como usar XML com colunas computadas.</span><span class="sxs-lookup"><span data-stu-id="3474a-104">The examples in this topic show how to use XML with computed columns.</span></span>  
  
## <a name="creating-computed-columns-from-xml-columns"></a><span data-ttu-id="3474a-105">Criando colunas computadas de colunas XML</span><span class="sxs-lookup"><span data-stu-id="3474a-105">Creating Computed Columns from XML Columns</span></span>  
 <span data-ttu-id="3474a-106">Na instrução `CREATE TABLE` a seguir, uma coluna de tipo `xml` (`col2`) é computada a partir de `col1`:</span><span class="sxs-lookup"><span data-stu-id="3474a-106">In the following `CREATE TABLE` statement, an `xml` type column (`col2`) is computed from `col1`:</span></span>  
  
```  
CREATE TABLE T(col1 varchar(max), col2 AS CAST(col1 AS xml) )    
```  
  
 <span data-ttu-id="3474a-107">O tipo de dados `xml` também pode ser exibido como uma origem ao criar uma coluna computada, conforme mostrado na seguinte instrução `CREATE TABLE` :</span><span class="sxs-lookup"><span data-stu-id="3474a-107">The `xml` data type can also appear as a source in creating a computed column, as shown in the following `CREATE TABLE` statement:</span></span>  
  
```  
CREATE TABLE T (col1 xml, col2 as cast(col1 as varchar(1000) ))   
```  
  
 <span data-ttu-id="3474a-108">É possível criar uma coluna computada extraindo um valor de uma coluna de tipo `xml` , conforme mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="3474a-108">You can create a computed column by extracting a value from an `xml` type column as shown in the following example.</span></span> <span data-ttu-id="3474a-109">Como os métodos do tipo de dados `xml` não podem ser usados diretamente ao criar colunas computadas, o exemplo primeiro define uma função (`my_udf`) que retorna um valor de uma instância XML.</span><span class="sxs-lookup"><span data-stu-id="3474a-109">Because the `xml` data type methods cannot be used directly in creating computed columns, the example first defines a function (`my_udf`) that returns a value from an XML instance.</span></span> <span data-ttu-id="3474a-110">A função encapsula o método `value()` do tipo `xml` .</span><span class="sxs-lookup"><span data-stu-id="3474a-110">The function wraps the `value()` method of the `xml` type.</span></span> <span data-ttu-id="3474a-111">Em seguida, o nome da função é especificado na instrução `CREATE TABLE` da coluna computada.</span><span class="sxs-lookup"><span data-stu-id="3474a-111">The function name is then specified in the `CREATE TABLE` statement for the computed column.</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml) returns int  
AS BEGIN   
RETURN @var.value('(/ProductDescription/@ProductModelID)[1]' , 'int')  
END  
GO  
-- Use the function in CREATE TABLE.  
CREATE TABLE T (col1 xml, col2 as dbo.my_udf(col1) )  
GO  
-- Try adding a row.   
INSERT INTO T values('<ProductDescription ProductModelID="1" />')  
GO  
-- Verify results.  
SELECT col2, col1  
FROM T  
  
```  
  
 <span data-ttu-id="3474a-112">Como no exemplo anterior, o exemplo a seguir define uma função para retornar uma instância de tipo `xml` para uma coluna computada.</span><span class="sxs-lookup"><span data-stu-id="3474a-112">As in the previous example, the following example defines a function to return an `xml` type instance for a computed column.</span></span> <span data-ttu-id="3474a-113">Dentro da função, o método `query()` do tipo de dados `xml` recupera um valor de um parâmetro de tipo `xml` .</span><span class="sxs-lookup"><span data-stu-id="3474a-113">Inside the function, the `query()` method of the `xml` data type retrieves a value from an `xml` type parameter.</span></span>  
  
```  
CREATE FUNCTION my_udf(@var xml)   
  RETURNS xml AS   
BEGIN   
   RETURN @var.query('ProductDescription/Features')  
END  
```  
  
 <span data-ttu-id="3474a-114">Na instrução `CREATE TABLE` a seguir, `Col2` é uma coluna computada que usa os dados XML (elemento`<Features>` ) que são retornados pela função:</span><span class="sxs-lookup"><span data-stu-id="3474a-114">In the following `CREATE TABLE` statement, `Col2` is a computed column that uses the XML data (`<Features>` element) that is returned by the function:</span></span>  
  
```  
CREATE TABLE T (Col1 xml, Col2 as dbo.my_udf(Col1) )  
-- Insert a row in table T.  
INSERT INTO T VALUES('  
<ProductDescription ProductModelID="1" >  
  <Features>  
    <Feature1>description</Feature1>  
    <Feature2>description</Feature2>  
  </Features>  
</ProductDescription>')  
-- Verify the results.  
SELECT *  
FROM T  
```  
  
### <a name="in-this-section"></a><span data-ttu-id="3474a-115">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="3474a-115">In This Section</span></span>  
  
|<span data-ttu-id="3474a-116">Tópico</span><span class="sxs-lookup"><span data-stu-id="3474a-116">Topic</span></span>|<span data-ttu-id="3474a-117">Descrição</span><span class="sxs-lookup"><span data-stu-id="3474a-117">Description</span></span>|  
|-----------|-----------------|  
|[<span data-ttu-id="3474a-118">Promover valores XML frequentemente usados com colunas computadas</span><span class="sxs-lookup"><span data-stu-id="3474a-118">Promote Frequently Used XML Values with Computed Columns</span></span>](promote-frequently-used-xml-values-with-computed-columns.md)|<span data-ttu-id="3474a-119">Descreve como usar promoção de propriedades com colunas computadas e tabelas de propriedades.</span><span class="sxs-lookup"><span data-stu-id="3474a-119">Describes how to use property promotion with computed columns and property tables.</span></span>|  
  
  
