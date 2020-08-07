---
title: Especificando um namespace de destino usando o atributo targetNamespace (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- namespaces [SQLXML], annotated XSD schemas
- targetNamespace attribute
- XSD schemas [SQLXML], target namespaces
- annotated XSD schemas, target namespaces
- xsd:targetNamespace
- attributeFormDefault attribute
- elementFormDefault attribute
- target namespaces [SQLXML]
ms.assetid: f3df9877-6672-4444-8245-2670063c9310
author: rothja
ms.author: jroth
ms.openlocfilehash: 823bcbf7f4906a2e1d2ced1ff58b681c0ca41a8b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582371"
---
# <a name="specifying-a-target-namespace-using-the-targetnamespace-attribute-sqlxml-40"></a><span data-ttu-id="288bc-102">Especificando um namespace de destino usando o atributo targetNamespace (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="288bc-102">Specifying a Target Namespace Using the targetNamespace Attribute (SQLXML 4.0)</span></span>
  <span data-ttu-id="288bc-103">Ao escrever esquemas XSD, você pode usar o atributo de XSD **targetNamespace** para especificar um namespace de destino.</span><span class="sxs-lookup"><span data-stu-id="288bc-103">In writing XSD schemas, you can use the XSD **targetNamespace** attribute to specify a target namespace.</span></span> <span data-ttu-id="288bc-104">Este tópico descreve como os atributos de **targetNamespace**, **elementFormDefault**e **attributeFormDefault** do xsd funcionam, como eles afetam a instância XML gerada e como as consultas XPath são especificadas com namespaces.</span><span class="sxs-lookup"><span data-stu-id="288bc-104">This topic describes how the XSD **targetNamespace**, **elementFormDefault**, and **attributeFormDefault** attributes work, how they affect the XML instance that is generated, and how XPath queries are specified with namespaces.</span></span>  
  
 <span data-ttu-id="288bc-105">Você pode usar o atributo **xsd: targetNamespace** para posicionar elementos e atributos do namespace padrão em um namespace diferente.</span><span class="sxs-lookup"><span data-stu-id="288bc-105">You can use the **xsd:targetNamespace** attribute to place elements and attributes from the default namespace into a different namespace.</span></span> <span data-ttu-id="288bc-106">Você também pode especificar se os elementos e atributos do esquema declarados localmente devem aparecer qualificados por um namespace, seja explicitamente, usando um prefixo, ou implicitamente, por padrão.</span><span class="sxs-lookup"><span data-stu-id="288bc-106">You can also specify whether the locally declared elements and attributes of the schema should appear qualified by a namespace, either explicitly by using a prefix or implicitly by default.</span></span> <span data-ttu-id="288bc-107">Você pode usar os atributos **elementFormDefault** e **attributeFormDefault** no **\<xsd:schema>** elemento para especificar globalmente a qualificação de elementos e atributos locais, ou pode usar o atributo **Form** para especificar elementos e atributos individuais separadamente.</span><span class="sxs-lookup"><span data-stu-id="288bc-107">You can use the **elementFormDefault** and **attributeFormDefault** attributes on the **\<xsd:schema>** element to globally specify the qualification of local elements and attributes, or you can use the **form** attribute to specify individual elements and attributes separately.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="288bc-108">Exemplos</span><span class="sxs-lookup"><span data-stu-id="288bc-108">Examples</span></span>  
 <span data-ttu-id="288bc-109">Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="288bc-109">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="288bc-110">Para obter mais informações, consulte [Requirements for running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="288bc-110">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-a-target-namespace"></a><span data-ttu-id="288bc-111">a.</span><span class="sxs-lookup"><span data-stu-id="288bc-111">A.</span></span> <span data-ttu-id="288bc-112">Especificando um namespace de destino</span><span class="sxs-lookup"><span data-stu-id="288bc-112">Specifying a target namespace</span></span>  
 <span data-ttu-id="288bc-113">O esquema XSD a seguir especifica um namespace de destino usando o atributo **xsd: targetNamespace** .</span><span class="sxs-lookup"><span data-stu-id="288bc-113">The following XSD schema specifies a target namespace by using the **xsd:targetNamespace** attribute.</span></span> <span data-ttu-id="288bc-114">O esquema também define os valores de atributo **elementFormDefault** e **attributeFormDefault** como **"unqualified"** (o valor padrão para esses atributos).</span><span class="sxs-lookup"><span data-stu-id="288bc-114">The schema also sets the **elementFormDefault** and **attributeFormDefault** attribute values to **"unqualified"** (the default value for these attributes).</span></span> <span data-ttu-id="288bc-115">Essa é uma declaração global e afeta todos os elementos locais ( **\<Order>** no esquema) e atributos (**CustomerID**, **ContactName**e **OrderID** no esquema).</span><span class="sxs-lookup"><span data-stu-id="288bc-115">This is a global declaration and affects all the local elements (**\<Order>** in the schema) and attributes (**CustomerID**, **ContactName**, and **OrderID** in the schema).</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
            xmlns:CO="urn:MyNamespace"   
            targetNamespace="urn:MyNamespace" >  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer"   
               sql:relation="Sales.Customer"   
               type="CO:CustomerType" />  
  
  <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                     sql:relationship="CustOrders"  
                     type="CO:OrderType" />  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
        <xsd:attribute name="SalesPersonID"  type="xsd:string" />  
  </xsd:complexType>  
  <xsd:complexType name="OrderType" >  
     <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
     <xsd:attribute name="CustomerID" type="xsd:string" />  
  </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="288bc-116">No esquema:</span><span class="sxs-lookup"><span data-stu-id="288bc-116">In the schema:</span></span>  
  
-   <span data-ttu-id="288bc-117">As declarações de tipo **CustomerType** e **ordertype** são globais e, portanto, são incluídas no namespace de destino do esquema.</span><span class="sxs-lookup"><span data-stu-id="288bc-117">The **CustomerType** and **OrderType** type declarations are global and, therefore, are included in the schema's target namespace.</span></span> <span data-ttu-id="288bc-118">Como resultado, quando esses tipos são referenciados na declaração do **\<Customer>** elemento e seu **\<Order>** elemento filho, é especificado um prefixo associado ao namespace de destino.</span><span class="sxs-lookup"><span data-stu-id="288bc-118">As a result, when these types are referenced in the declaration of **\<Customer>** element and its **\<Order>** child element, a prefix is specified that is associated with the target namespace.</span></span>  
  
-   <span data-ttu-id="288bc-119">O **\<Customer>** elemento também é incluído no namespace de destino do esquema porque ele é um elemento global no esquema.</span><span class="sxs-lookup"><span data-stu-id="288bc-119">The **\<Customer>** element is also included in the target namespace of the schema because it is a global element in the schema.</span></span>  
  
 <span data-ttu-id="288bc-120">Execute a consulta XPath a seguir no esquema:</span><span class="sxs-lookup"><span data-stu-id="288bc-120">Execute the following XPath query against the schema:</span></span>  
  
```  
(/CO:Customer[@CustomerID=1)   
```  
  
 <span data-ttu-id="288bc-121">A consulta de XPath gera este documento da instância (somente alguns pedidos são mostrados):</span><span class="sxs-lookup"><span data-stu-id="288bc-121">The XPath query generates this instance document (only a few of the orders are shown):</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <y0:Customer xmlns:y0="urn:MyNamespace"   
      CustomerID="ALFKI" ContactName="Maria Anders">  
        <Order CustomerID="ALFKI" OrderID="10643" />   
        <Order CustomerID="ALFKI" OrderID="10692" />   
        ...  
  </y0:Customer>  
  </ROOT>  
```  
  
 <span data-ttu-id="288bc-122">Este documento de instância define o namespace urn: MyNamespace e associa um prefixo (y0) a ele.</span><span class="sxs-lookup"><span data-stu-id="288bc-122">This instance document defines the urn:MyNamespace namespace and associates a prefix (y0) to it.</span></span> <span data-ttu-id="288bc-123">O prefixo é aplicado somente ao **\<Customer>** elemento global.</span><span class="sxs-lookup"><span data-stu-id="288bc-123">The prefix is applied only to the **\<Customer>** global element.</span></span> <span data-ttu-id="288bc-124">(O elemento é global porque está declarado como um filho do **\<xsd:schema>** elemento no esquema.)</span><span class="sxs-lookup"><span data-stu-id="288bc-124">(The element is global because it is declared as a child of **\<xsd:schema>** element in the schema.)</span></span>  
  
 <span data-ttu-id="288bc-125">O prefixo não é aplicado aos elementos e atributos locais porque o valor dos atributos **elementFormDefault** e **attributeFormDefault** está definido como **"unqualified"** no esquema.</span><span class="sxs-lookup"><span data-stu-id="288bc-125">The prefix is not applied to the local elements and attributes because the value of **elementFormDefault** and **attributeFormDefault** attributes is set to **"unqualified"** in the schema.</span></span> <span data-ttu-id="288bc-126">Observe que o **\<Order>** elemento é local porque sua declaração aparece como um filho do **\<complexType>** elemento que define o **\<CustomerType>** elemento.</span><span class="sxs-lookup"><span data-stu-id="288bc-126">Note that the **\<Order>** element is local because its declaration appears as a child of the **\<complexType>** element that defines the **\<CustomerType>** element.</span></span> <span data-ttu-id="288bc-127">Da mesma forma, os atributos (**CustomerID**, **OrderID**e **ContactName**) são locais, e não globais.</span><span class="sxs-lookup"><span data-stu-id="288bc-127">Similarly, the attributes (**CustomerID**, **OrderID**, and **ContactName**) are local, not global.</span></span>  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="288bc-128">Para criar um exemplo de funcionamento deste esquema</span><span class="sxs-lookup"><span data-stu-id="288bc-128">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="288bc-129">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="288bc-129">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="288bc-130">Salve o arquivo como target.NameSpace.xml.</span><span class="sxs-lookup"><span data-stu-id="288bc-130">Save the file as targetNameSpace.xml.</span></span>  
  
2.  <span data-ttu-id="288bc-131">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="288bc-131">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="288bc-132">Salve o arquivo como target.NameSpaceT.xml no mesmo diretório em que você salvou targetNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="288bc-132">Save the file as targetNameSpaceT.xml in the same directory where you saved targetNamespace.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="targetNamespace.xml"  
                       xmlns:CO="urn:MyNamespace" >  
        /CO:Customer[@CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="288bc-133">A consulta XPath no modelo retorna o **\<Customer>** elemento para o cliente com um CustomerID de 1.</span><span class="sxs-lookup"><span data-stu-id="288bc-133">The XPath query in the template returns the **\<Customer>** element for the customer with a CustomerID of 1.</span></span> <span data-ttu-id="288bc-134">Observe que a consulta XPath especifica o prefixo de namespace para o elemento na consulta e não para o atributo.</span><span class="sxs-lookup"><span data-stu-id="288bc-134">Note that the XPath query specifies the namespace prefix for the element in the query and not for the attribute.</span></span> <span data-ttu-id="288bc-135">(Não são qualificados atributos locais, como especificado no esquema.)</span><span class="sxs-lookup"><span data-stu-id="288bc-135">(Local attributes are not qualified, as specified in the schema.)</span></span>  
  
     <span data-ttu-id="288bc-136">O caminho de diretório especificado para o esquema de mapeamento (targetNamespace.xml) é relativo ao diretório onde o modelo está salvo.</span><span class="sxs-lookup"><span data-stu-id="288bc-136">The directory path specified for the mapping schema (targetNamespace.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="288bc-137">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="288bc-137">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\targetNamepsace.xml"  
    ```  
  
3.  <span data-ttu-id="288bc-138">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="288bc-138">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="288bc-139">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="288bc-139">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="288bc-140">Se o esquema especificar os atributos **elementFormDefault** e **attributeFormDefault** com o valor **"qualified"**, o documento de instância terá todos os elementos e atributos locais qualificados.</span><span class="sxs-lookup"><span data-stu-id="288bc-140">If the schema specifies **elementFormDefault** and **attributeFormDefault** attributes with value **"qualified"**, the instance document will have all of the local elements and attributes qualified.</span></span> <span data-ttu-id="288bc-141">Você pode alterar o esquema anterior para incluir esses atributos no **\<xsd:schema>** elemento e executar o modelo novamente.</span><span class="sxs-lookup"><span data-stu-id="288bc-141">You can change the previous schema to include these attributes in the **\<xsd:schema>** element and execute the template again.</span></span> <span data-ttu-id="288bc-142">Como os atributos agora são qualificados também na instância, a consulta XPath será alterada para incluir o prefixo de namespace.</span><span class="sxs-lookup"><span data-stu-id="288bc-142">Because the attributes are now also qualified in the instance, the XPath query will change to include the namespace prefix.</span></span>  
  
 <span data-ttu-id="288bc-143">Esta é a consulta XPath revisada:</span><span class="sxs-lookup"><span data-stu-id="288bc-143">This is the revised XPath query:</span></span>  
  
```  
/CO:Customer[@CO:CustomerID=1]  
```  
  
 <span data-ttu-id="288bc-144">Este é o documento XML retornado:</span><span class="sxs-lookup"><span data-stu-id="288bc-144">This is the XML document that is returned:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
   <y0:Customer xmlns:y0="urn:MyNamespace" CustomerID="1" SalesPersonID="280">  
      <Order SalesOrderID="43860" CustomerID="1" />   
      <Order SalesOrderID="44501" CustomerID="1" />   
      <Order SalesOrderID="45283" CustomerID="1" />   
      <Order SalesOrderID="46042" CustomerID="1" />   
   </y0:Customer>  
</ROOT>  
```  
  
  
