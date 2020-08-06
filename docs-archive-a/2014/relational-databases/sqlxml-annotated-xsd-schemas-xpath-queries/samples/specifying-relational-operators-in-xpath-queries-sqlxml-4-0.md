---
title: Especificando operadores relacionais em consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], relational operators
- relational operators [SQLXML]
- XPath operators [SQLXML]
- operators [SQLXML]
ms.assetid: 177a0eb2-11ef-4459-a317-485a433ee769
author: rothja
ms.author: jroth
ms.openlocfilehash: 50d59ebd3a776386c61f4c3a8a1e892d30981d1b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569282"
---
# <a name="specifying-relational-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="e2dd2-102">Especificando operadores relacionais em consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e2dd2-102">Specifying Relational Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="e2dd2-103">Os seguintes exemplos mostram como operadores relacionais são especificados em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-103">The following examples show how relational operators are specified in XPath queries.</span></span> <span data-ttu-id="e2dd2-104">As consultas XPath nesses exemplos são especificadas com relação ao esquema de mapeamento contido em SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="e2dd2-105">Para obter informações sobre este esquema de exemplo, consulte [exemplo de esquema XSD anotado para exemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e2dd2-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e2dd2-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e2dd2-106">Examples</span></span>  
  
### <a name="a-specify-relational-operator"></a><span data-ttu-id="e2dd2-107">a.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-107">A.</span></span> <span data-ttu-id="e2dd2-108">Especifique operador relacional</span><span class="sxs-lookup"><span data-stu-id="e2dd2-108">Specify relational operator</span></span>  
 <span data-ttu-id="e2dd2-109">Essa consulta XPath retorna os elementos filho do **\<Customer>** elemento em que o valor do atributo **CustomerID** é "1" e onde os **\<Order>** elementos filho contêm um **\<OrderDetail>** filho com um atributo **OrderQty** com um valor maior que 3:</span><span class="sxs-lookup"><span data-stu-id="e2dd2-109">This XPath query returns the child elements of the **\<Customer>** element where the **CustomerID** attribute value is "1" and where any child **\<Order>** elements contain an **\<OrderDetail>** child with a **OrderQty** attribute with a value greater than 3:</span></span>  
  
```  
/child::Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
```  
  
 <span data-ttu-id="e2dd2-110">O predicado especificado nos colchetes filtra os **\<Customer>** elementos.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-110">The predicate specified in the brackets filters the **\<Customer>** elements.</span></span> <span data-ttu-id="e2dd2-111">Somente os **\<Customer>** elementos que têm pelo menos um **\<OrderDetail>** neto com um valor de atributo OrderQty maior que 3 são retornados.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-111">Only the **\<Customer>** elements that have at least one **\<OrderDetail>** grandchild with a OrderQty attribute value greater than 3 are returned.</span></span>  
  
 <span data-ttu-id="e2dd2-112">O eixo `child` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-112">The `child` axis is the default.</span></span> <span data-ttu-id="e2dd2-113">Assim, a consulta pode ser especificada como:</span><span class="sxs-lookup"><span data-stu-id="e2dd2-113">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="e2dd2-114">Para testar a consulta XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="e2dd2-114">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="e2dd2-115">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-115">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="e2dd2-116">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-116">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="e2dd2-117">Crie o modelo a seguir (SpecifyRelationalA.xml) e salve-o no diretório em que SampleSchema1.xml foi salvo.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-117">Create the following template (SpecifyRelationalA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="1"]/Order/OrderDetail[@OrderQty > 3]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e2dd2-118">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-118">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e2dd2-119">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e2dd2-119">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="e2dd2-120">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-120">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e2dd2-121">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e2dd2-121">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e2dd2-122">Aqui está o conjunto de resultados da execução do modelo:</span><span class="sxs-lookup"><span data-stu-id="e2dd2-122">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <OrderDetail ProductID="Prod-760" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-766" UnitPrice="503.3507" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="4" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-757" UnitPrice="1049.7528" OrderQty="4" UnitPriceDiscount="0" />   
</ROOT>  
```  
  
### <a name="b-specify-relational-operator-in-the-xpath-query-and-use-boolean-function-to-compare-the-result"></a><span data-ttu-id="e2dd2-123">B.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-123">B.</span></span> <span data-ttu-id="e2dd2-124">Especifique o operador relacional na consulta XPath e use a função Booliano para comparar o resultado</span><span class="sxs-lookup"><span data-stu-id="e2dd2-124">Specify relational operator in the XPath query and use Boolean function to compare the result</span></span>  
 <span data-ttu-id="e2dd2-125">Essa consulta retorna todos os **\<Order>** elementos filho do nó de contexto que têm um valor de atributo **vendedorid** menor que 270:</span><span class="sxs-lookup"><span data-stu-id="e2dd2-125">This query returns all the **\<Order>** element children of the context node that have an **SalesPersonID** attribute value that is less than 270:</span></span>  
  
```  
/child::Customer/child::Order[(attribute::SalesPersonID < 270)=true()]  
```  
  
 <span data-ttu-id="e2dd2-126">Um atalho para o `attribute` eixo (@) pode ser especificado e, como o `child` eixo é o padrão, ele pode ser omitido da consulta:</span><span class="sxs-lookup"><span data-stu-id="e2dd2-126">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer/Order[(@SalesPersonID < 270)=true()]  
```  
  
> [!NOTE]  
>  <span data-ttu-id="e2dd2-127">Quando essa consulta é especificada em um modelo, o caractere de < deve ser codificado de entidade porque o caractere de < tem um significado especial em um documento XML.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-127">When this query is specified in a template, the < character must be entity encoded because the < character has special meaning in an XML document.</span></span> <span data-ttu-id="e2dd2-128">Em um modelo, use `<` para especificar o caractere de <.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-128">In a template, use `<` to specify the < character.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="e2dd2-129">Para testar a consulta XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="e2dd2-129">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="e2dd2-130">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-130">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="e2dd2-131">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-131">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="e2dd2-132">Crie o modelo a seguir (SpecifyRelationalB.xml) e salve-o no diretório em que SampleSchema1.xml foi salvo.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-132">Create the following template (SpecifyRelationalB.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="SampleSchema1.xml">  
            /Customer/Order[(@SalesPersonID<270)=true()]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e2dd2-133">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-133">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e2dd2-134">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e2dd2-134">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="e2dd2-135">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e2dd2-135">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e2dd2-136">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e2dd2-136">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e2dd2-137">Aqui está o conjunto de resultados parcial da execução do modelo:</span><span class="sxs-lookup"><span data-stu-id="e2dd2-137">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-46613" SalesPersonID="268"   
         OrderDate="2002-07-01T00:00:00"   
         DueDate="2002-07-13T00:00:00"   
         ShipDate="2002-07-08T00:00:00">  
    <OrderDetail ProductID="Prod-739" UnitPrice="917.9363"   
                 OrderQty="2" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-779" UnitPrice="1491.4221"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-825" UnitPrice="242.1391"   
                 OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
  <Order SalesOrderID="Ord-71919" SalesPersonID="268"  
         OrderDate="2004-06-01T00:00:00"   
         DueDate="2004-06-13T00:00:00"   
         ShipDate="2004-06-08T00:00:00">  
    <OrderDetail ProductID="Prod-961" UnitPrice="534.492"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-965" UnitPrice="534.492"   
                 OrderQty="1" UnitPriceDiscount="0" />   
    <OrderDetail ProductID="Prod-966" UnitPrice="1716.5304"   
                 OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
  ...  
</ROOT>  
```  
  
  