---
title: Especificando predicados com valor booliano em consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], predicates
- nested predicates
- successive predicates
- predicates [SQLXML]
- top-level predicates
- Boolean-valued predicates
- multiple predicates
ms.assetid: 5f6e7219-6911-4bca-a54b-56b95e0b43dd
author: rothja
ms.author: jroth
ms.openlocfilehash: 56f2f94ec895c5b76382d5103ca9d518b78cc899
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569289"
---
# <a name="specifying-boolean-valued-predicates-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="2a4fc-102">Especificando predicados com valor booliano em consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="2a4fc-102">Specifying Boolean-Valued Predicates in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="2a4fc-103">Os exemplos a seguir mostram como os predicados com valor booliano são especificados em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-103">The following examples show how Boolean-valued predicates are specified in XPath queries.</span></span> <span data-ttu-id="2a4fc-104">As consultas XPath nesses exemplos são especificadas com relação ao esquema de mapeamento contido em SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="2a4fc-105">Para obter informações sobre este esquema de exemplo, consulte [exemplo de esquema XSD anotado para exemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="2a4fc-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="2a4fc-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="2a4fc-106">Examples</span></span>  
  
### <a name="a-specify-multiple-predicates"></a><span data-ttu-id="2a4fc-107">a.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-107">A.</span></span> <span data-ttu-id="2a4fc-108">Especificar vários predicados</span><span class="sxs-lookup"><span data-stu-id="2a4fc-108">Specify multiple predicates</span></span>  
 <span data-ttu-id="2a4fc-109">A consulta XPath a seguir usa vários predicados para localizar informações de ordem de uma determinada ID de ordem e uma ID de cliente:</span><span class="sxs-lookup"><span data-stu-id="2a4fc-109">The following XPath query uses multiple predicates to find order information for a given order ID and a customer ID:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="1"]/child::Order[attribute::OrderID="Ord-43860"]  
```  
  
 <span data-ttu-id="2a4fc-110">Um atalho para o `attribute` eixo (@) pode ser especificado e, como o `child` eixo é o padrão, ele pode ser omitido da consulta:</span><span class="sxs-lookup"><span data-stu-id="2a4fc-110">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order[@SalesOrderID="Ord-43860"]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="2a4fc-111">Para testar a consulta XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="2a4fc-111">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="2a4fc-112">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-112">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="2a4fc-113">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-113">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="2a4fc-114">Crie o modelo a seguir (BooleanValuedPredicatesA.xml) e o salve no diretório em que SampleSchema1.xml foi salvo.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-114">Create the following template (BooleanValuedPredicatesA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="1"]/Order[@SalesOrderID="Ord-43860"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="2a4fc-115">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-115">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="2a4fc-116">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2a4fc-116">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="2a4fc-117">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-117">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="2a4fc-118">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="2a4fc-118">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
     <span data-ttu-id="2a4fc-119">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="2a4fc-119">Here is the result:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <Order SalesOrderID="Ord-43860" SalesPersonID="280" OrderDate="2001-08-01T00:00:00" DueDate="2001-08-13T00:00:00" ShipDate="2001-08-08T00:00:00">  
        <OrderDetail ProductID="Prod-729" UnitPrice="226.8571" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-738" UnitPrice="220.2496" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-761" UnitPrice="503.3507" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-762" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-763" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-765" UnitPrice="503.3507" OrderQty="2" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-768" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
        <OrderDetail ProductID="Prod-770" UnitPrice="503.3507" OrderQty="1" UnitPriceDiscount="0" />   
      </Order>  
    </ROOT>  
    ```  
  
### <a name="b-specify-successive-and-nested-predicates"></a><span data-ttu-id="2a4fc-120">B.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-120">B.</span></span> <span data-ttu-id="2a4fc-121">Especificar predicados sucessivos e aninhados</span><span class="sxs-lookup"><span data-stu-id="2a4fc-121">Specify successive and nested predicates</span></span>  
 <span data-ttu-id="2a4fc-122">A consulta a seguir mostra o uso de predicados sucessivos.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-122">The following query shows using successive predicates.</span></span> <span data-ttu-id="2a4fc-123">A consulta retorna todos os **\<Customer>** elementos filho do nó de contexto que têm um atributo **vendedorid** com um valor de 277 e um atributo de **territórioid** com um valor de 3:</span><span class="sxs-lookup"><span data-stu-id="2a4fc-123">The query returns all the **\<Customer>** child elements of the context node that have both a **SalesPersonID** attribute with a value of 277 and a **TerritoryID** attribute with a value of 3:</span></span>  
  
```  
/child::Customer[attribute::SalesPersonID="277"][attribute::TerritoryID="3"]  
```  
  
 <span data-ttu-id="2a4fc-124">A consulta retorna os **\<Customer>** elementos que atendem às duas condições especificadas nos predicados.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-124">The query returns the **\<Customer>** elements that satisfy both the conditions specified in the predicates.</span></span>  
  
 <span data-ttu-id="2a4fc-125">Um atalho para o `attribute` eixo (@) pode ser especificado e, como o `child` eixo é o padrão, ele pode ser omitido da consulta:</span><span class="sxs-lookup"><span data-stu-id="2a4fc-125">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted from the query:</span></span>  
  
```  
/Customer[@SalesPersonID="277"][@TerritoryID="3"]  
```  
  
 <span data-ttu-id="2a4fc-126">A consulta XPath a seguir ilustra o uso de predicados aninhados.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-126">The following XPath query illustrates the use of nested predicates.</span></span> <span data-ttu-id="2a4fc-127">A consulta retorna todos os **\<Customer>** elementos filho do nó de contexto que incluem **\<Order>** elementos filho com pelo menos um **\<Order>** elemento com um valor de atributo **vendedorid** de 2.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-127">The query returns all the **\<Customer>** child elements of the context node that include **\<Order>** child elements with at least one **\<Order>** element that has a **SalesPersonID** attribute value of 2.</span></span>  
  
```  
/Customer[Order[@SalesPersonID=2]]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="2a4fc-128">Para testar a consulta XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="2a4fc-128">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="2a4fc-129">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-129">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="2a4fc-130">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-130">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="2a4fc-131">Crie o modelo a seguir (nestedSuccessive.xml) e o salve no diretório em que SampleSchema1.xml foi salvo.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-131">Create the following template (nestedSuccessive.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
             /Customer[@SalesPersonID="277"][@TerritoryID="3"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="2a4fc-132">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-132">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="2a4fc-133">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2a4fc-133">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="2a4fc-134">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-134">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="2a4fc-135">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="2a4fc-135">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="2a4fc-136">O seguinte é um resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="2a4fc-136">The following is a partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="22" SalesPersonID="277" TerritoryID="3"   
            AccountNumber="22" CustomerType="S"   
            Orders="Ord-43874 Ord-44519 Ord-46989 Ord-48013 Ord-49130 Ord-50274 Ord-51807 Ord-57113 Ord-63162 Ord-69495">  
    <Order SalesOrderID="Ord-43874" SalesPersonID="277"   
           OrderDate="2001-08-01T00:00:00"   
           DueDate="2001-08-13T00:00:00"   
           ShipDate="2001-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
                   OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
    ...  
  </Customer>  
  <Customer CustomerID="39" SalesPersonID="277" TerritoryID="3"   
            AccountNumber="39" CustomerType="S"   
            Orders="Ord-47428 Ord-48367 Ord-49529 Ord-50742 Ord-53591 Ord-59051 Ord-65301 Ord-71912">    <Order SalesOrderID="Ord-47428" SalesPersonID="277"   
           OrderDate="2002-09-01T00:00:00"   
           DueDate="2002-09-13T00:00:00"   
           ShipDate="2002-09-08T00:00:00">  
      <OrderDetail ProductID="Prod-759" UnitPrice="563.7528" OrderQty="2" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-769" UnitPrice="563.7528" OrderQty="1" UnitPriceDiscount="0" />   
      ...  
    </Order>  
    ...  
  </Customer>  
  ...  
</ROOT>  
```  
  
### <a name="c-specify-a-top-level-predicate"></a><span data-ttu-id="2a4fc-137">C.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-137">C.</span></span> <span data-ttu-id="2a4fc-138">Especificar um predicado de nível superior</span><span class="sxs-lookup"><span data-stu-id="2a4fc-138">Specify a top-level predicate</span></span>  
 <span data-ttu-id="2a4fc-139">A consulta a seguir retorna os **\<Customer>** nós de elemento filho do nó de contexto que têm **\<Order>** elementos filhos.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-139">The following query returns the **\<Customer>** child element nodes of the context node that have **\<Order>** element children.</span></span> <span data-ttu-id="2a4fc-140">A consulta testa o caminho de local como o predicado de nível superior:</span><span class="sxs-lookup"><span data-stu-id="2a4fc-140">The query tests the location path as the top-level predicate:</span></span>  
  
```  
/child::Customer[child::Order]  
```  
  
 <span data-ttu-id="2a4fc-141">O eixo `child` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-141">The `child` axis is the default.</span></span> <span data-ttu-id="2a4fc-142">Assim, a consulta pode ser especificada como:</span><span class="sxs-lookup"><span data-stu-id="2a4fc-142">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[Order]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="2a4fc-143">Para testar a consulta XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="2a4fc-143">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="2a4fc-144">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-144">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="2a4fc-145">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-145">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="2a4fc-146">Crie o modelo a seguir (TopLevelPredicate.xml) e o salve no diretório em que SampleSchema1.xml foi salvo.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-146">Create the following template (TopLevelPredicate.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[Order]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="2a4fc-147">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-147">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="2a4fc-148">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="2a4fc-148">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="2a4fc-149">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="2a4fc-149">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="2a4fc-150">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="2a4fc-150">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="2a4fc-151">Este é o resultado parcial:</span><span class="sxs-lookup"><span data-stu-id="2a4fc-151">Here is the partial result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" SalesPersonID="280" TerritoryID="1" AccountNumber="1" CustomerType="S" Orders="Ord-43860 Ord-44501 Ord-45283 Ord-46042">  
    <Order SalesOrderID="Ord-43860" SalesPersonID="280" OrderDate="2001-08-01T00:00:00" DueDate="2001-08-13T00:00:00" ShipDate="2001-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-729" UnitPrice="226.8571" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-732" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-738" UnitPrice="220.2496" OrderQty="1" UnitPriceDiscount="0" />   
      ...  
    </Order>  
    <Order SalesOrderID="Ord-44501" SalesPersonID="280" OrderDate="2001-11-01T00:00:00" DueDate="2001-11-13T00:00:00" ShipDate="2001-11-08T00:00:00">  
      <OrderDetail ProductID="Prod-725" UnitPrice="226.8571" OrderQty="3" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-726" UnitPrice="226.8571" OrderQty="2" UnitPriceDiscount="0" />   
      ...  
    </Order>    ...  
  </Customer>  
  ...  
</ROOT>  
```  
  
  
