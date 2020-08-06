---
title: Especificando funções booleanas em consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath queries [SQLXML], Boolean functions
- false function
- not function [SQLXML]
- true function
- Boolean functions
ms.assetid: c72cd333-9294-4d41-84f2-1748bf20e3eb
author: rothja
ms.author: jroth
ms.openlocfilehash: d230c7cd8792066732085b9ce501c0794687d17d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569291"
---
# <a name="specifying-boolean-functions-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="4b2e6-102">Especificando funções boolianas em consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4b2e6-102">Specifying Boolean Functions in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="4b2e6-103">Os exemplos a seguir mostram como as funções boolianas são especificadas em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-103">The following examples show how Boolean functions are specified in XPath queries.</span></span> <span data-ttu-id="4b2e6-104">As consultas XPath nesses exemplos são especificadas com relação ao esquema de mapeamento contido em SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-104">The XPath queries in these examples are specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="4b2e6-105">Para obter informações sobre este esquema de exemplo, consulte [exemplo de esquema XSD anotado para exemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="4b2e6-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="4b2e6-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="4b2e6-106">Examples</span></span>  
  
## <a name="a-specify-the-not-boolean-function"></a><span data-ttu-id="4b2e6-107">a.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-107">A.</span></span> <span data-ttu-id="4b2e6-108">Especificar a função booliana not()</span><span class="sxs-lookup"><span data-stu-id="4b2e6-108">Specify the not() Boolean function</span></span>  
 <span data-ttu-id="4b2e6-109">Essa consulta retorna todos os **\<Customer>** elementos filho do nó de contexto que não têm **\<Order>** elementos filho:</span><span class="sxs-lookup"><span data-stu-id="4b2e6-109">This query returns all the **\<Customer>** child elements of the context node that do not have **\<Order>** child elements:</span></span>  
  
```  
/child::Customer[not(child::Order)]  
```  
  
 <span data-ttu-id="4b2e6-110">O eixo `child` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-110">The `child` axis is the default.</span></span> <span data-ttu-id="4b2e6-111">Assim, a consulta pode ser especificada como:</span><span class="sxs-lookup"><span data-stu-id="4b2e6-111">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[not(Order)]  
```  
  
#### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="4b2e6-112">Para testar a consulta XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="4b2e6-112">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="4b2e6-113">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-113">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="4b2e6-114">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-114">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="4b2e6-115">Crie o modelo a seguir (BooleanFunctionsA.xml) e salve-o no diretório em que SampleSchema1.xml foi salvo.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-115">Create the following template (BooleanFunctionsA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        Customer[not(Order)]  
    </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="4b2e6-116">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-116">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="4b2e6-117">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4b2e6-117">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="4b2e6-118">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-118">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="4b2e6-119">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4b2e6-119">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="4b2e6-120">Aqui está o conjunto de resultados parcial da execução do modelo:</span><span class="sxs-lookup"><span data-stu-id="4b2e6-120">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="32" SalesPersonID="289" TerritoryID="8" AccountNumber="32" CustomerType="S" />   
  <Customer CustomerID="35" SalesPersonID="275" TerritoryID="2" AccountNumber="35" CustomerType="S" />   
  ...  
</ROOT>  
```  
  
## <a name="b-specify-the-true-and-false-boolean-functions"></a><span data-ttu-id="4b2e6-121">B.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-121">B.</span></span> <span data-ttu-id="4b2e6-122">Especificar as funções boolianas true() e false()</span><span class="sxs-lookup"><span data-stu-id="4b2e6-122">Specify the true() and false() Boolean functions</span></span>  
 <span data-ttu-id="4b2e6-123">Essa consulta retorna todos os elementos **\<Customer>** filho do nó de contexto que não têm **\<Order>** elementos filho.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-123">This query returns all **\<Customer>** element children of the context node that do not have **\<Order>** child elements.</span></span> <span data-ttu-id="4b2e6-124">Em termos relacionais, esta consulta retorna todos os clientes que não fizeram nenhum pedido.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-124">In relational terms, this query returns all customers who have not placed any orders.</span></span>  
  
```  
/child::Customer[child::Order=false()]  
```  
  
 <span data-ttu-id="4b2e6-125">O eixo `child` é o padrão.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-125">The `child` axis is the default.</span></span> <span data-ttu-id="4b2e6-126">Assim, a consulta pode ser especificada como:</span><span class="sxs-lookup"><span data-stu-id="4b2e6-126">Therefore, the query can be specified as:</span></span>  
  
```  
/Customer[Order=false()]  
```  
  
 <span data-ttu-id="4b2e6-127">Essa consulta é equivalente à especificação a seguir:</span><span class="sxs-lookup"><span data-stu-id="4b2e6-127">This query is equivalent to the following:</span></span>  
  
```  
/Customer[not(Order)]  
```  
  
 <span data-ttu-id="4b2e6-128">A consulta seguinte retorna todos os clientes que fizeram pelo menos um pedido:</span><span class="sxs-lookup"><span data-stu-id="4b2e6-128">The following query returns all the customers who have placed at least one order:</span></span>  
  
```  
/Customer[Order=true()]  
```  
  
 <span data-ttu-id="4b2e6-129">Essa consulta é equivalente a esta:</span><span class="sxs-lookup"><span data-stu-id="4b2e6-129">This query is equivalent to this one:</span></span>  
  
```  
/Customer[Order]  
```  
  
#### <a name="to-test-the-xpath-query-against-the-mapping-schema"></a><span data-ttu-id="4b2e6-130">Para testar a consulta XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="4b2e6-130">To test the XPath query against the mapping schema</span></span>  
  
1.  <span data-ttu-id="4b2e6-131">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-131">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="4b2e6-132">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-132">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="4b2e6-133">Crie o modelo a seguir (BooleanFunctionsB.xml) e salve-o no diretório em que SampleSchema1.xml foi salvo.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-133">Create the following template (BooleanFunctionsB.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[Order=false()]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="4b2e6-134">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-134">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="4b2e6-135">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="4b2e6-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="4b2e6-136">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="4b2e6-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="4b2e6-137">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="4b2e6-137">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="4b2e6-138">Aqui está o conjunto de resultados parcial da execução do modelo:</span><span class="sxs-lookup"><span data-stu-id="4b2e6-138">Here is the partial result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="32" SalesPersonID="289" TerritoryID="8" AccountNumber="32" CustomerType="S" />   
  <Customer CustomerID="35" SalesPersonID="275" TerritoryID="2" AccountNumber="35" CustomerType="S" />   
  ...  
</ROOT>  
```  
  
  
