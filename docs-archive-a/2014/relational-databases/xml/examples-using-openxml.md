---
title: 'Exemplos: Usando OPENXML | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- ColPattern [XML in SQL Server]
- XML [SQL Server], mapping data
- OPENXML statement, about OPENXML statement
- overflow in XML document [SQL Server]
- mapping XML data [SQL Server]
- combining attribute-centric and element centric mapping
- unconsumed data
- attribute-centric mapping
- column patterns [XML in SQL Server]
- XML [SQL Server], overflow handling
- row patterns [XML in SQL Server]
- rowpattern [XML in SQL Server]
- flags parameter
- element-centric mapping [SQL Server]
- edge tables
ms.assetid: 689297f3-adb0-4d8d-bf62-cfda26210164
author: rothja
ms.author: jroth
ms.openlocfilehash: 09fc6ad073b12df2f9fbd8ebc6a59149f6154ced
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686202"
---
# <a name="examples-using-openxml"></a><span data-ttu-id="d9304-102">Exemplos: uso do OPENXML</span><span class="sxs-lookup"><span data-stu-id="d9304-102">Examples: Using OPENXML</span></span>
  <span data-ttu-id="d9304-103">Os exemplos neste tópico mostram como o OPENXML é usado para criar uma exibição de conjunto de linhas de um documento XML.</span><span class="sxs-lookup"><span data-stu-id="d9304-103">The examples in this topic show how OPENXML is used to create a rowset view of an XML document.</span></span> <span data-ttu-id="d9304-104">Para obter informações sobre a sintaxe do OPENXML, veja [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="d9304-104">For information about the syntax of OPENXML, see [OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql).</span></span> <span data-ttu-id="d9304-105">Os exemplos mostram todos os aspectos do OPENXML, mas não especificam metapropriedades no OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-105">The examples show all aspects of OPENXML, but do not specify metaproperties in OPENXML.</span></span> <span data-ttu-id="d9304-106">Para obter mais informações sobre como especificar metapropriedades no OPENXML, veja [Especificar metapropriedades no OPENXML](specify-metaproperties-in-openxml.md).</span><span class="sxs-lookup"><span data-stu-id="d9304-106">For more information about how to specify metaproperties in OPENXML, see [Specify Metaproperties in OPENXML](specify-metaproperties-in-openxml.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="d9304-107">Exemplos</span><span class="sxs-lookup"><span data-stu-id="d9304-107">Examples</span></span>  
 <span data-ttu-id="d9304-108">Ao recuperar dados, *rowpattern* é usado para identificar os nós no documento XML que determinam as linhas.</span><span class="sxs-lookup"><span data-stu-id="d9304-108">In retrieving the data, *rowpattern* is used to identify the nodes in the XML document that determine the rows.</span></span> <span data-ttu-id="d9304-109">Além disso, *rowpattern* é expressado na linguagem padrão XPath que é usada na implementação do MSXML XPath.</span><span class="sxs-lookup"><span data-stu-id="d9304-109">Additionally, *rowpattern* is expressed in the XPath pattern language that is used in the MSXML XPath implementation.</span></span> <span data-ttu-id="d9304-110">Por exemplo, se o padrão terminar em um elemento ou atributo, uma linha será criada para cada elemento ou atributo selecionado por *rowpattern*.</span><span class="sxs-lookup"><span data-stu-id="d9304-110">For example, if the pattern ends in an element or an attribute, a row is created for each element or attribute node that is selected by *rowpattern*.</span></span>  
  
 <span data-ttu-id="d9304-111">O valor de *flags* fornece o mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="d9304-111">The *flags* value provides default mapping.</span></span> <span data-ttu-id="d9304-112">Se nenhum *ColPattern* for especificado no *SchemaDeclaration*, o mapeamento especificado em *flags* será assumido.</span><span class="sxs-lookup"><span data-stu-id="d9304-112">If no *ColPattern* is specified in the *SchemaDeclaration*, the mapping specified in *flags* is assumed.</span></span> <span data-ttu-id="d9304-113">O valor de *flags* será ignorado se *ColPattern* estiver especificado em *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="d9304-113">The *flags* value is ignored if *ColPattern* is specified in *SchemaDeclaration*.</span></span> <span data-ttu-id="d9304-114">O *ColPattern* especificado determina o mapeamento centrado em atributo ou centrado em elemento e também o comportamento para manipulação de dados não consumidos ou de estouro.</span><span class="sxs-lookup"><span data-stu-id="d9304-114">The specified *ColPattern* determines the mapping, attribute-centric or element-centric, and also the behavior in dealing with overflow and unconsumed data.</span></span>  
  
### <a name="a-executing-a-simple-select-statement-with-openxml"></a><span data-ttu-id="d9304-115">a.</span><span class="sxs-lookup"><span data-stu-id="d9304-115">A.</span></span> <span data-ttu-id="d9304-116">Executando uma instrução SELECT simples com OPENXML</span><span class="sxs-lookup"><span data-stu-id="d9304-116">Executing a simple SELECT statement with OPENXML</span></span>  
 <span data-ttu-id="d9304-117">O documento XML neste exemplo é composto dos elementos <`Customer`>, <`Order`>e <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="d9304-117">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="d9304-118">A instrução OPENXML recupera informações do cliente em um conjunto de linhas de duas colunas, **CustomerID** e **ContactName**, do documento XML.</span><span class="sxs-lookup"><span data-stu-id="d9304-118">The OPENXML statement retrieves customer information in a two-column rowset, **CustomerID** and **ContactName**, from the XML document.</span></span>  
  
 <span data-ttu-id="d9304-119">Primeiro, o procedimento armazenado **sp_xml_preparedocument** é chamado para obter um identificador de documento.</span><span class="sxs-lookup"><span data-stu-id="d9304-119">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="d9304-120">Esse identificador de documento é passado para o OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-120">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="d9304-121">A instrução OPENXML ilustra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d9304-121">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="d9304-122">*rowpattern* (/ROOT/Customer) identifica os nós <`Customer`> a serem processados.</span><span class="sxs-lookup"><span data-stu-id="d9304-122">*rowpattern* (/ROOT/Customer) identifies the <`Customer`> nodes to process.</span></span>  
  
-   <span data-ttu-id="d9304-123">O valor do parâmetro *flags* é definido como **1** e indica o mapeamento centrado em atributo.</span><span class="sxs-lookup"><span data-stu-id="d9304-123">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="d9304-124">Como resultado, os atributos XML são mapeados para as colunas no conjunto de linhas definido em *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="d9304-124">As a result, the XML attributes map to the columns in the rowset defined in *SchemaDeclaration*.</span></span>  
  
-   <span data-ttu-id="d9304-125">Em *SchemaDeclaration*, na cláusula WITH, os valores de *ColName* especificados correspondem aos nomes dos atributos XML correspondentes.</span><span class="sxs-lookup"><span data-stu-id="d9304-125">In *SchemaDeclaration*, in the WITH clause, the specified *ColName* values match the corresponding XML attribute names.</span></span> <span data-ttu-id="d9304-126">Portanto o parâmetro *ColPattern* não é especificado em *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="d9304-126">Therefore, the *ColPattern* parameter is not specified in *SchemaDeclaration*.</span></span>  
  
 <span data-ttu-id="d9304-127">Em seguida, a instrução SELECT recupera todas as colunas no conjunto de linhas fornecido pelo OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-127">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @DocHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
          OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
          OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @DocHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@DocHandle, '/ROOT/Customer',1)  
      WITH (CustomerID  varchar(10),  
            ContactName varchar(20))  
EXEC sp_xml_removedocument @DocHandle  
```  
  
 <span data-ttu-id="d9304-128">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="d9304-128">This is the result:</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="d9304-129">Como os elementos <`Customer`> não têm nenhum subelemento, se a mesma instrução SELECT for executada com *flags* definido como **2** para indicar mapeamento centrado em elemento, os valores de **CustomerID** e **ContactName** dos dois clientes serão retornados como NULL.</span><span class="sxs-lookup"><span data-stu-id="d9304-129">Because the <`Customer`> elements do not have any subelements, if the same SELECT statement is executed with *flags* set to **2** to indicate element-centric mapping, the values of **CustomerID** and **ContactName** for both the customers are returned as NULL.</span></span>  
  
 <span data-ttu-id="d9304-130">O @xmlDocument também pode ser do tipo **xml** ou do tipo **(n)varchar(max)**.</span><span class="sxs-lookup"><span data-stu-id="d9304-130">The @xmlDocument can also be of **xml** type or of **(n)varchar(max)** type.</span></span>  
  
 <span data-ttu-id="d9304-131">Se <`CustomerID`> e <`ContactName`> no documento XML forem subelementos, o mapeamento centrado em elemento recuperará os valores.</span><span class="sxs-lookup"><span data-stu-id="d9304-131">If <`CustomerID`> and <`ContactName`> in the XML document are subelements, the element-centric mapping retrieves the values.</span></span>  
  
```  
DECLARE @XmlDocumentHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer>  
   <CustomerID>VINET</CustomerID>  
   <ContactName>Paul Henriot</ContactName>  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5" OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer>     
   <CustomerID>LILAS</CustomerID>  
   <ContactName>Carlos Gonzlez</ContactName>  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3" OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @XmlDocumentHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT    *  
FROM      OPENXML (@XmlDocumentHandle, '/ROOT/Customer',2)  
           WITH (CustomerID  varchar(10),  
                 ContactName varchar(20))  
EXEC sp_xml_removedocument @XmlDocumentHandle  
```  
  
 <span data-ttu-id="d9304-132">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="d9304-132">This is the result:</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="d9304-133">Observe que o identificador de documento retornado por **sp_xml_preparedocument** é válido durante o lote e não durante a sessão.</span><span class="sxs-lookup"><span data-stu-id="d9304-133">Note that the document handle returned by **sp_xml_preparedocument** is valid for the duration of the batch and not the session.</span></span>  
  
### <a name="b-specifying-colpattern-for-mapping-between-rowset-columns-and-the-xml-attributes-and-elements"></a><span data-ttu-id="d9304-134">B.</span><span class="sxs-lookup"><span data-stu-id="d9304-134">B.</span></span> <span data-ttu-id="d9304-135">Especificando ColPattern para mapeamento entre colunas do conjunto de linhas e os elementos e atributos XML</span><span class="sxs-lookup"><span data-stu-id="d9304-135">Specifying ColPattern for mapping between rowset columns and the XML attributes and elements</span></span>  
 <span data-ttu-id="d9304-136">Este exemplo mostra como o padrão Xpath é especificado no parâmetro *ColPattern* opcional para fornecer mapeamento entre colunas do conjunto de linhas e os elementos e atributos XML.</span><span class="sxs-lookup"><span data-stu-id="d9304-136">This example shows how the XPath pattern is specified in the optional *ColPattern* parameter to provide mapping between rowset columns and the XML attributes and elements.</span></span>  
  
 <span data-ttu-id="d9304-137">O documento XML neste exemplo é composto dos elementos <`Customer`>, <`Order`>e <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="d9304-137">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="d9304-138">A instrução OPENXML recupera informações do cliente e do pedido como um conjunto de linhas (**CustomerID**, **OrderDate**, **ProdID**e **Qty**) do documento XML.</span><span class="sxs-lookup"><span data-stu-id="d9304-138">The OPENXML statement retrieves customer and order information as a rowset (**CustomerID**, **OrderDate**, **ProdID**, and **Qty**) from the XML document.</span></span>  
  
 <span data-ttu-id="d9304-139">Primeiro, o procedimento armazenado **sp_xml_preparedocument** é chamado para obter um identificador de documento.</span><span class="sxs-lookup"><span data-stu-id="d9304-139">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="d9304-140">Esse identificador de documento é passado para o OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-140">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="d9304-141">A instrução OPENXML ilustra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d9304-141">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="d9304-142">*rowpattern* (/ROOT/Customer/Order/OrderDetail) identifica os nós <`OrderDetail`> a serem processados.</span><span class="sxs-lookup"><span data-stu-id="d9304-142">*rowpattern* (/ROOT/Customer/Order/OrderDetail) identifies the <`OrderDetail`> nodes to process.</span></span>  
  
 <span data-ttu-id="d9304-143">Para fins ilustrativos, o valor do parâmetro *flags* está definido como **2** e indica mapeamento centrado em elemento.</span><span class="sxs-lookup"><span data-stu-id="d9304-143">For illustration, the *flags* parameter value is set to **2** and indicates element-centric mapping.</span></span> <span data-ttu-id="d9304-144">No entanto o mapeamento especificado em *ColPattern* substitui esse mapeamento.</span><span class="sxs-lookup"><span data-stu-id="d9304-144">However, the mapping specified in *ColPattern* overwrites this mapping.</span></span> <span data-ttu-id="d9304-145">Quer dizer, o padrão XPath especificado em *ColPattern* mapeia as colunas do conjunto de linhas para atributos.</span><span class="sxs-lookup"><span data-stu-id="d9304-145">That is, the XPath pattern specified in *ColPattern* maps the columns in the rowset to attributes.</span></span> <span data-ttu-id="d9304-146">Isso resulta em mapeamento centrado em atributo.</span><span class="sxs-lookup"><span data-stu-id="d9304-146">This results in attribute-centric mapping.</span></span>  
  
 <span data-ttu-id="d9304-147">Em *SchemaDeclaration*, cláusula WITH, *ColPattern* também é especificado com os parâmetros *ColName* e *ColType* .</span><span class="sxs-lookup"><span data-stu-id="d9304-147">In *SchemaDeclaration*, in the WITH clause, *ColPattern* is also specified with the *ColName* and *ColType* parameters.</span></span> <span data-ttu-id="d9304-148">O *ColPattern* opcional é o padrão XPath especificado e indica o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d9304-148">The optional *ColPattern* is the XPath pattern specified and indicates the following:</span></span>  
  
-   <span data-ttu-id="d9304-149">As colunas **OrderID**, **CustomerID** e **OrderDate** no conjunto de linhas são mapeadas para os atributos do pai dos nós identificados por *rowpattern*, e *rowpattern* identifica os nós <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="d9304-149">The **OrderID**, **CustomerID**, and **OrderDate** columns in the rowset map to the attributes of the parent of the nodes identified by *rowpattern*, and *rowpattern* identifies the <`OrderDetail`> nodes.</span></span> <span data-ttu-id="d9304-150">Portanto as colunas **CustomerID** e **OrderDate** são mapeadas para os atributos **CustomerID** e **OrderDate** do elemento <`Order`>.</span><span class="sxs-lookup"><span data-stu-id="d9304-150">Therefore, the **CustomerID** and **OrderDate** columns map to **CustomerID** and **OrderDate** attributes of the <`Order`> element.</span></span>  
  
-   <span data-ttu-id="d9304-151">As colunas **ProdID** e **Qty** do conjunto de linhas são mapeadas para os atributos **ProductID** e **Quantity** dos nós identificados em *rowpattern*.</span><span class="sxs-lookup"><span data-stu-id="d9304-151">The **ProdID** and **Qty** columns in the rowset map to the **ProductID** and **Quantity** attributes of the nodes identified in *rowpattern*.</span></span>  
  
 <span data-ttu-id="d9304-152">Em seguida, a instrução SELECT recupera todas as colunas no conjunto de linhas fornecido pelo OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-152">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @XmlDocumentHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
           OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
           OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @XmlDocumentHandle OUTPUT, @XmlDocument  
-- Execute a SELECT stmt using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@XmlDocumentHandle, '/ROOT/Customer/Order/OrderDetail',2)  
WITH (OrderID     int         '../@OrderID',  
      CustomerID  varchar(10) '../@CustomerID',  
      OrderDate   datetime    '../@OrderDate',  
      ProdID      int         '@ProductID',  
      Qty         int         '@Quantity')  
EXEC sp_xml_removedocument @XmlDocumentHandle  
```  
  
 <span data-ttu-id="d9304-153">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="d9304-153">This is the result:</span></span>  
  
```  
OrderID CustomerID        OrderDate          ProdID    Qty  
-------------------------------------------------------------  
10248    VINET     1996-07-04 00:00:00.000     11       12  
10248    VINET     1996-07-04 00:00:00.000     42       10  
10283    LILAS     1996-08-16 00:00:00.000     72        3  
```  
  
 <span data-ttu-id="d9304-154">O padrão XPath especificado como *ColPattern* também pode ser especificado para mapear os elementos XML para as colunas do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="d9304-154">The XPath pattern specified as *ColPattern* can also be specified to map the XML elements to the rowset columns.</span></span> <span data-ttu-id="d9304-155">Isso resulta em mapeamento centrado em elemento.</span><span class="sxs-lookup"><span data-stu-id="d9304-155">This results in element-centric mapping.</span></span> <span data-ttu-id="d9304-156">No exemplo seguinte, o documento XML <`CustomerID`> e <`OrderDate`> são subelementos do elemento <`Orders`>.</span><span class="sxs-lookup"><span data-stu-id="d9304-156">In the following example, the XML document <`CustomerID`> and <`OrderDate`> are subelements of the <`Orders`> element.</span></span> <span data-ttu-id="d9304-157">Como *ColPattern* substitui o mapeamento especificado no parâmetro *flags* , o parâmetro *flags* não é especificado no OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-157">Because *ColPattern* overwrites the mapping specified in the *flags* parameter, the *flags* parameter is not specified in OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order EmployeeID="5" >  
      <OrderID>10248</OrderID>  
      <CustomerID>VINET</CustomerID>  
      <OrderDate>1996-07-04T00:00:00</OrderDate>  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order  EmployeeID="3" >  
      <OrderID>10283</OrderID>  
      <CustomerID>LILAS</CustomerID>  
      <OrderDate>1996-08-16T00:00:00</OrderDate>  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @XmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer/Order/OrderDetail')  
WITH (CustomerID  varchar(10)   '../CustomerID',  
      OrderDate   datetime      '../OrderDate',  
      ProdID      int           '@ProductID',  
      Qty         int           '@Quantity')  
EXEC sp_xml_removedocument @docHandle  
```  
  
### <a name="c-combining-attribute-centric-and-element-centric-mapping"></a><span data-ttu-id="d9304-158">C.</span><span class="sxs-lookup"><span data-stu-id="d9304-158">C.</span></span> <span data-ttu-id="d9304-159">Combinando o mapeamento centrado em elemento e centrado em atributo</span><span class="sxs-lookup"><span data-stu-id="d9304-159">Combining attribute-centric and element-centric mapping</span></span>  
 <span data-ttu-id="d9304-160">Neste exemplo, o parâmetro *flags* está definido como **3** e indica que o mapeamento centrado em atributo e o mapeamento centrado em elemento serão aplicados.</span><span class="sxs-lookup"><span data-stu-id="d9304-160">In this example, the *flags* parameter is set to **3** and indicates that both attribute-centric and element-centric mapping will be applied.</span></span> <span data-ttu-id="d9304-161">Nesse caso, o mapeamento centrado em atributo é aplicado primeiro e, em seguida, o mapeamento centrado em elemento é aplicado a todas as colunas que ainda não foram tratadas.</span><span class="sxs-lookup"><span data-stu-id="d9304-161">In this case, the attribute-centric mapping is applied first, and then element-centric mapping is applied for all the columns not yet dealt with.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @XmlDocument nvarchar(1000)  
SET @XmlDocument =N'<ROOT>  
<Customer CustomerID="VINET"  >  
     <ContactName>Paul Henriot</ContactName>  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5"   
          OrderDate="1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" >   
     <ContactName>Carlos Gonzlez</ContactName>  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3"   
          OrderDate="1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @XmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer',3)  
      WITH (CustomerID  varchar(10),  
            ContactName varchar(20))  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="d9304-162">Este será o resultado</span><span class="sxs-lookup"><span data-stu-id="d9304-162">This is the result</span></span>  
  
```  
CustomerID ContactName            
---------- --------------------   
VINET      Paul Henriot  
LILAS      Carlos Gonzlez  
```  
  
 <span data-ttu-id="d9304-163">O mapeamento centrado em atributo é aplicado para **CustomerID**.</span><span class="sxs-lookup"><span data-stu-id="d9304-163">The attribute-centric mapping is applied for **CustomerID**.</span></span> <span data-ttu-id="d9304-164">Não há nenhum atributo **ContactName** no elemento <`Customer`>.</span><span class="sxs-lookup"><span data-stu-id="d9304-164">There is no **ContactName** attribute in the <`Customer`> element.</span></span> <span data-ttu-id="d9304-165">Portanto o mapeamento centrado em elemento é aplicado.</span><span class="sxs-lookup"><span data-stu-id="d9304-165">Therefore, element-centric mapping is applied.</span></span>  
  
### <a name="d-specifying-the-text-xpath-function-as-colpattern"></a><span data-ttu-id="d9304-166">D.</span><span class="sxs-lookup"><span data-stu-id="d9304-166">D.</span></span> <span data-ttu-id="d9304-167">Especificando a função text() XPath como ColPattern</span><span class="sxs-lookup"><span data-stu-id="d9304-167">Specifying the text() XPath function as ColPattern</span></span>  
 <span data-ttu-id="d9304-168">O documento XML neste exemplo é composto dos elementos <`Customer`> e <`Order`>.</span><span class="sxs-lookup"><span data-stu-id="d9304-168">The XML document in this example is made up of the <`Customer`> and <`Order`> elements.</span></span> <span data-ttu-id="d9304-169">A instrução OPENXML recupera um conjunto de linhas composto do atributo **oid** do elemento <`Order`>, a ID do pai do nó identificado por *rowpattern* e a cadeia de caracteres do valor de folha do conteúdo do elemento.</span><span class="sxs-lookup"><span data-stu-id="d9304-169">The OPENXML statement retrieves a rowset that is made up of the **oid** attribute from the <`Order`> element, the ID of the parent of the node identified by *rowpattern*, and the leaf-value string of the element content.</span></span>  
  
 <span data-ttu-id="d9304-170">Primeiro, o procedimento armazenado **sp_xml_preparedocument** é chamado para obter um identificador de documento.</span><span class="sxs-lookup"><span data-stu-id="d9304-170">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="d9304-171">Esse identificador de documento é passado para o OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-171">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="d9304-172">A instrução OPENXML ilustra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d9304-172">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="d9304-173">*rowpattern* (/root/Customer/Order) identifica os nós <`Order`> a serem processados.</span><span class="sxs-lookup"><span data-stu-id="d9304-173">*rowpattern* (/root/Customer/Order) identifies the <`Order`> nodes to process.</span></span>  
  
-   <span data-ttu-id="d9304-174">O valor do parâmetro *flags* é definido como **1** e indica o mapeamento centrado em atributo.</span><span class="sxs-lookup"><span data-stu-id="d9304-174">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="d9304-175">Como resultado, os atributos XML são mapeados para as colunas do conjunto de linhas definidas em *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="d9304-175">As a result, the XML attributes map to the rowset columns defined in *SchemaDeclaration*.</span></span>  
  
-   <span data-ttu-id="d9304-176">Em *SchemaDeclaration* na cláusula WITH, os nomes das colunas do conjunto de linhas **oid** e **amount** coincidem com os nomes dos atributos XML correspondentes.</span><span class="sxs-lookup"><span data-stu-id="d9304-176">In *SchemaDeclaration* in the WITH clause, the **oid** and **amount** rowset column names match the corresponding XML attribute names.</span></span> <span data-ttu-id="d9304-177">Portanto o parâmetro *ColPattern* não é especificado.</span><span class="sxs-lookup"><span data-stu-id="d9304-177">Therefore, the *ColPattern* parameter is not specified.</span></span> <span data-ttu-id="d9304-178">Para a coluna **comment** do conjunto de linhas, a função XPath, **text()** , é especificada como *ColPattern*.</span><span class="sxs-lookup"><span data-stu-id="d9304-178">For the **comment** column in the rowset, the XPath function, **text()**, is specified as *ColPattern*.</span></span> <span data-ttu-id="d9304-179">Isso substitui o mapeamento centrado em atributo especificado em *flags*, e a coluna contém a cadeia de caracteres do valor de folha do conteúdo do elemento.</span><span class="sxs-lookup"><span data-stu-id="d9304-179">This overwrites the attribute-centric mapping specified in *flags*, and the column contains the leaf-value string of the element content.</span></span>  
  
 <span data-ttu-id="d9304-180">Em seguida, a instrução SELECT recupera todas as colunas no conjunto de linhas fornecido pelo OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-180">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
--sample XML document  
SET @xmlDocument =N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very satisfied  
      </Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
            <Urgency>Important</Urgency>  
            Happy Customer.  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/root/Customer/Order', 1)  
     WITH (oid     char(5),   
           amount  float,   
           comment ntext 'text()')  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="d9304-181">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="d9304-181">This is the result:</span></span>  
  
```  
oid   amount        comment  
----- -----------   -----------------------------  
O1    3.5           NULL  
O2    13.4          Customer was very satisfied  
O3    100.0         Happy Customer.  
O4    10000.0       NULL  
```  
  
### <a name="e-specifying-tablename-in-the-with-clause"></a><span data-ttu-id="d9304-182">E.</span><span class="sxs-lookup"><span data-stu-id="d9304-182">E.</span></span> <span data-ttu-id="d9304-183">Especificando TableName na cláusula WITH</span><span class="sxs-lookup"><span data-stu-id="d9304-183">Specifying TableName in the WITH clause</span></span>  
 <span data-ttu-id="d9304-184">Este exemplo especifica *TableName* na cláusula WITH em vez de *SchemaDeclaration*.</span><span class="sxs-lookup"><span data-stu-id="d9304-184">This example specifies *TableName* in the WITH clause instead of *SchemaDeclaration*.</span></span> <span data-ttu-id="d9304-185">Isso será útil se você tiver uma tabela que tem a estrutura desejada e nenhum padrão de coluna, parâmetro *ColPattern* , é necessário.</span><span class="sxs-lookup"><span data-stu-id="d9304-185">This is useful if you have a table that has the structure you want and no column patterns, *ColPattern* parameter, are required.</span></span>  
  
 <span data-ttu-id="d9304-186">O documento XML neste exemplo é composto dos elementos <`Customer`> e <`Order`>.</span><span class="sxs-lookup"><span data-stu-id="d9304-186">The XML document in this example is made up of the <`Customer`> and <`Order`> elements.</span></span> <span data-ttu-id="d9304-187">A instrução OPENXML recupera informações de pedido em um conjunto de linhas de três colunas (**oid**, **date**e **amount**) do documento XML.</span><span class="sxs-lookup"><span data-stu-id="d9304-187">The OPENXML statement retrieves order information in a three-column rowset (**oid**, **date**, and **amount**) from the XML document.</span></span>  
  
 <span data-ttu-id="d9304-188">Primeiro, o procedimento armazenado **sp_xml_preparedocument** é chamado para obter um identificador de documento.</span><span class="sxs-lookup"><span data-stu-id="d9304-188">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="d9304-189">Esse identificador de documento é passado para o OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-189">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="d9304-190">A instrução OPENXML ilustra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d9304-190">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="d9304-191">*rowpattern* (/root/Customer/Order) identifica os nós <`Order`> a serem processados.</span><span class="sxs-lookup"><span data-stu-id="d9304-191">*rowpattern* (/root/Customer/Order) identifies the <`Order`> nodes to process.</span></span>  
  
-   <span data-ttu-id="d9304-192">Não há nenhum *SchemaDeclaration* na cláusula WITH.</span><span class="sxs-lookup"><span data-stu-id="d9304-192">There is no *SchemaDeclaration* in the WITH clause.</span></span> <span data-ttu-id="d9304-193">Em vez disso, um nome de tabela é especificado.</span><span class="sxs-lookup"><span data-stu-id="d9304-193">Instead, a table name is specified.</span></span> <span data-ttu-id="d9304-194">Portanto o esquema da tabela é usado como o esquema do conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="d9304-194">Therefore, the table schema is used as the rowset schema.</span></span>  
  
-   <span data-ttu-id="d9304-195">O valor do parâmetro *flags* é definido como **1** e indica o mapeamento centrado em atributo.</span><span class="sxs-lookup"><span data-stu-id="d9304-195">The *flags* parameter value is set to **1** and indicates attribute-centric mapping.</span></span> <span data-ttu-id="d9304-196">Portanto os atributos dos elementos identificados por *rowpattern*são mapeados para as colunas do conjunto de linhas com o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="d9304-196">Therefore, attributes of the elements, identified by *rowpattern*, map to the rowset columns with the same name.</span></span>  
  
 <span data-ttu-id="d9304-197">Em seguida, a instrução SELECT recupera todas as colunas no conjunto de linhas fornecido pelo OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-197">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
-- Create a test table. This table schema is used by OPENXML as the  
-- rowset schema.  
CREATE TABLE T1(oid char(5), date datetime, amount float)  
GO  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
-- Sample XML document  
SET @xmlDocument =N'<root>  
  <Customer cid= "C1" name="Janine" city="Issaquah">  
      <Order oid="O1" date="1/20/1996" amount="3.5" />  
      <Order oid="O2" date="4/30/1997" amount="13.4">Customer was very   
             satisfied</Order>  
   </Customer>  
   <Customer cid="C2" name="Ursula" city="Oelde" >  
      <Order oid="O3" date="7/14/1999" amount="100" note="Wrap it blue   
             white red">  
          <Urgency>Important</Urgency>  
      </Order>  
      <Order oid="O4" date="1/20/1996" amount="10000"/>  
   </Customer>  
</root>'  
--Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/root/Customer/Order', 1)  
     WITH T1  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="d9304-198">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="d9304-198">This is the result:</span></span>  
  
```  
oid   date                        amount  
----- --------------------------- ----------  
O1    1996-01-20 00:00:00.000     3.5  
O2    1997-04-30 00:00:00.000     13.4  
O3    1999-07-14 00:00:00.000     100.0  
O4    1996-01-20 00:00:00.000     10000.0  
```  
  
### <a name="f-obtaining-the-result-in-an-edge-table-format"></a><span data-ttu-id="d9304-199">F.</span><span class="sxs-lookup"><span data-stu-id="d9304-199">F.</span></span> <span data-ttu-id="d9304-200">Obtendo o resultado em um formato de tabela de borda</span><span class="sxs-lookup"><span data-stu-id="d9304-200">Obtaining the result in an edge table format</span></span>  
 <span data-ttu-id="d9304-201">Neste exemplo, a cláusula WITH não é especificada na instrução OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-201">In this example, the WITH clause is not specified in the OPENXML statement.</span></span> <span data-ttu-id="d9304-202">Como resultado, o conjunto de linhas gerado por OPENXML tem um formato de tabela de borda.</span><span class="sxs-lookup"><span data-stu-id="d9304-202">As a result, the rowset generated by OPENXML has an edge table format.</span></span> <span data-ttu-id="d9304-203">A instrução SELECT retorna todas as colunas da tabela de borda.</span><span class="sxs-lookup"><span data-stu-id="d9304-203">The SELECT statement returns all the columns in the edge table.</span></span>  
  
 <span data-ttu-id="d9304-204">O documento XML de exemplo é composto dos elementos <`Customer`>, <`Order`> e <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="d9304-204">The sample XML document in the example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span>  
  
 <span data-ttu-id="d9304-205">Primeiro, o procedimento armazenado **sp_xml_preparedocument** é chamado para obter um identificador de documento.</span><span class="sxs-lookup"><span data-stu-id="d9304-205">First, the **sp_xml_preparedocument** stored procedure is called to obtain a document handle.</span></span> <span data-ttu-id="d9304-206">Esse identificador de documento é passado para o OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-206">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="d9304-207">A instrução OPENXML ilustra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d9304-207">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="d9304-208">*rowpattern* (/ROOT/Customer) identifica os nós <`Customer`> a serem processados.</span><span class="sxs-lookup"><span data-stu-id="d9304-208">*rowpattern* (/ROOT/Customer) identifies the <`Customer`> nodes to process.</span></span>  
  
-   <span data-ttu-id="d9304-209">A cláusula WITH não é fornecida.</span><span class="sxs-lookup"><span data-stu-id="d9304-209">The WITH clause is not provided.</span></span> <span data-ttu-id="d9304-210">Portanto o OPENXML retorna o conjunto de linhas em um formato de tabela de borda.</span><span class="sxs-lookup"><span data-stu-id="d9304-210">Therefore, OPENXML returns the rowset in an edge table format.</span></span>  
  
 <span data-ttu-id="d9304-211">Em seguida, a instrução SELECT retorna todas as colunas da tabela de borda.</span><span class="sxs-lookup"><span data-stu-id="d9304-211">The SELECT statement then retrieves all the columns in the edge table.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
SET @xmlDocument = N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order CustomerID="VINET" EmployeeID="5" OrderDate=  
           "1996-07-04T00:00:00">  
      <OrderDetail OrderID="10248" ProductID="11" Quantity="12"/>  
      <OrderDetail OrderID="10248" ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order CustomerID="LILAS" EmployeeID="3" OrderDate=  
           "1996-08-16T00:00:00">  
      <OrderDetail OrderID="10283" ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
--Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer')  
  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="d9304-212">O resultado é retornado como uma tabela de borda.</span><span class="sxs-lookup"><span data-stu-id="d9304-212">The result is returned as an edge table.</span></span> <span data-ttu-id="d9304-213">É possível escrever consultas em relação à tabela de borda para obter informações.</span><span class="sxs-lookup"><span data-stu-id="d9304-213">You can write queries against the edge table to obtain information.</span></span> <span data-ttu-id="d9304-214">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d9304-214">For example:</span></span>  
  
-   <span data-ttu-id="d9304-215">A consulta a seguir retorna o número de nós **Customer** no documento.</span><span class="sxs-lookup"><span data-stu-id="d9304-215">The following query returns the number of **Customer** nodes in the document.</span></span> <span data-ttu-id="d9304-216">Como a cláusula WITH não é especificada, o OPENXML retorna uma tabela de borda.</span><span class="sxs-lookup"><span data-stu-id="d9304-216">Because the WITH clause is not specified, OPENXML returns an edge table.</span></span> <span data-ttu-id="d9304-217">A instrução SELECT consulta a tabela de borda.</span><span class="sxs-lookup"><span data-stu-id="d9304-217">The SELECT statement queries the edge table.</span></span>  
  
    ```  
    SELECT count(*)  
    FROM OPENXML(@docHandle, '/')  
    WHERE localname = 'Customer'  
    ```  
  
-   <span data-ttu-id="d9304-218">A consulta a seguir retorna os nomes locais de nós XML do tipo do elemento.</span><span class="sxs-lookup"><span data-stu-id="d9304-218">The following query returns the local names of XML nodes of element type.</span></span>  
  
    ```  
    SELECT distinct localname   
    FROM OPENXML(@docHandle, '/')   
    WHERE nodetype = 1   
    ORDER BY localname  
    ```  
  
### <a name="g-specifying-rowpattern-ending-with-an-attribute"></a><span data-ttu-id="d9304-219">G.</span><span class="sxs-lookup"><span data-stu-id="d9304-219">G.</span></span> <span data-ttu-id="d9304-220">Especificando rowpattern terminando com um atributo</span><span class="sxs-lookup"><span data-stu-id="d9304-220">Specifying rowpattern ending with an attribute</span></span>  
 <span data-ttu-id="d9304-221">O documento XML neste exemplo é composto dos elementos <`Customer`>, <`Order`>e <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="d9304-221">The XML document in this example is made up of the <`Customer`>, <`Order`>, and <`OrderDetail`> elements.</span></span> <span data-ttu-id="d9304-222">A instrução OPENXML recupera informações sobre os detalhes do pedido em um conjunto de linhas de três colunas (**ProductID**, **Quantity**e **OrderID**) do documento XML.</span><span class="sxs-lookup"><span data-stu-id="d9304-222">The OPENXML statement retrieves information about the order details in a three-column rowset (**ProductID**, **Quantity**, and **OrderID**) from the XML document.</span></span>  
  
 <span data-ttu-id="d9304-223">Primeiro, o **sp_xml_preparedocument** é chamado para obter um identificador de documento.</span><span class="sxs-lookup"><span data-stu-id="d9304-223">First, the **sp_xml_preparedocument** is called to obtain a document handle.</span></span> <span data-ttu-id="d9304-224">Esse identificador de documento é passado para o OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-224">This document handle is passed to OPENXML.</span></span>  
  
 <span data-ttu-id="d9304-225">A instrução OPENXML ilustra o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d9304-225">The OPENXML statement illustrates the following:</span></span>  
  
-   <span data-ttu-id="d9304-226">*rowpattern* (/ROOT/Customer/Order/OrderDetail/\@ProductID) termina com um atributo XML, **ProductID**.</span><span class="sxs-lookup"><span data-stu-id="d9304-226">*rowpattern* (/ROOT/Customer/Order/OrderDetail/\@ProductID) ends with an XML attribute, **ProductID**.</span></span> <span data-ttu-id="d9304-227">No conjunto de linhas resultante, uma linha é criada para cada nó de atributo selecionado no documento XML.</span><span class="sxs-lookup"><span data-stu-id="d9304-227">In the resulting rowset, a row is created for each attribute node selected in the XML document.</span></span>  
  
-   <span data-ttu-id="d9304-228">Neste exemplo, o parâmetro *flags* não é especificado.</span><span class="sxs-lookup"><span data-stu-id="d9304-228">In this example, the *flags* parameter is not specified.</span></span> <span data-ttu-id="d9304-229">Em vez disso, os mapeamentos são especificados pelo parâmetro *ColPattern* .</span><span class="sxs-lookup"><span data-stu-id="d9304-229">Instead, the mappings are specified by the *ColPattern* parameter.</span></span>  
  
 <span data-ttu-id="d9304-230">Em *SchemaDeclaration* na cláusula WITH, *ColPattern* também é especificado com os parâmetros *ColName* e *ColType* .</span><span class="sxs-lookup"><span data-stu-id="d9304-230">In *SchemaDeclaration* in the WITH clause, *ColPattern* is also specified with the *ColName* and *ColType* parameters.</span></span> <span data-ttu-id="d9304-231">O *ColPattern* opcional é o padrão XPath especificado para indicar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="d9304-231">The optional *ColPattern* is the XPath pattern specified to indicate the following:</span></span>  
  
-   <span data-ttu-id="d9304-232">O padrão XPath ( **.** ) especificado como *ColPattern* para a coluna **ProdID** no conjunto de linhas identifica o nó de contexto, o nó atual.</span><span class="sxs-lookup"><span data-stu-id="d9304-232">The XPath pattern (**.**) specified as *ColPattern* for the **ProdID** column in the rowset identifies the context node, current node.</span></span> <span data-ttu-id="d9304-233">De acordo com o *rowpattern* especificado, ele é o atributo **ProductID** do elemento <`OrderDetail`>.</span><span class="sxs-lookup"><span data-stu-id="d9304-233">As per the *rowpattern* specified, it is the **ProductID** attribute of the <`OrderDetail`> element.</span></span>  
  
-   <span data-ttu-id="d9304-234">O *ColPattern*, **../\@Quantity**, especificado para a coluna **Qty** no conjunto de linhas identifica o atributo **Quantity** do pai, <`OrderDetail`>, nó do nó de contexto, \<ProductID>.</span><span class="sxs-lookup"><span data-stu-id="d9304-234">The *ColPattern*, **../\@Quantity**, specified for the **Qty** column in the rowset identifies the **Quantity** attribute of the parent, <`OrderDetail`>, node of the context node, \<ProductID>.</span></span>  
  
-   <span data-ttu-id="d9304-235">De maneira semelhante, o *ColPattern*, **../../\@OrderID**, especificado para a coluna **OID** no conjunto de linhas identifica o atributo **OrderID** do pai, <`Order`>, do nó pai do nó de contexto.</span><span class="sxs-lookup"><span data-stu-id="d9304-235">Similarly, the *ColPattern*, **../../\@OrderID**, specified for the **OID** column in the rowset identifies the **OrderID** attribute of the parent, <`Order`>, of the parent node of the context node.</span></span> <span data-ttu-id="d9304-236">O nó pai é <`OrderDetail`>, e o nó de contexto é <`ProductID`>.</span><span class="sxs-lookup"><span data-stu-id="d9304-236">The parent node is <`OrderDetail`>, and the context node is <`ProductID`>.</span></span>  
  
 <span data-ttu-id="d9304-237">Em seguida, a instrução SELECT recupera todas as colunas no conjunto de linhas fornecido pelo OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-237">The SELECT statement then retrieves all the columns in the rowset provided by OPENXML.</span></span>  
  
```  
DECLARE @docHandle int  
DECLARE @xmlDocument nvarchar(1000)  
--Sample XML document  
SET @xmlDocument =N'<ROOT>  
<Customer CustomerID="VINET" ContactName="Paul Henriot">  
   <Order OrderID="10248" CustomerID="VINET" EmployeeID="5" OrderDate=  
           "1996-07-04T00:00:00">  
      <OrderDetail ProductID="11" Quantity="12"/>  
      <OrderDetail ProductID="42" Quantity="10"/>  
   </Order>  
</Customer>  
<Customer CustomerID="LILAS" ContactName="Carlos Gonzlez">  
   <Order OrderID="10283" CustomerID="LILAS" EmployeeID="3" OrderDate=  
           "1996-08-16T00:00:00">  
      <OrderDetail ProductID="72" Quantity="3"/>  
   </Order>  
</Customer>  
</ROOT>'  
-- Create an internal representation of the XML document.  
EXEC sp_xml_preparedocument @docHandle OUTPUT, @xmlDocument  
-- Execute a SELECT statement using OPENXML rowset provider.  
SELECT *  
FROM OPENXML (@docHandle, '/ROOT/Customer/Order/OrderDetail/@ProductID')  
       WITH ( ProdID  int '.',  
              Qty     int '../@Quantity',  
              OID     int '../../@OrderID')  
EXEC sp_xml_removedocument @docHandle  
```  
  
 <span data-ttu-id="d9304-238">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="d9304-238">This is the result:</span></span>  
  
```  
ProdID      Qty         OID  
----------- ----------- -------   
11          12          10248  
42          10          10248  
72          3           10283  
```  
  
### <a name="h-specifying-an-xml-document-that-has-multiple-text-nodes"></a><span data-ttu-id="d9304-239">H.</span><span class="sxs-lookup"><span data-stu-id="d9304-239">H.</span></span> <span data-ttu-id="d9304-240">Especificando um documento XML que tem vários nós de texto</span><span class="sxs-lookup"><span data-stu-id="d9304-240">Specifying an XML document that has multiple text nodes</span></span>  
 <span data-ttu-id="d9304-241">Se você tiver vários nós de texto em um documento XML, uma instrução SELECT com um *ColPattern*, **text()** , retornará apenas o primeiro nó de texto, em vez de todos eles.</span><span class="sxs-lookup"><span data-stu-id="d9304-241">If you have multiple text nodes in an XML document, a SELECT statement with a *ColPattern*, **text()**, returns only the first text node, instead of all of them.</span></span> <span data-ttu-id="d9304-242">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d9304-242">For example:</span></span>  
  
```  
DECLARE @h int  
EXEC sp_xml_preparedocument @h OUTPUT,  
         N'<root xmlns:a="urn:1">  
           <a:Elem abar="asdf">  
             T<a>a</a>U  
           </a:Elem>  
         </root>',  
         '<ns xmlns:b="urn:1" />'  
  
SELECT * FROM openxml(@h, '/root/b:Elem')  
      WITH (Col1 varchar(20) 'text()')  
EXEC sp_xml_removedocument @h  
```  
  
 <span data-ttu-id="d9304-243">A instrução SELECT retorna **T** como o resultado, e não **TaU**.</span><span class="sxs-lookup"><span data-stu-id="d9304-243">The SELECT statement returns **T** as the result, and not **TaU**.</span></span>  
  
### <a name="i-specifying-the-xml-data-type-in-the-with-clause"></a><span data-ttu-id="d9304-244">I.</span><span class="sxs-lookup"><span data-stu-id="d9304-244">I.</span></span> <span data-ttu-id="d9304-245">Especificando o tipo de dados xml na cláusula WITH</span><span class="sxs-lookup"><span data-stu-id="d9304-245">Specifying the xml data type in the WITH clause</span></span>  
 <span data-ttu-id="d9304-246">Na cláusula WITH, um padrão de coluna que é mapeado para a coluna de tipo de dados **xml** , com tipo ou sem-tipo, deve retornar uma sequência vazia ou uma sequência de elementos, instruções de processamento, nós de texto e comentários.</span><span class="sxs-lookup"><span data-stu-id="d9304-246">In the WITH clause, a column pattern that is mapped to the **xml** data type column, whether typed or untyped, must return either an empty sequence or a sequence of elements, processing instructions, text nodes, and comments.</span></span> <span data-ttu-id="d9304-247">Os dados são convertidos em um tipo de dados **xml** .</span><span class="sxs-lookup"><span data-stu-id="d9304-247">The data is cast to an **xml** data type.</span></span>  
  
 <span data-ttu-id="d9304-248">No exemplo a seguir, a declaração de esquema de tabela na cláusula WITH inclui colunas de tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="d9304-248">In the following example, the table schema declaration in the WITH clause includes **xml** type columns.</span></span>  
  
```  
DECLARE @h int  
DECLARE @x xml  
set @x = '<Root>  
  <row id="1"><lname>Duffy</lname>  
   <Address>  
            <Street>111 Maple</Street>  
            <City>Seattle</City>  
   </Address>  
  </row>  
  <row id="2"><lname>Wang</lname>  
   <Address>  
            <Street>222 Pine</Street>  
            <City>Bothell</City>  
   </Address>  
  </row>  
</Root>'  
  
EXEC sp_xml_preparedocument @h output, @x  
SELECT *  
FROM   OPENXML (@h, '/Root/row', 10)  
      WITH (id int '@id',  
  
            lname    varchar(30),  
            xmlname  xml 'lname',  
            OverFlow xml '@mp:xmltext')  
EXEC sp_xml_removedocument @h  
```  
  
 <span data-ttu-id="d9304-249">Especificamente, você está passando uma variável de tipo **xml** (\@x) para a função **sp_xml_preparedocument()** .</span><span class="sxs-lookup"><span data-stu-id="d9304-249">Specifically, you are passing an **xml** type variable (\@x) to the **sp_xml_preparedocument()** function.</span></span>  
  
 <span data-ttu-id="d9304-250">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="d9304-250">This is the result:</span></span>  
  
```  
id  lname   xmlname                   OverFlow  
--- ------- ------------------------------ -------------------------------  
1   Duffy   <lname>Duffy</lname>  <row><Address>  
                                   <Street>111 Maple</Street>  
                                   <City>Seattle</City>  
                                  </Address></row>  
2   Wang    <lname>Wang</lname>   <row><Address>  
                                    <Street>222 Pine</Street>  
                                    <City>Bothell</City>  
                                   </Address></row>  
```  
  
 <span data-ttu-id="d9304-251">Observe o seguinte no resultado:</span><span class="sxs-lookup"><span data-stu-id="d9304-251">Note the following from the result:</span></span>  
  
-   <span data-ttu-id="d9304-252">Para a coluna **lname** de tipo **varchar(30)** , o valor é recuperado do elemento <`lname`> correspondente.</span><span class="sxs-lookup"><span data-stu-id="d9304-252">For the **lname** column of **varchar(30)** type, its value is retrieved from the corresponding <`lname`> element.</span></span>  
  
-   <span data-ttu-id="d9304-253">Para a coluna **xmlname** de tipo **xml** , o mesmo elemento de nome é retornado como seu valor.</span><span class="sxs-lookup"><span data-stu-id="d9304-253">For the **xmlname** column of **xml** type, the same name element is returned as its value.</span></span>  
  
-   <span data-ttu-id="d9304-254">O sinalizador é definido como 10.</span><span class="sxs-lookup"><span data-stu-id="d9304-254">The flag is set to 10.</span></span> <span data-ttu-id="d9304-255">O 10 significa 2 + 8, em que 2 indica mapeamento centrado em elemento e 8 indica que apenas os dados XML não consumidos devem ser adicionados à coluna OverFlow definida na cláusula WITH.</span><span class="sxs-lookup"><span data-stu-id="d9304-255">The 10 means 2 + 8, where 2 indicates element-centric mapping and 8 indicates that only unconsumed XML data should be added to the OverFlow column defined in the WITH clause.</span></span> <span data-ttu-id="d9304-256">Se você definir o sinalizador como 2, todo o documento XML será copiado para a coluna OverFlow especificada na cláusula WITH.</span><span class="sxs-lookup"><span data-stu-id="d9304-256">If you set the flag to 2, the whole XML document is copied to the OverFlow column that is specified in the WITH clause.</span></span>  
  
-   <span data-ttu-id="d9304-257">Caso a coluna da cláusula WITH seja uma coluna XML com tipo e a instância XML não seja confirmada para o esquema, será retornado um erro.</span><span class="sxs-lookup"><span data-stu-id="d9304-257">In case the column in the WITH clause is a typed XML column and the XML instance does not confirm to the schema, an error is returned.</span></span>  
  
### <a name="j-retrieving-individual-values-from-multivalued-attributes"></a><span data-ttu-id="d9304-258">J.</span><span class="sxs-lookup"><span data-stu-id="d9304-258">J.</span></span> <span data-ttu-id="d9304-259">Recuperando valores individuais de atributos com vários valores</span><span class="sxs-lookup"><span data-stu-id="d9304-259">Retrieving individual values from multivalued attributes</span></span>  
 <span data-ttu-id="d9304-260">Um documento XML pode ter atributos com vários valores.</span><span class="sxs-lookup"><span data-stu-id="d9304-260">An XML document can have attributes that are multivalued.</span></span> <span data-ttu-id="d9304-261">Por exemplo, o atributo **IDREFS** pode ter vários valores.</span><span class="sxs-lookup"><span data-stu-id="d9304-261">For example, the **IDREFS** attribute can be multivalued.</span></span> <span data-ttu-id="d9304-262">Em um documento XML, valores de atributos com vários valores são especificados como uma cadeia de caracteres, com os valores separados por um espaço.</span><span class="sxs-lookup"><span data-stu-id="d9304-262">In an XML document, the multivalued attribute values are specified as a string, with the values separated by a space.</span></span> <span data-ttu-id="d9304-263">No documento XML a seguir, o atributo **attends** do elemento \<Student> e o atributo **attendedBy** de \<Class> têm vários valores.</span><span class="sxs-lookup"><span data-stu-id="d9304-263">In the following XML document, the **attends** attribute of the \<Student> element and the **attendedBy** attribute of \<Class> are multivalued.</span></span> <span data-ttu-id="d9304-264">A recuperação de valores individuais de um atributo XML de vários valores e o armazenamento de cada valor em uma linha separada no banco de dados requer trabalho adicional.</span><span class="sxs-lookup"><span data-stu-id="d9304-264">Retrieving individual values from a multivalued XML attribute and storing each value in a separate row in the database requires additional work.</span></span> <span data-ttu-id="d9304-265">Este exemplo mostra o processo.</span><span class="sxs-lookup"><span data-stu-id="d9304-265">This example shows the process.</span></span>  
  
 <span data-ttu-id="d9304-266">Este documento XML de exemplo é composto dos seguintes elementos:</span><span class="sxs-lookup"><span data-stu-id="d9304-266">This sample XML document is made up of the following elements:</span></span>  
  
-   \<Student>  
  
     <span data-ttu-id="d9304-267">Os atributos **id** (ID do estudante), **name**e **attends** .</span><span class="sxs-lookup"><span data-stu-id="d9304-267">The **id** (student ID), **name**, and **attends** attributes.</span></span> <span data-ttu-id="d9304-268">O atributo **attends** é um atributo com vários valores.</span><span class="sxs-lookup"><span data-stu-id="d9304-268">The **attends** attribute is a multivalued attribute.</span></span>  
  
-   \<Class>  
  
     <span data-ttu-id="d9304-269">Os atributos **id** (ID da aula), **name**e **attendedBy** .</span><span class="sxs-lookup"><span data-stu-id="d9304-269">The **id** (class ID), **name**, and **attendedBy** attributes.</span></span> <span data-ttu-id="d9304-270">O atributo **attendedBy** é um atributo com vários valores.</span><span class="sxs-lookup"><span data-stu-id="d9304-270">The **attendedBy** attribute is a multivalued attribute.</span></span>  
  
 <span data-ttu-id="d9304-271">O atributo **attends** em \<Student> e o atributo **attendedBy** em \<Class> representam uma relação **m:n** entre as tabelas Student e Class.</span><span class="sxs-lookup"><span data-stu-id="d9304-271">The **attends** attribute in \<Student> and the **attendedBy** attribute in \<Class> represent a **m:n** relationship between the Student and Class tables.</span></span> <span data-ttu-id="d9304-272">Um estudante pode assistir muitas aulas e uma aula pode ter muitos estudantes.</span><span class="sxs-lookup"><span data-stu-id="d9304-272">A student can take many classes and a class can have many students.</span></span>  
  
 <span data-ttu-id="d9304-273">Suponha que você queira fragmentar esse documento e salvá-lo no banco de dados, conforme mostrado a seguir:</span><span class="sxs-lookup"><span data-stu-id="d9304-273">Assume that you want to shred this document and save it in the database as shown in the following:</span></span>  
  
-   <span data-ttu-id="d9304-274">Salve os dados de \<Student> na tabela Students.</span><span class="sxs-lookup"><span data-stu-id="d9304-274">Save the \<Student> data in the Students table.</span></span>  
  
-   <span data-ttu-id="d9304-275">Salve os dados de \<Class> na tabela Courses.</span><span class="sxs-lookup"><span data-stu-id="d9304-275">Save the \<Class> data in the Courses table.</span></span>  
  
-   <span data-ttu-id="d9304-276">Salve os dados da relação **m:n** , entre Student e Class, na tabela CourseAttendence.</span><span class="sxs-lookup"><span data-stu-id="d9304-276">Save the **m:n** relationship data, between Student and Class, in the CourseAttendence table.</span></span> <span data-ttu-id="d9304-277">Trabalho adicional é necessário para extrair os valores.</span><span class="sxs-lookup"><span data-stu-id="d9304-277">Additional work is required to extract the values.</span></span> <span data-ttu-id="d9304-278">Para recuperar essas informações e armazená-las na tabela, use estes procedimentos armazenados:</span><span class="sxs-lookup"><span data-stu-id="d9304-278">To retrieve this information and store it in the table, use these stored procedures:</span></span>  
  
    -   <span data-ttu-id="d9304-279">**Insert_Idrefs_Values**</span><span class="sxs-lookup"><span data-stu-id="d9304-279">**Insert_Idrefs_Values**</span></span>  
  
         <span data-ttu-id="d9304-280">Insere os valores de ID do curso e ID do estudante na tabela CourseAttendence.</span><span class="sxs-lookup"><span data-stu-id="d9304-280">Inserts the values of course ID and student ID in the CourseAttendence table.</span></span>  
  
    -   <span data-ttu-id="d9304-281">**Extract_idrefs_values**</span><span class="sxs-lookup"><span data-stu-id="d9304-281">**Extract_idrefs_values**</span></span>  
  
         <span data-ttu-id="d9304-282">Extrai as IDs de estudantes individuais de cada elemento \<Course>.</span><span class="sxs-lookup"><span data-stu-id="d9304-282">Extracts the individual student IDs from each \<Course> element.</span></span> <span data-ttu-id="d9304-283">Uma tabela de borda é usada para recuperar esses valores.</span><span class="sxs-lookup"><span data-stu-id="d9304-283">An edge table is used to retrieve these values.</span></span>  
  
 <span data-ttu-id="d9304-284">Siga estas etapas:</span><span class="sxs-lookup"><span data-stu-id="d9304-284">Here are the steps:</span></span>  
  
```  
-- Create these tables:  
DROP TABLE CourseAttendance  
DROP TABLE Students  
DROP TABLE Courses  
GO  
CREATE TABLE Students(  
                id   varchar(5) primary key,  
                name varchar(30)  
                )  
GO  
CREATE TABLE Courses(  
               id       varchar(5) primary key,  
               name     varchar(30),  
               taughtBy varchar(5)  
)  
GO  
CREATE TABLE CourseAttendance(  
             id         varchar(5) references Courses(id),  
             attendedBy varchar(5) references Students(id),  
             constraint CourseAttendance_PK primary key (id, attendedBy)  
)  
go  
-- Create these stored procedures:  
DROP PROCEDURE f_idrefs  
GO  
CREATE PROCEDURE f_idrefs  
    @t      varchar(500),  
    @idtab  varchar(50),  
    @id     varchar(5)  
AS  
DECLARE @sp int  
DECLARE @att varchar(5)  
SET @sp = 0  
WHILE (LEN(@t) > 0)  
BEGIN   
    SET @sp = CHARINDEX(' ', @t+ ' ')  
    SET @att = LEFT(@t, @sp-1)  
    EXEC('INSERT INTO '+@idtab+' VALUES ('''+@id+''', '''+@att+''')')  
    SET @t = SUBSTRING(@t+ ' ', @sp+1, LEN(@t)+1-@sp)  
END  
Go  
  
DROP PROCEDURE fill_idrefs  
GO  
CREATE PROCEDURE fill_idrefs   
    @xmldoc     int,  
    @xpath      varchar(100),  
    @from       varchar(50),  
    @to         varchar(50),  
    @idtable    varchar(100)  
AS  
DECLARE @t varchar(500)  
DECLARE @id varchar(5)  
  
/* Temporary edge table */  
SELECT *   
INTO #TempEdge   
FROM OPENXML(@xmldoc, @xpath)  
  
DECLARE fillidrefs_cursor CURSOR FOR  
    SELECT CAST(iv.text AS nvarchar(200)) AS id,  
           CAST(av.text AS nvarchar(4000)) AS refs  
    FROM   #TempEdge c, #TempEdge i,  
           #TempEdge iv, #TempEdge a, #TempEdge av  
    WHERE  c.id = i.parentid  
    AND    UPPER(i.localname) = UPPER(@from)  
    AND    i.id = iv.parentid  
    AND    c.id = a.parentid  
    AND    UPPER(a.localname) = UPPER(@to)  
    AND    a.id = av.parentid  
  
OPEN fillidrefs_cursor  
FETCH NEXT FROM fillidrefs_cursor INTO @id, @t  
WHILE (@@FETCH_STATUS <> -1)  
BEGIN  
    IF (@@FETCH_STATUS <> -2)  
    BEGIN  
        execute f_idrefs @t, @idtable, @id  
    END  
    FETCH NEXT FROM fillidrefs_cursor INTO @id, @t  
END  
CLOSE fillidrefs_cursor  
DEALLOCATE fillidrefs_cursor  
Go  
-- This is the sample document that is shredded and the data is stored in the preceding tables.  
DECLARE @h int  
EXECUTE sp_xml_preparedocument @h OUTPUT, N'<Data>  
  <Student id = "s1" name = "Student1"  attends = "c1 c3 c6"  />  
  <Student id = "s2" name = "Student2"  attends = "c2 c4" />  
  <Student id = "s3" name = "Student3"  attends = "c2 c4 c6" />  
  <Student id = "s4" name = "Student4"  attends = "c1 c3 c5" />  
  <Student id = "s5" name = "Student5"  attends = "c1 c3 c5 c6" />  
  <Student id = "s6" name = "Student6" />  
  
  <Class id = "c1" name = "Intro to Programming"   
         attendedBy = "s1 s4 s5" />  
  <Class id = "c2" name = "Databases"   
         attendedBy = "s2 s3" />  
  <Class id = "c3" name = "Operating Systems"   
         attendedBy = "s1 s4 s5" />  
  <Class id = "c4" name = "Networks" attendedBy = "s2 s3" />  
  <Class id = "c5" name = "Algorithms and Graphs"   
         attendedBy =  "s4 s5"/>  
  <Class id = "c6" name = "Power and Pragmatism"   
         attendedBy = "s1 s3 s5" />  
</Data>'  
  
INSERT INTO Students SELECT * FROM OPENXML(@h, '//Student') WITH Students  
  
INSERT INTO Courses SELECT * FROM OPENXML(@h, '//Class') WITH Courses  
/* Using the edge table */  
EXECUTE fill_idrefs @h, '//Class', 'id', 'attendedby', 'CourseAttendance'  
  
SELECT * FROM Students  
SELECT * FROM Courses  
SELECT * FROM CourseAttendance  
  
EXECUTE sp_xml_removedocument @h  
```  
  
### <a name="k-retrieving-binary-from-base64-encoded-data-in-xml"></a><span data-ttu-id="d9304-285">K.</span><span class="sxs-lookup"><span data-stu-id="d9304-285">K.</span></span> <span data-ttu-id="d9304-286">Recuperando binários de dados codificados na base64 no XML</span><span class="sxs-lookup"><span data-stu-id="d9304-286">Retrieving binary from base64 encoded data in XML</span></span>  
 <span data-ttu-id="d9304-287">Dados Binários são frequentemente incluídos no XML usando codificação na base64.</span><span class="sxs-lookup"><span data-stu-id="d9304-287">Binary data is frequently included in XML using base64 encoding.</span></span> <span data-ttu-id="d9304-288">Quando você fragmenta esse XML usando OPENXML, você recebe os dados codificados na base64.</span><span class="sxs-lookup"><span data-stu-id="d9304-288">When you shred this XML by using OPENXML, you receive the base64 encoded data.</span></span> <span data-ttu-id="d9304-289">Este exemplo mostra como é possível converter o dados codificados na base64 novamente em binários.</span><span class="sxs-lookup"><span data-stu-id="d9304-289">This example shows how you can convert the base64 encoded data back to binary.</span></span>  
  
-   <span data-ttu-id="d9304-290">Crie uma tabela com dados binários de exemplo.</span><span class="sxs-lookup"><span data-stu-id="d9304-290">Create a table with sample binary data.</span></span>  
  
-   <span data-ttu-id="d9304-291">Use uma consulta FOR XML e a opção BINARY BASE64 para construir XML que tenha dados binários codificados como base64.</span><span class="sxs-lookup"><span data-stu-id="d9304-291">Use a FOR XML query and the BINARY BASE64 option to construct XML that has the binary data encoded as base64.</span></span>  
  
-   <span data-ttu-id="d9304-292">Fragmente o XML usando OPENXML.</span><span class="sxs-lookup"><span data-stu-id="d9304-292">Shred the XML by using OPENXML.</span></span> <span data-ttu-id="d9304-293">Os dados retornados por OPENXML serão codificados na base64.</span><span class="sxs-lookup"><span data-stu-id="d9304-293">The data returned by OPENXML will be base64 encoded data.</span></span> <span data-ttu-id="d9304-294">Em seguida, chame a função .value para convertê-los novamente em binários.</span><span class="sxs-lookup"><span data-stu-id="d9304-294">Next, call the .value function to convert it back to binary.</span></span>  
  
```  
CREATE TABLE T (Col1 int primary key, Col2 varbinary(100))  
go  
-- Insert sample binary data  
INSERT T VALUES(1, 0x1234567890)   
go  
 -- Create test XML document that has base64 encoded binary data (use FOR XML query and specify BINARY BASE64 option)  
SELECT * FROM T  
FOR XML AUTO, BINARY BASE64  
go  
-- result  
-- <T Col1="1" Col2="EjRWeJA="/>  
  
-- Now shredd the sample XML using OPENXML.   
-- Call the .value function to convert   
-- the base64 encoded data returned by OPENXML to binary.  
DECLARE @h int ;  
EXEC sp_xml_preparedocument @h OUTPUT, '<T Col1="1" Col2="EjRWeJA="/>' ;  
SELECT Col1,   
CAST('<binary>' + Col2 + '</binary>' AS XML).value('.', 'varbinary(max)') AS BinaryCol   
FROM openxml(@h, '/T')   
WITH (Col1 integer, Col2 varchar(max)) ;  
EXEC sp_xml_removedocument @h ;  
GO  
```  
  
 Este é o resultado. <span data-ttu-id="d9304-296">Os dados binários retornados são os dados binários originais na tabela T.</span><span class="sxs-lookup"><span data-stu-id="d9304-296">The binary data returned is the original binary data in table T.</span></span>  
  
```  
Col1        BinaryCol  
----------- ---------------------  
1           0x1234567890  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9304-297">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d9304-297">See Also</span></span>  
 <span data-ttu-id="d9304-298">[sp_xml_preparedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d9304-298">[sp_xml_preparedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-preparedocument-transact-sql) </span></span>  
 <span data-ttu-id="d9304-299">[sp_xml_removedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d9304-299">[sp_xml_removedocument &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-xml-removedocument-transact-sql) </span></span>  
 <span data-ttu-id="d9304-300">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d9304-300">[OPENXML &#40;Transact-SQL&#41;](/sql/t-sql/functions/openxml-transact-sql) </span></span>  
 [<span data-ttu-id="d9304-301">OPENXML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d9304-301">OPENXML &#40;SQL Server&#41;</span></span>](openxml-sql-server.md)  
  
  
