---
title: Especificando operadores boolianos em consultas XPath (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XPath operators [SQLXML]
- OR operator
- Boolean operators
- XPath queries [SQLXML], Boolean operators
- operators [SQLXML]
ms.assetid: 9928cff5-62ac-42aa-96bf-2e09a1df0bc3
author: rothja
ms.author: jroth
ms.openlocfilehash: 02dd6e1f120b53382ce984684ea352b36d34b768
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569290"
---
# <a name="specifying-boolean-operators-in-xpath-queries-sqlxml-40"></a><span data-ttu-id="6c405-102">Especificando operadores boolianos em consultas XPath (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="6c405-102">Specifying Boolean Operators in XPath Queries (SQLXML 4.0)</span></span>
  <span data-ttu-id="6c405-103">O exemplo a seguir mostra como os operadores Boolianos são especificados em consultas XPath.</span><span class="sxs-lookup"><span data-stu-id="6c405-103">The following example shows how Boolean operators are specified in XPath queries.</span></span> <span data-ttu-id="6c405-104">A consulta XPath deste exemplo é especificada com relação ao esquema de mapeamento contido em SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="6c405-104">The XPath query in this example is specified against the mapping schema contained in SampleSchema1.xml.</span></span> <span data-ttu-id="6c405-105">Para obter informações sobre este esquema de exemplo, consulte [exemplo de esquema XSD anotado para exemplos de XPath &#40;SQLXML 4,0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="6c405-105">For information about this sample schema, see [Sample Annotated XSD Schema for XPath Examples &#40;SQLXML 4.0&#41;](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6c405-106">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6c405-106">Examples</span></span>  
  
### <a name="a-specify-the-or-boolean-operator"></a><span data-ttu-id="6c405-107">a.</span><span class="sxs-lookup"><span data-stu-id="6c405-107">A.</span></span> <span data-ttu-id="6c405-108">Especificar o operador booliano OR</span><span class="sxs-lookup"><span data-stu-id="6c405-108">Specify the OR Boolean operator</span></span>  
 <span data-ttu-id="6c405-109">Essa consulta XPath retorna o **\<Customer>** elemento filho do nó de contexto com o valor do atributo **CustomerID** de 13 ou 31:</span><span class="sxs-lookup"><span data-stu-id="6c405-109">This XPath query returns the **\<Customer>** element children of the context node with the **CustomerID** attribute value of 13 or 31:</span></span>  
  
```  
/child::Customer[attribute::CustomerID="13" or attribute::CustomerID="31"]  
```  
  
 <span data-ttu-id="6c405-110">Um atalho para o eixo `attribute` (@) pode ser especificado e, como o eixo `child` é o padrão, ele pode ser omitido:</span><span class="sxs-lookup"><span data-stu-id="6c405-110">A shortcut to the `attribute` axis (@) can be specified, and because the `child` axis is the default, it can be omitted:</span></span>  
  
```  
/Customer[@CustomerID="13" or @CustomerID="31"]  
```  
  
 <span data-ttu-id="6c405-111">No predicado, `attribute` é o eixo e `CustomerID` é o teste de nó (true se **CustomerID** for um **\<attribute>** nó, porque o **\<attribute>** nó é o nó primário do `attribute` eixo).</span><span class="sxs-lookup"><span data-stu-id="6c405-111">In the predicate, `attribute` is the axis and `CustomerID` is the node test (TRUE if **CustomerID** is an **\<attribute>** node, because the **\<attribute>** node is the primary node for the `attribute` axis).</span></span> <span data-ttu-id="6c405-112">O predicado filtra os **\<Customer>** elementos e retorna apenas aqueles que atendem à condição especificada no predicado.</span><span class="sxs-lookup"><span data-stu-id="6c405-112">The predicate filters the **\<Customer>** elements and returns only those that satisfy the condition specified in the predicate.</span></span>  
  
##### <a name="to-test-the-xpath-queries-against-the-mapping-schema"></a><span data-ttu-id="6c405-113">Para testar as consultas XPath com relação ao esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="6c405-113">To test the XPath queries against the mapping schema</span></span>  
  
1.  <span data-ttu-id="6c405-114">Copie o [código do esquema de exemplo](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="6c405-114">Copy the [sample schema code](sample-annotated-xsd-schema-for-xpath-examples-sqlxml-4-0.md) and paste it into a text file.</span></span> <span data-ttu-id="6c405-115">Salve o arquivo como SampleSchema1.xml.</span><span class="sxs-lookup"><span data-stu-id="6c405-115">Save the file as SampleSchema1.xml.</span></span>  
  
2.  <span data-ttu-id="6c405-116">Crie o modelo a seguir (BooleanOperatorsA.xml) e salve-o no diretório em que SampleSchema1.xml foi salvo.</span><span class="sxs-lookup"><span data-stu-id="6c405-116">Create the following template (BooleanOperatorsA.xml) and save it in the directory where SampleSchema1.xml is saved.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="SampleSchema1.xml">  
        /Customer[@CustomerID="13" or @CustomerID="31"]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="6c405-117">O caminho do diretório especificado para o esquema de mapeamento (SampleSchema1.xml) é relativo ao diretório em que o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="6c405-117">The directory path specified for the mapping schema (SampleSchema1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="6c405-118">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6c405-118">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\SampleSchema1.xml"  
    ```  
  
3.  <span data-ttu-id="6c405-119">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="6c405-119">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="6c405-120">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="6c405-120">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="6c405-121">Aqui está o conjunto de resultados da execução do modelo:</span><span class="sxs-lookup"><span data-stu-id="6c405-121">Here is the result set of the template execution:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customer CustomerID="13" SalesPersonID="286" TerritoryID="7" AccountNumber="13" CustomerType="S" />   
  <Customer CustomerID="31" SalesPersonID="286" TerritoryID="7" AccountNumber="31" CustomerType="S" Orders="Ord-51803 Ord-69427">  
    <Order SalesOrderID="Ord-51803" SalesPersonID="286" OrderDate="2003-08-01T00:00:00" DueDate="2003-08-13T00:00:00" ShipDate="2003-08-08T00:00:00">  
      <OrderDetail ProductID="Prod-718" UnitPrice="1059.31" OrderQty="1" UnitPriceDiscount="0" />   
      <OrderDetail ProductID="Prod-838" UnitPrice="1059.31" OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
    <Order SalesOrderID="Ord-69427" SalesPersonID="286" OrderDate="2004-05-01T00:00:00" DueDate="2004-05-13T00:00:00" ShipDate="2004-05-08T00:00:00">  
      <OrderDetail ProductID="Prod-835" UnitPrice="440.1742" OrderQty="1" UnitPriceDiscount="0" />   
    </Order>  
  </Customer>  
</ROOT>  
```  
  
  
