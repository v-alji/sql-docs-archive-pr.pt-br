---
title: 'Criando elementos constantes usando SQL: is-constant (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- element does not map [SQLXML]
- sql:is-constant
- XSD schemas [SQLXML], constant elements
- element mapping [SQLXML], constant elements
- is-constant annotation
- constant elements [SQLXML]
- annotated XSD schemas, constant elements
ms.assetid: 940eea1b-54f5-445f-b844-c894d9f3941b
author: rothja
ms.author: jroth
ms.openlocfilehash: 8deedd8547d6bc3f0154eedb889ad908750f071a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681479"
---
# <a name="creating-constant-elements-using-sqlis-constant-sqlxml-40"></a><span data-ttu-id="a695c-102">Criando elementos constantes usando sql:is-constant (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="a695c-102">Creating Constant Elements Using sql:is-constant (SQLXML 4.0)</span></span>
  <span data-ttu-id="a695c-103">Para especificar um elemento Constant, ou seja, um elemento no esquema XSD que não é mapeado para nenhuma tabela ou coluna de banco de dados, você pode usar a `sql:is-constant` anotação.</span><span class="sxs-lookup"><span data-stu-id="a695c-103">To specify a constant element-that is, an element in the XSD schema that does not map to any database table or column-you can use the `sql:is-constant` annotation.</span></span> <span data-ttu-id="a695c-104">Essa anotação usa um valor Booliano (0 = false, 1 = true).</span><span class="sxs-lookup"><span data-stu-id="a695c-104">This annotation takes a Boolean value (0 = false, 1 = true).</span></span> <span data-ttu-id="a695c-105">Os valores aceitáveis são 0, 1, true e false.</span><span class="sxs-lookup"><span data-stu-id="a695c-105">The acceptable values are 0, 1, true, and false.</span></span> <span data-ttu-id="a695c-106">A anotação `sql:is-constant` pode ser especificada em um elemento que não tem nenhum atributo.</span><span class="sxs-lookup"><span data-stu-id="a695c-106">The `sql:is-constant` annotation can be specified on an element that does not have any attributes.</span></span> <span data-ttu-id="a695c-107">Se ela for especificada em um elemento com o valor true (ou 1), esse elemento não será mapeado para o banco de dados, mas ainda aparecerá no documento XML.</span><span class="sxs-lookup"><span data-stu-id="a695c-107">If it is specified on an element with the value true (or 1), that element is not mapped to the database but still appears in the XML document.</span></span>  
  
 <span data-ttu-id="a695c-108">A anotação `sql:is-constant` pode ser usada para:</span><span class="sxs-lookup"><span data-stu-id="a695c-108">The `sql:is-constant` annotation can be used for:</span></span>  
  
-   <span data-ttu-id="a695c-109">Adicionar um elemento de nível superior ao documento XML.</span><span class="sxs-lookup"><span data-stu-id="a695c-109">Adding a top-level element to the XML document.</span></span> <span data-ttu-id="a695c-110">XML requer um único elemento de nível superior (elemento root) para o documento.</span><span class="sxs-lookup"><span data-stu-id="a695c-110">XML requires a single top-level element (root element) for the document.</span></span>  
  
-   <span data-ttu-id="a695c-111">Criando elementos de contêiner, como um **\<Orders>** elemento que encapsula todos os pedidos.</span><span class="sxs-lookup"><span data-stu-id="a695c-111">Creating container elements, such as an **\<Orders>** element that wraps all orders.</span></span>  
  
 <span data-ttu-id="a695c-112">A `sql:is-constant` anotação pode ser adicionada a um **\<complexType>** elemento.</span><span class="sxs-lookup"><span data-stu-id="a695c-112">The `sql:is-constant` annotation can be added to a **\<complexType>** element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="a695c-113">Exemplos</span><span class="sxs-lookup"><span data-stu-id="a695c-113">Examples</span></span>  
 <span data-ttu-id="a695c-114">Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="a695c-114">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="a695c-115">Para obter mais informações, consulte [Requirements for running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="a695c-115">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqlis-constant-to-add-a-container-element"></a><span data-ttu-id="a695c-116">a.</span><span class="sxs-lookup"><span data-stu-id="a695c-116">A.</span></span> <span data-ttu-id="a695c-117">Especificando sql:is-constant para adicionar um elemento do contêiner</span><span class="sxs-lookup"><span data-stu-id="a695c-117">Specifying sql:is-constant to add a container element</span></span>  
 <span data-ttu-id="a695c-118">Neste esquema XSD anotado, **\<CustomerOrders>** é definido como um elemento constante, especificando o `sql:is-constant` atributo com um valor de 1.</span><span class="sxs-lookup"><span data-stu-id="a695c-118">In this annotated XSD schema, **\<CustomerOrders>** is defined as a constant element by specifying the `sql:is-constant` attribute with a value of 1.</span></span> <span data-ttu-id="a695c-119">Portanto, o **\<CustomerOrders>** não é mapeado para nenhuma tabela ou coluna de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="a695c-119">Therefore, **\<CustomerOrders>** is not mapped to any database table or column.</span></span> <span data-ttu-id="a695c-120">Esse elemento Constant consiste nos **\<Order>** elementos filho.</span><span class="sxs-lookup"><span data-stu-id="a695c-120">This constant element consists of the **\<Order>** child elements.</span></span>  
  
 <span data-ttu-id="a695c-121">Embora o não **\<CustomerOrders>** mapeie para nenhuma tabela ou coluna de banco de dados, ele ainda aparece no XML resultante como um elemento de contêiner que contém os **\<Order>** elementos filho.</span><span class="sxs-lookup"><span data-stu-id="a695c-121">Although **\<CustomerOrders>** does not map to any database table or column, it still appears in the resulting XML as a container element containing the **\<Order>** child elements.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
        parent="Sales.Customer"  
        parent-key="CustomerID"  
        child="Sales.SalesOrderHeader"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="CustomerOrders" sql:is-constant="1" >  
          <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"  
                           sql:relationship="CustOrders"   
                           maxOccurs="unbounded" >  
                <xsd:complexType>  
                   <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                   <xsd:attribute name="OrderDate" type="xsd:date" />  
                   <xsd:attribute name="CustomerID" type="xsd:string" />  
                </xsd:complexType>  
              </xsd:element>  
            </xsd:sequence>  
           </xsd:complexType>  
          </xsd:element>  
         </xsd:sequence>  
          <xsd:attribute name="CustomerID" type="xsd:string" />  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="a695c-122">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="a695c-122">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="a695c-123">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="a695c-123">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="a695c-124">Salve o arquivo como isConstant.xml.</span><span class="sxs-lookup"><span data-stu-id="a695c-124">Save the file as isConstant.xml.</span></span>  
  
2.  <span data-ttu-id="a695c-125">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="a695c-125">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="a695c-126">Salve o arquivo como isConstantT.xml no mesmo diretório onde você salvou isConstant.xml.</span><span class="sxs-lookup"><span data-stu-id="a695c-126">Save the file as isConstantT.xml in the same directory where you saved isConstant.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="isConstant.xml">  
            Customer[@CustomerID=1]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="a695c-127">O caminho de diretório especificado para o esquema de mapeamento (isConstant.xml) é relativo ao diretório onde o modelo está salvo.</span><span class="sxs-lookup"><span data-stu-id="a695c-127">The directory path specified for the mapping schema (isConstant.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="a695c-128">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="a695c-128">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\isConstant.xml"  
    ```  
  
3.  <span data-ttu-id="a695c-129">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="a695c-129">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="a695c-130">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="a695c-130">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="a695c-131">Este é o conjunto de resultados parcial:</span><span class="sxs-lookup"><span data-stu-id="a695c-131">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
<Customer CustomerID="1">   
  <CustomerOrders>   
    <Order SalesOrderID="43860" OrderDate="2001-08-01" CustomerID="1" />   
    <Order SalesOrderID="44501" OrderDate="2001-11-01" CustomerID="1" />   
    <Order SalesOrderID="45283" OrderDate="2002-02-01" CustomerID="1" />   
    <Order SalesOrderID="46042" OrderDate="2002-05-01" CustomerID="1" />   
    ...  
  </CustomerOrders>   
</Customer>   
</ROOT>  
```  
  
  
