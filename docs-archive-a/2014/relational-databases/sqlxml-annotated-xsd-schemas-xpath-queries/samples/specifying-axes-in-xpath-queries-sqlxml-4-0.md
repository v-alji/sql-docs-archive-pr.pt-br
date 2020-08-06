---
title: Especificando eixos em consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], axes
- context node [SQLXML]
- attribute axis [SQLXML]
- axis [SQLXML]
- child axis
- parent axis
- axes [SQLXML]
ms.assetid: d17b8278-da58-4576-95b4-7a92772566d8
author: rothja
ms.author: jroth
ms.openlocfilehash: f6f17404ea109bb0e687f9116b61025bbc411008
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569293"
---
# <a name="specifying-axes-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="e6060-102">Especificando eixos em consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e6060-102">Specifying Axes in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="e6060-103">Os seguintes exemplos mostram como os eixos são especificados em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="e6060-103">The following examples show how axes are specified in XPath queries.</span></span>  
  
 <span data-ttu-id="e6060-104">As consultas XPath nesses exemplos são especificadas com relação ao esquema de mapeamento contido em SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="e6060-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="e6060-105">Para obter informações sobre este esquema de exemplo, consulte [exemplo de esquema XSD anotado para exemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e6060-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e6060-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e6060-106">Examples</span></span>  
  
### <a name="a-retrieve-child-elements-of-the-context-node"></a><span data-ttu-id="e6060-107">a.</span><span class="sxs-lookup"><span data-stu-id="e6060-107">A.</span></span> <span data-ttu-id="e6060-108">Recuperar elementos filho do nó de contexto</span><span class="sxs-lookup"><span data-stu-id="e6060-108">Retrieve child elements of the context node</span></span>  
 <span data-ttu-id="e6060-109">A consulta XPath a seguir seleciona todos os **\<Contact>** elementos filho do nó de contexto:</span><span class="sxs-lookup"><span data-stu-id="e6060-109">The following XPath query selects all the **\<Contact>** child elements of the context node:</span></span>  
  
```  
/child::Contact  
```  
  
 <span data-ttu-id="e6060-110">Na consulta, `child` é o eixo e `Contact` é o teste de nó (verdadeiro se `Contact` for um **\<element>** nó, porque \<element> é o tipo de nó primário associado ao `child` eixo).</span><span class="sxs-lookup"><span data-stu-id="e6060-110">In the query, `child` is the axis and `Contact` is the node test (TRUE if `Contact` is an **\<element>** node, because \<element> is the primary node type associated with the `child` axis).</span></span>  
  
 <span data-ttu-id="e6060-111">O eixo `child` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="e6060-111">The `child` axis is the default.</span></span> <span data-ttu-id="e6060-112">Portanto, a consulta pode ser escrita da seguinte forma:</span><span class="sxs-lookup"><span data-stu-id="e6060-112">Therefore, the query can be written as:</span></span>  
  
```  
/Contact  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="e6060-113">Para testar a consulta XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="e6060-113">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="e6060-114">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e6060-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="e6060-115">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="e6060-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="e6060-116">Crie o seguinte modelo (XPathAxesSampleA.xml) e salve-o no diretório onde SampleSchema1.xml foi salvo.</span><span class="sxs-lookup"><span data-stu-id="e6060-116">Create the following template (XPathAxesSampleA.xml) and save it in the directory where SampleSchema1.xml was saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Contact  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e6060-117">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="e6060-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e6060-118">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e6060-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="e6060-119">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e6060-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e6060-120">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e6060-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e6060-121">Aqui está o conjunto de resultados parcial da execução do modelo:</span><span class="sxs-lookup"><span data-stu-id="e6060-121">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Contact ContactID="1" LastName="Achong" FirstName="Gustavo" Title="Mr." />   
  <Contact ContactID="2" LastName="Abel" FirstName="Catherine" Title="Ms." />   
  <Contact ContactID="3" LastName="Abercrombie" FirstName="Kim" Title="Ms." />   
  <Contact ContactID="4" LastName="Acevedo" FirstName="Humberto" Title="Sr." />  
  ...  
</ROOT>  
```  
  
### <a name="b-retrieve-grandchildren-of-the-context-node"></a><span data-ttu-id="e6060-122">B.</span><span class="sxs-lookup"><span data-stu-id="e6060-122">B.</span></span> <span data-ttu-id="e6060-123">Recuperar os netos do nó de contexto</span><span class="sxs-lookup"><span data-stu-id="e6060-123">Retrieve grandchildren of the context node</span></span>  
 <span data-ttu-id="e6060-124">A consulta XPath a seguir seleciona todos os **\<Order>** elementos filho do **\<Customer>** elemento filho do nó de contexto:</span><span class="sxs-lookup"><span data-stu-id="e6060-124">The following XPath query selects all the **\<Order>** element children of the **\<Customer>** element children of the context node:</span></span>  
  
```  
/child::Customer/child::Order  
```  
  
 <span data-ttu-id="e6060-125">Na consulta, `child` é o eixo e `Customer` e `Order` são os testes de nó (esses testes de nó serão verdadeiros se o cliente e a ordem forem **\<element>** nós, porque o **\<element>** nó é o nó primário para o `child` eixo).</span><span class="sxs-lookup"><span data-stu-id="e6060-125">In the query, `child` is the axis and `Customer` and `Order` are the node tests (these node tests are TRUE if Customer and Order are **\<element>** nodes, because the **\<element>** node is the primary node for the `child` axis).</span></span> <span data-ttu-id="e6060-126">Para cada nó correspondente **\<Customer>** , os nós correspondentes **\<Orders>** são adicionados ao resultado.</span><span class="sxs-lookup"><span data-stu-id="e6060-126">For each node matching **\<Customer>**, the nodes matching **\<Orders>** are added to the result.</span></span> <span data-ttu-id="e6060-127">Somente **\<Order>** é retornado no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="e6060-127">Only **\<Order>** is returned in the result set.</span></span>  
  
 <span data-ttu-id="e6060-128">O eixo `child` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="e6060-128">The `child` axis is the default.</span></span> <span data-ttu-id="e6060-129">Assim, a consulta pode ser especificada como:</span><span class="sxs-lookup"><span data-stu-id="e6060-129">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer/Order  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="e6060-130">Para testar a consulta XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="e6060-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="e6060-131">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e6060-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="e6060-132">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="e6060-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="e6060-133">Crie o seguinte modelo (XPathAxesSampleB.xml) e salve-o no diretório onde:</span><span class="sxs-lookup"><span data-stu-id="e6060-133">Create the following template (XPathAxesSampleB.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer/Order  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e6060-134">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="e6060-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e6060-135">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e6060-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="e6060-136">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e6060-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e6060-137">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e6060-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e6060-138">Aqui está o conjunto de resultados parcial da execução do modelo:</span><span class="sxs-lookup"><span data-stu-id="e6060-138">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
         OrderDate="2001-08-01T00:00:00"   
         DueDate="2001-08-13T00:00:00"   
         ShipDate="2001-08-08T00:00:00">  
  <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-761" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-762" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-765" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-768" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-770" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
   ...  
</ROOT>  
```  
  
 <span data-ttu-id="e6060-139">Se a consulta XPath for especificada como `Customer/Order/OrderDetail` , de cada nó correspondente à **\<Customer>** consulta navegará para seus **\<Order>** elementos.</span><span class="sxs-lookup"><span data-stu-id="e6060-139">If the XPath query is specified as `Customer/Order/OrderDetail`, from each node matching **\<Customer>** the query navigates to its **\<Order>** elements.</span></span> <span data-ttu-id="e6060-140">E para cada nó correspondente **\<Order>** , a consulta adiciona os nós **\<OrderDetail>** ao resultado.</span><span class="sxs-lookup"><span data-stu-id="e6060-140">And for each node matching **\<Order>**, the query adds the nodes **\<OrderDetail>** to the result.</span></span> <span data-ttu-id="e6060-141">Somente **\<OrderDetail>** é retornado no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="e6060-141">Only **\<OrderDetail>** is returned in the result set.</span></span>  
  
### <a name="c-use--to-specify-the-parent-axis"></a><span data-ttu-id="e6060-142">C.</span><span class="sxs-lookup"><span data-stu-id="e6060-142">C.</span></span> <span data-ttu-id="e6060-143">Usar .</span><span class="sxs-lookup"><span data-stu-id="e6060-143">Use ..</span></span> <span data-ttu-id="e6060-144">para especificar o eixo pai</span><span class="sxs-lookup"><span data-stu-id="e6060-144">to specify the parent axis</span></span>  
 <span data-ttu-id="e6060-145">A consulta a seguir recupera todos os **\<Order>** elementos com um **\<Customer>** elemento pai com um valor de atributo **CustomerID** de 1.</span><span class="sxs-lookup"><span data-stu-id="e6060-145">The following query retrieves all the **\<Order>** elements with a parent **\<Customer>** element with a **CustomerID** attribute value of 1.</span></span> <span data-ttu-id="e6060-146">A consulta usa o `child` eixo no predicado para localizar o pai do **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="e6060-146">The query uses the `child` axis in the predicate to find the parent of the **\<Order>** element.</span></span>  
  
```  
/child::Customer/child::Order[../@CustomerID="1"]  
```  
  
 <span data-ttu-id="e6060-147">O `child` eixo é o eixo padrão.</span><span class="sxs-lookup"><span data-stu-id="e6060-147">The `child` axis is the default axis.</span></span> <span data-ttu-id="e6060-148">Assim, a consulta pode ser especificada como:</span><span class="sxs-lookup"><span data-stu-id="e6060-148">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer/Order[../@CustomerID="1"]  
```  
  
 <span data-ttu-id="e6060-149">A consulta XPath é equivalente a:</span><span class="sxs-lookup"><span data-stu-id="e6060-149">The XPath query is equivalent to:</span></span>  
  
```  
/Customer[@CustomerID="1"]/Order.  
```  
  
> [!NOTE]  
>  <span data-ttu-id="e6060-150">A consulta XPath `/Order[../@CustomerID="1"]` retornará um erro, pois não há nenhum pai de **\<Order>** .</span><span class="sxs-lookup"><span data-stu-id="e6060-150">The XPath query `/Order[../@CustomerID="1"]` will return an error because there is no parent of **\<Order>**.</span></span> <span data-ttu-id="e6060-151">Embora possa haver elementos no esquema de mapeamento que contêm **\<Order>** , o XPath não começou em nenhum deles; consequentemente, **\<Order>** é considerado um tipo de elemento de nível superior no documento.</span><span class="sxs-lookup"><span data-stu-id="e6060-151">Although there may be elements in the mapping schema that contain **\<Order>**, the XPath did not begin at any of them; consequently, **\<Order>** is considered to be the top-level element type in the document.</span></span>  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="e6060-152">Para testar a consulta XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="e6060-152">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="e6060-153">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e6060-153">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="e6060-154">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="e6060-154">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="e6060-155">Crie o seguinte modelo (XPathAxesSampleC.xml) e salve-o no diretório onde:</span><span class="sxs-lookup"><span data-stu-id="e6060-155">Create the following template (XPathAxesSampleC.xml) and save it in the directory where:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer/Order[../@CustomerID="1"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e6060-156">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="e6060-156">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e6060-157">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e6060-157">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="e6060-158">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e6060-158">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e6060-159">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e6060-159">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e6060-160">Aqui está o conjunto de resultados parcial da execução do modelo:</span><span class="sxs-lookup"><span data-stu-id="e6060-160">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
         OrderDate="2001-08-01T00:00:00"   
         DueDate="2001-08-13T00:00:00"   
         ShipDate="2001-08-08T00:00:00">  
  <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-753" UnitPrice="2576.3544"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-756" UnitPrice="1049.7528"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-758" UnitPrice="1049.7528"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-761" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-762" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-763" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-765" UnitPrice="503.3507"   
               OrderQty="2" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-768" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  <OrderDetail ProductID="Prod-770" UnitPrice="503.3507"   
               OrderQty="1" UnitPriceDiscount="0" />   
  </Order>  
   ...  
</Order>  
</ROOT>  
```  
  
### <a name="d-specify-the-attribute-axis"></a><span data-ttu-id="e6060-161">D.</span><span class="sxs-lookup"><span data-stu-id="e6060-161">D.</span></span> <span data-ttu-id="e6060-162">Especificar o eixo de atributo</span><span class="sxs-lookup"><span data-stu-id="e6060-162">Specify the attribute axis</span></span>  
 <span data-ttu-id="e6060-163">A consulta XPath a seguir seleciona todos os **\<Customer>** elementos filho do nó de contexto com um valor de atributo **CustomerID** de 1:</span><span class="sxs-lookup"><span data-stu-id="e6060-163">The following XPath query selects all the **\<Customer>** child elements of the context node with a **CustomerID** attribute value of 1:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="1"]  
```  
  
 <span data-ttu-id="e6060-164">No predicado `attribute::CustomerID` , `attribute` é o eixo e `CustomerID` é o teste do nó (se `CustomerID` for um atributo, o teste do nó será verdadeiro, pois o **\<attribute>** nó é o nó primário do `attribute` eixo).</span><span class="sxs-lookup"><span data-stu-id="e6060-164">In the predicate `attribute::CustomerID`, `attribute` is the axis and `CustomerID` is the node test (if `CustomerID` is an attribute the node test is TRUE, because the **\<attribute>** node is the primary node for the `attribute` axis).</span></span>  
  
 <span data-ttu-id="e6060-165">Um atalho para o eixo `attribute` (@) pode ser especificado e, como o eixo `child` é o padrão, ele pode ser omitido da consulta:</span><span class="sxs-lookup"><span data-stu-id="e6060-165">A shortcut to the `attribute` axis (@) can be specified, and because `child` is the default axis, it can be omitted from the query:</span></span>  
  
```  
/Customer[@CustomerID="1"]  
```  
  
##### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="e6060-166">Para testar a consulta XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="e6060-166">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="e6060-167">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e6060-167">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="e6060-168">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="e6060-168">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="e6060-169">Crie seguinte o modelo (XPathAxesSampleD.xml) e salve-o no diretório onde SampleSchema1.xml foi salvo.</span><span class="sxs-lookup"><span data-stu-id="e6060-169">Create the following template (XPathAxesSampleD.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        child::Customer[attribute::CustomerID="1"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e6060-170">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="e6060-170">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e6060-171">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e6060-171">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="e6060-172">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e6060-172">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e6060-173">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e6060-173">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e6060-174">Aqui está o conjunto de resultados parcial da execução do modelo:</span><span class="sxs-lookup"><span data-stu-id="e6060-174">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="1" SalesPersonID="280"   
            TerritoryID="1" AccountNumber="1"   
            CustomerType="S" Orders="Ord-43860 Ord-44501 Ord-45283 Ord-46042">  
    <Order SalesOrderID="Ord-43860" SalesPersonID="280"   
           OrderDate="2001-08-01T00:00:00"   
           DueDate="2001-08-13T00:00:00"   
           ShipDate="2001-08-08T00:00:00">  
       <OrderDetail ProductID="Prod-729" UnitPrice="226.8571"   
                    OrderQty="1" UnitPriceDiscount="0" />   
       <OrderDetail ProductID="Prod-732" UnitPrice="440.1742"   
                    OrderQty="1" UnitPriceDiscount="0" />   
       <OrderDetail ProductID="Prod-738" UnitPrice="220.2496"   
                    OrderQty="1" UnitPriceDiscount="0" />   
      ...   
    </Order>  
   ...  
  </Customer>  
</ROOT>  
```  
  
  
