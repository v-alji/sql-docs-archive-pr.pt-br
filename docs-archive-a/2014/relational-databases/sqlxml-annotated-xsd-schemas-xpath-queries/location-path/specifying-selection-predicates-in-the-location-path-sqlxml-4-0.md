---
title: Especificando predicados de seleção no caminho do local (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], predicates
- predicates [SQLXML]
- position-based filtering [SQLXML]
- XPath queries [SQLXML], location paths
- filtering [SQLXML]
- location path for XPath query
ms.assetid: dbef4cf4-a89b-4d7e-b72b-4062f7b29a80
author: rothja
ms.author: jroth
ms.openlocfilehash: d323558556fb05d350e48ea9218a8e9b8dc9b5c9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574585"
---
# <a name="specifying-selection-predicates-in-the-location-path-sqlxml-40"></a><span data-ttu-id="d92c8-102">Especificando predicados de seleção no caminho do local (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="d92c8-102">Specifying Selection Predicates in the Location Path (SQLXML 4.0)</span></span>
  <span data-ttu-id="d92c8-103">Um predicado filtra um conjunto de nós com respeito a um eixo (semelhantemente a uma cláusula WHERE em uma instrução SELECT).</span><span class="sxs-lookup"><span data-stu-id="d92c8-103">A predicate filters a node-set with respect to an axis (similar to a WHERE clause in a SELECT statement).</span></span> <span data-ttu-id="d92c8-104">O predicado é especificado entre colchetes.</span><span class="sxs-lookup"><span data-stu-id="d92c8-104">The predicate is specified between brackets.</span></span> <span data-ttu-id="d92c8-105">Para cada nó no conjunto de nós a ser filtrado, a expressão de predicado é avaliada com esse nó como o nó de contexto, com o número de nós no conjunto de nós como o tamanho do contexto.</span><span class="sxs-lookup"><span data-stu-id="d92c8-105">For each node in the node-set to be filtered, the predicate expression is evaluated with that node as the context node, with the number of nodes in the node-set as context size.</span></span> <span data-ttu-id="d92c8-106">Se a expressão de predicado for avaliada como TRUE para esse nó, o nó será incluído no conjunto de nós resultante.</span><span class="sxs-lookup"><span data-stu-id="d92c8-106">If the predicate expression evaluates to TRUE for that node, the node is included in the resulting node-set.</span></span>  
  
 <span data-ttu-id="d92c8-107">XPath também permite a filtragem com base na posição.</span><span class="sxs-lookup"><span data-stu-id="d92c8-107">XPath also allows position-based filtering.</span></span> <span data-ttu-id="d92c8-108">Uma expressão de predicado avaliada como um número seleciona esse nó ordinal.</span><span class="sxs-lookup"><span data-stu-id="d92c8-108">A predicate expression evaluating to a number selects that ordinal node.</span></span> <span data-ttu-id="d92c8-109">Por exemplo, o caminho do local `Customer[3]` retorna o terceiro cliente.</span><span class="sxs-lookup"><span data-stu-id="d92c8-109">For example, the location path `Customer[3]` returns the third customer.</span></span> <span data-ttu-id="d92c8-110">Não há suporte para tais predicados numéricos.</span><span class="sxs-lookup"><span data-stu-id="d92c8-110">Such numeric predicates are not supported.</span></span> <span data-ttu-id="d92c8-111">Há suporte somente para expressões de predicado que retornem um resultado Boolean.</span><span class="sxs-lookup"><span data-stu-id="d92c8-111">Only predicate expressions that return a Boolean result are supported.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="d92c8-112">Para obter informações sobre as limitações dessa implementação XPath do XPath e as diferenças entre ela e a especificação W3C, consulte [introdução ao uso de consultas XPath &#40;SQLXML 4,0&#41;](../introduction-to-using-xpath-queries-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="d92c8-112">For information about the limitations of this XPath implementation of XPath and the differences between it and the W3C specification, see [Introduction to Using XPath Queries &#40;SQLXML 4.0&#41;](../introduction-to-using-xpath-queries-sqlxml-4-0.md).</span></span>  
  
## <a name="selection-predicate-example-1"></a><span data-ttu-id="d92c8-113">Predicado de seleção: exemplo 1</span><span class="sxs-lookup"><span data-stu-id="d92c8-113">Selection Predicate: Example 1</span></span>  
 <span data-ttu-id="d92c8-114">A seguinte expressão XPath (caminho do local) seleciona a partir do nó de contexto atual todos os **\<Customer>** filhos do elemento que têm o atributo **CustomerID** com o valor de ALFKI:</span><span class="sxs-lookup"><span data-stu-id="d92c8-114">The following XPath expression (location path) selects from the current context node all the **\<Customer>** element children that have the **CustomerID** attribute with value of ALFKI:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="ALFKI"]  
```  
  
 <span data-ttu-id="d92c8-115">Nesta consulta XPath, `child` e `attribute` são nomes de eixo.</span><span class="sxs-lookup"><span data-stu-id="d92c8-115">In this XPath query, `child` and `attribute` are axis names.</span></span> <span data-ttu-id="d92c8-116">`Customer`é o teste de nó (verdadeiro se `Customer` for um **\<element node>** , porque **\<element>** é o tipo de nó principal para o `child` eixo).</span><span class="sxs-lookup"><span data-stu-id="d92c8-116">`Customer` is the node test (TRUE if `Customer` is an **\<element node>**, because **\<element>** is the principal node type for the `child` axis).</span></span> <span data-ttu-id="d92c8-117">`attribute::CustomerID="ALFKI"` é o predicado.</span><span class="sxs-lookup"><span data-stu-id="d92c8-117">`attribute::CustomerID="ALFKI"` is the predicate.</span></span> <span data-ttu-id="d92c8-118">No predicado, `attribute` é o eixo e `CustomerID` é o teste de nó (true se **CustomerID** é um atributo do nó de contexto, porque **\<attribute>** é o tipo de nó principal do `attribute` eixo).</span><span class="sxs-lookup"><span data-stu-id="d92c8-118">In the predicate, `attribute` is the axis and `CustomerID` is the node test (TRUE if **CustomerID** is an attribute of the context node, because **\<attribute>** is the principal node type of `attribute` axis).</span></span>  
  
 <span data-ttu-id="d92c8-119">Usando a sintaxe abreviada, a consulta XPath também pode ser especificada como:</span><span class="sxs-lookup"><span data-stu-id="d92c8-119">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
/Customer[@CustomerID="ALFKI"]  
```  
  
## <a name="selection-predicate-example-2"></a><span data-ttu-id="d92c8-120">Predicado de seleção: exemplo 2</span><span class="sxs-lookup"><span data-stu-id="d92c8-120">Selection Predicate: Example 2</span></span>  
 <span data-ttu-id="d92c8-121">A seguinte expressão XPath (caminho de localização) seleciona a partir do nó de contexto atual todos os **\<Order>** netos que têm o atributo **SalesOrderID** com o valor 1:</span><span class="sxs-lookup"><span data-stu-id="d92c8-121">The following XPath expression (location path) selects from the current context node all the **\<Order>** grandchildren that have the **SalesOrderID** attribute with the value 1:</span></span>  
  
```  
/child::Customer/child::Order[attribute::SalesOrderID="1"]  
```  
  
 <span data-ttu-id="d92c8-122">Nesta expressão XPath, `child` e `attribute` são os nomes de eixo.</span><span class="sxs-lookup"><span data-stu-id="d92c8-122">In this XPath expression, `child` and `attribute` are the axis names.</span></span> <span data-ttu-id="d92c8-123">`Customer`, `Order` e `SalesOrderID` são os testes de nó.</span><span class="sxs-lookup"><span data-stu-id="d92c8-123">`Customer`, `Order`, and `SalesOrderID` are the node tests.</span></span> <span data-ttu-id="d92c8-124">`attribute::OrderID="1"` é o predicado.</span><span class="sxs-lookup"><span data-stu-id="d92c8-124">`attribute::OrderID="1"` is the predicate.</span></span>  
  
 <span data-ttu-id="d92c8-125">Usando a sintaxe abreviada, a consulta XPath também pode ser especificada como:</span><span class="sxs-lookup"><span data-stu-id="d92c8-125">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
/Customer/Order[@SalesOrderID="1"]  
```  
  
## <a name="selection-predicate-example-3"></a><span data-ttu-id="d92c8-126">Predicado de seleção: exemplo 3</span><span class="sxs-lookup"><span data-stu-id="d92c8-126">Selection Predicate: Example 3</span></span>  
 <span data-ttu-id="d92c8-127">A seguinte expressão XPath (caminho de localização) seleciona a partir do nó de contexto atual todos os **\<Customer>** filhos que têm um ou mais **\<ContactName>** filhos:</span><span class="sxs-lookup"><span data-stu-id="d92c8-127">The following XPath expression (location path) selects from the current context node all the **\<Customer>** children that have one or more **\<ContactName>** children:</span></span>  
  
```  
child::Customer[child::ContactName]  
```  
  
 <span data-ttu-id="d92c8-128">Este exemplo pressupõe que o **\<ContactName>** é um elemento filho do **\<Customer>** elemento no documento XML, que é conhecido como *mapeamento centrado em elemento* em um esquema XSD anotado.</span><span class="sxs-lookup"><span data-stu-id="d92c8-128">This example assumes that the **\<ContactName>** is a child element of the **\<Customer>** element in the XML document, which is referred to as *element-centric mapping* in an annotated XSD schema.</span></span>  
  
 <span data-ttu-id="d92c8-129">Nesta expressão XPath, `child` é o nome do eixo.</span><span class="sxs-lookup"><span data-stu-id="d92c8-129">In this XPath expression, `child` is the axis name.</span></span> <span data-ttu-id="d92c8-130">`Customer`é o teste de nó (TRUE se `Customer` for um **\<element>** nó, porque **\<element>** é o tipo de nó principal para `child` Axis).</span><span class="sxs-lookup"><span data-stu-id="d92c8-130">`Customer` is the node test (TRUE if `Customer` is an **\<element>** node, because **\<element>** is the principal node type for `child` axis).</span></span> <span data-ttu-id="d92c8-131">`child::ContactName` é o predicado.</span><span class="sxs-lookup"><span data-stu-id="d92c8-131">`child::ContactName` is the predicate.</span></span> <span data-ttu-id="d92c8-132">No predicado, `child` é o eixo e `ContactName` é o teste de nó (verdadeiro se `ContactName` for um **\<element>** nó).</span><span class="sxs-lookup"><span data-stu-id="d92c8-132">In the predicate, `child` is the axis and `ContactName` is the node test (TRUE if `ContactName` is an **\<element>** node).</span></span>  
  
 <span data-ttu-id="d92c8-133">Essa expressão retorna somente os **\<Customer>** filhos do elemento do nó de contexto que têm **\<ContactName>** elementos filhos.</span><span class="sxs-lookup"><span data-stu-id="d92c8-133">This expression returns only the **\<Customer>** element children of the context node that have **\<ContactName>** element children.</span></span>  
  
 <span data-ttu-id="d92c8-134">Usando a sintaxe abreviada, a consulta XPath também pode ser especificada como:</span><span class="sxs-lookup"><span data-stu-id="d92c8-134">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[ContactName]  
```  
  
## <a name="selection-predicate-example-4"></a><span data-ttu-id="d92c8-135">Predicado de seleção: exemplo 4</span><span class="sxs-lookup"><span data-stu-id="d92c8-135">Selection Predicate: Example 4</span></span>  
 <span data-ttu-id="d92c8-136">A expressão XPath a seguir seleciona **\<Customer>** elementos filhos do nó de contexto que não têm **\<ContactName>** elementos filho:</span><span class="sxs-lookup"><span data-stu-id="d92c8-136">The following XPath expression selects **\<Customer>** element children of the context node that do not have **\<ContactName>** element children:</span></span>  
  
```  
child::Customer[not(child::ContactName)]  
```  
  
 <span data-ttu-id="d92c8-137">Este exemplo pressupõe que **\<ContactName>** é um elemento filho do **\<Customer>** elemento no documento XML, e o campo ContactName não é necessário no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d92c8-137">This example assumes that **\<ContactName>** is a child element of the **\<Customer>** element in the XML document, and the ContactName field is not required in the database.</span></span>  
  
 <span data-ttu-id="d92c8-138">Neste exemplo, `child` é o eixo.</span><span class="sxs-lookup"><span data-stu-id="d92c8-138">In this example, `child` is the axis.</span></span> <span data-ttu-id="d92c8-139">`Customer`é o teste de nó (verdadeiro se `Customer` for um \<element> nó).</span><span class="sxs-lookup"><span data-stu-id="d92c8-139">`Customer` is the node test (TRUE if `Customer` is an \<element> node).</span></span> <span data-ttu-id="d92c8-140">`not(child::ContactName)` é o predicado.</span><span class="sxs-lookup"><span data-stu-id="d92c8-140">`not(child::ContactName)` is the predicate.</span></span> <span data-ttu-id="d92c8-141">No predicado, `child` é o eixo e `ContactName` é o teste de nó (verdadeiro se `ContactName` for um \<element> nó).</span><span class="sxs-lookup"><span data-stu-id="d92c8-141">In the predicate, `child` is the axis and `ContactName` is the node test (TRUE if `ContactName` is an \<element> node).</span></span>  
  
 <span data-ttu-id="d92c8-142">Usando a sintaxe abreviada, a consulta XPath também pode ser especificada como:</span><span class="sxs-lookup"><span data-stu-id="d92c8-142">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[not(ContactName)]  
```  
  
## <a name="selection-predicate-example-5"></a><span data-ttu-id="d92c8-143">Predicado de seleção: exemplo 5</span><span class="sxs-lookup"><span data-stu-id="d92c8-143">Selection Predicate: Example 5</span></span>  
 <span data-ttu-id="d92c8-144">A expressão XPath a seguir seleciona a partir do nó de contexto atual todos os **\<Customer>** filhos que têm o atributo **CustomerID** :</span><span class="sxs-lookup"><span data-stu-id="d92c8-144">The following XPath expression selects from the current context node all the **\<Customer>** children that have the **CustomerID** attribute:</span></span>  
  
```  
child::Customer[attribute::CustomerID]  
```  
  
 <span data-ttu-id="d92c8-145">Neste exemplo, `child` é o eixo e `Customer` é o teste de nó (verdadeiro se `Customer` for um \<element> nó).</span><span class="sxs-lookup"><span data-stu-id="d92c8-145">In this example, `child` is the axis and `Customer` is node test (TRUE if `Customer` is an \<element> node).</span></span> <span data-ttu-id="d92c8-146">`attribute::CustomerID` é o predicado.</span><span class="sxs-lookup"><span data-stu-id="d92c8-146">`attribute::CustomerID` is the predicate.</span></span> <span data-ttu-id="d92c8-147">No predicado, `attribute` é o eixo e `CustomerID` é o predicado (true se `CustomerID` for um **\<attribute>** nó).</span><span class="sxs-lookup"><span data-stu-id="d92c8-147">In the predicate, `attribute` is the axis and `CustomerID` is the predicate (TRUE if `CustomerID` is an **\<attribute>** node).</span></span>  
  
 <span data-ttu-id="d92c8-148">Usando a sintaxe abreviada, a consulta XPath também pode ser especificada como:</span><span class="sxs-lookup"><span data-stu-id="d92c8-148">Using the abbreviated syntax, the XPath query can also be specified as:</span></span>  
  
```  
Customer[@CustomerID]  
```  
  
## <a name="selection-predicate-example-6"></a><span data-ttu-id="d92c8-149">Predicado de seleção: Exemplo 6</span><span class="sxs-lookup"><span data-stu-id="d92c8-149">Selection Predicate: Example 6</span></span>  
 <span data-ttu-id="d92c8-150">O [!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 inclui suporte para consultas XPath que contenham um produto cruzado no predicado, conforme mostrado no seguinte exemplo:</span><span class="sxs-lookup"><span data-stu-id="d92c8-150">[!INCLUDE[msCoName](../../../includes/msconame-md.md)] SQLXML 4.0 includes support for XPath queries that contain a cross-product in the predicate, as shown in the following example:</span></span>  
  
```  
Customer[Order/@OrderDate=Order/@ShipDate]  
```  
  
 <span data-ttu-id="d92c8-151">Esta consulta seleciona todos os clientes com qualquer `Order` para o qual `OrderDate` é igual a qualquer `ShipDate` de qualquer `Order`.</span><span class="sxs-lookup"><span data-stu-id="d92c8-151">This query selects all customers with any `Order` for which the `OrderDate` equals the `ShipDate` of any `Order`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d92c8-152">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d92c8-152">See Also</span></span>  
 <span data-ttu-id="d92c8-153">[Introdução aos esquemas XSD anotados &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) </span><span class="sxs-lookup"><span data-stu-id="d92c8-153">[Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md) </span></span>  
 [<span data-ttu-id="d92c8-154">Formatação XML do lado do cliente &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="d92c8-154">Client-side XML Formatting &#40;SQLXML 4.0&#41;</span></span>](../../sqlxml/formatting/client-side-xml-formatting-sqlxml-4-0.md)  
  
  
