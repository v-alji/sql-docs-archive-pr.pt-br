---
title: 'Identificando colunas de chave usando SQL: Key-Fields (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- nesting XML results
- proper nesting in results [SQLXML]
- sql:key-fields
- XSD schemas [SQLXML], key columns
- identifying key columns [SQLXML]
- annotated XSD schemas, key columns
- key columns [SQLXML]
- relationships [SQLXML], key columns
- hierarchical relationships [SQLXML]
- key-fields annotation
ms.assetid: 1a5ad868-8602-45c4-913d-6fbb837eebb0
author: rothja
ms.author: jroth
ms.openlocfilehash: 0ab12b34874a54bad2e08a96d08ebd0cc994f946
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685478"
---
# <a name="identifying-key-columns-using-sqlkey-fields-sqlxml-40"></a><span data-ttu-id="14332-102">Identificando colunas de chave usando campos sql:key (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="14332-102">Identifying Key Columns Using sql:key-fields (SQLXML 4.0)</span></span>
  <span data-ttu-id="14332-103">Quando uma consulta XPath é especificada em um esquema XSD, as informações de chave são necessárias, na maioria das vezes, para obter o aninhamento adequado no resultado.</span><span class="sxs-lookup"><span data-stu-id="14332-103">When an XPath query is specified against an XSD schema, key information is required in most cases to obtain proper nesting in the result.</span></span> <span data-ttu-id="14332-104">Especificar a anotação `sql:key-fields` é uma forma de assegurar que a hierarquia apropriada seja gerada.</span><span class="sxs-lookup"><span data-stu-id="14332-104">Specifying the `sql:key-fields` annotation is a way of ensuring that the appropriate hierarchy is generated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="14332-105">Para assegurar o aninhamento adequado, é recomendável especificar `sql:key-fields` para elementos que são mapeados para tabelas.</span><span class="sxs-lookup"><span data-stu-id="14332-105">To ensure proper nesting, it is recommended that you specify `sql:key-fields` for elements that map to tables.</span></span> <span data-ttu-id="14332-106">O XML gerado é sensível à ordenação do conjunto de resultados subjacente.</span><span class="sxs-lookup"><span data-stu-id="14332-106">The XML produced is sensitive to the ordering of the underlying result set.</span></span> <span data-ttu-id="14332-107">Se `sql:key-fields` não for especificada, o XML gerado poderá não ser formado corretamente.</span><span class="sxs-lookup"><span data-stu-id="14332-107">If `sql:key-fields` is not specified, the XML generated might not be formed properly.</span></span>  
  
 <span data-ttu-id="14332-108">O valor de `sql:key-fields` identifica as colunas que identificam as linhas de forma exclusiva na relação.</span><span class="sxs-lookup"><span data-stu-id="14332-108">The value of `sql:key-fields` identifies the column(s) that uniquely identify the rows in the relation.</span></span> <span data-ttu-id="14332-109">Se mais de uma coluna for necessária para identificar uma linha de forma exclusiva, os valores de coluna serão delimitados por espaços.</span><span class="sxs-lookup"><span data-stu-id="14332-109">If more than one column is required to uniquely identify a row, the column values are delimited by spaces.</span></span>  
  
 <span data-ttu-id="14332-110">Você deve usar a `sql:key-fields` anotação quando um elemento contiver um **\<sql:relationship>** que esteja definido entre o elemento e um elemento filho, mas não forneça a chave primária da tabela especificada no elemento pai.</span><span class="sxs-lookup"><span data-stu-id="14332-110">You must use the `sql:key-fields` annotation when an element contains a **\<sql:relationship>** that is defined between the element and a child element but does not provide the primary key of the table that is specified in the parent element.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="14332-111">Exemplos</span><span class="sxs-lookup"><span data-stu-id="14332-111">Examples</span></span>  
 <span data-ttu-id="14332-112">Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="14332-112">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="14332-113">Para obter mais informações, consulte [Requirements for running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="14332-113">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-producing-the-appropriate-nesting-when-sqlrelationship-does-not-provide-sufficient-information"></a><span data-ttu-id="14332-114">a.</span><span class="sxs-lookup"><span data-stu-id="14332-114">A.</span></span> <span data-ttu-id="14332-115">Produzindo o aninhamento apropriado quando o não \<sql:relationship> fornece informações suficientes</span><span class="sxs-lookup"><span data-stu-id="14332-115">Producing the appropriate nesting when \<sql:relationship> does not provide sufficient information</span></span>  
 <span data-ttu-id="14332-116">Esse exemplo mostra onde `sql:key-fields` deve ser especificada.</span><span class="sxs-lookup"><span data-stu-id="14332-116">This example shows where `sql:key-fields` must be specified.</span></span>  
  
 <span data-ttu-id="14332-117">Considere o esquema a seguir.</span><span class="sxs-lookup"><span data-stu-id="14332-117">Consider the following schema.</span></span> <span data-ttu-id="14332-118">O esquema especifica uma hierarquia entre os **\<Order>** **\<Customer>** elementos e nos quais o **\<Order>** elemento é o pai e o **\<Customer>** elemento é um filho.</span><span class="sxs-lookup"><span data-stu-id="14332-118">The schema specifies a hierarchy between the **\<Order>** and **\<Customer>** elements in which the **\<Order>** element is the parent and the **\<Customer>** element is a child.</span></span>  
  
 <span data-ttu-id="14332-119">A **\<sql:relationship>** marca é usada para especificar a relação pai-filho.</span><span class="sxs-lookup"><span data-stu-id="14332-119">The **\<sql:relationship>** tag is used to specify the parent-child relationship.</span></span> <span data-ttu-id="14332-120">Ela identifica CustomerID na tabela Sales.SalesOrderHeader como a chave pai que faz referência à chave filho CustomerID na tabela Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="14332-120">It identifies CustomerID in the Sales.SalesOrderHeader table as the parent key that refers to the CustomerID child key in the Sales.Customer table.</span></span> <span data-ttu-id="14332-121">As informações fornecidas no **\<sql:relationship>** não são suficientes para identificar exclusivamente as linhas na tabela pai (Sales. SalesOrderHeader).</span><span class="sxs-lookup"><span data-stu-id="14332-121">The information provided in **\<sql:relationship>** is not sufficient to uniquely identify rows in the parent table (Sales.SalesOrderHeader).</span></span> <span data-ttu-id="14332-122">Portanto, sem a anotação `sql:key-fields`, a hierarquia gerada é imprecisa.</span><span class="sxs-lookup"><span data-stu-id="14332-122">Therefore, without the `sql:key-fields` annotation, the hierarchy that is generated is inaccurate.</span></span>  
  
 <span data-ttu-id="14332-123">Com `sql:key-fields` o especificado em **\<Order>** , a anotação identifica exclusivamente as linhas na tabela pai (tabelas Sales. SalesOrderHeader) e seus elementos filho aparecem abaixo de seu pai.</span><span class="sxs-lookup"><span data-stu-id="14332-123">With `sql:key-fields` specified on **\<Order>**, the annotation uniquely identifies the rows in the parent (Sales.SalesOrderHeader table), and its child elements appear below its parent.</span></span>  
  
 <span data-ttu-id="14332-124">Este é o esquema:</span><span class="sxs-lookup"><span data-stu-id="14332-124">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrdCust"  
        parent="Sales.SalesOrderHeader"  
        parent-key="CustomerID"  
        child="Sales.Customer"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"   
               sql:key-fields="SalesOrderID">  
   <xsd:complexType>  
     <xsd:sequence>  
     <xsd:element name="Customer" sql:relation="Sales.Customer"   
                       sql:relationship="OrdCust"  >  
       <xsd:complexType>  
         <xsd:attribute name="CustID" sql:field="CustomerID" />  
         <xsd:attribute name="SoldBy" sql:field="SalesPersonID" />  
       </xsd:complexType>  
     </xsd:element>  
     </xsd:sequence>  
     <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
     <xsd:attribute name= "CustomerID" type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="14332-125">Para criar um exemplo de funcionamento deste esquema</span><span class="sxs-lookup"><span data-stu-id="14332-125">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="14332-126">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="14332-126">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="14332-127">Salve o arquivo como KeyFields1.xml.</span><span class="sxs-lookup"><span data-stu-id="14332-127">Save the file as KeyFields1.xml.</span></span>  
  
2.  <span data-ttu-id="14332-128">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="14332-128">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="14332-129">Salve o arquivo como KeyFields1T.xml no mesmo diretório em que você salvou KeyFields1.xml.</span><span class="sxs-lookup"><span data-stu-id="14332-129">Save the file as KeyFields1T.xml in the same directory where you saved KeyFields1.xml.</span></span> <span data-ttu-id="14332-130">A consulta XPath no modelo retorna todos os **\<Order>** elementos com um CustomerID de menos de 3.</span><span class="sxs-lookup"><span data-stu-id="14332-130">The XPath query in the template returns all the **\<Order>** elements with a CustomerID of less than 3.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="KeyFields1.xml">  
            /Order[@CustomerID < 3]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="14332-131">O caminho de diretório especificado para o esquema de mapeamento (KeyFields1.xml) é relativo ao diretório onde o modelo está salvo.</span><span class="sxs-lookup"><span data-stu-id="14332-131">The directory path specified for the mapping schema (KeyFields1.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="14332-132">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="14332-132">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\KeyFields1.xml"  
    ```  
  
3.  <span data-ttu-id="14332-133">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="14332-133">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="14332-134">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="14332-134">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="14332-135">Este é o conjunto de resultados parcial:</span><span class="sxs-lookup"><span data-stu-id="14332-135">This is the partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
    <Order SalesOrderID="43860" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    <Order SalesOrderID="44501" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    <Order SalesOrderID="45283" CustomerID="1">  
       <Customer CustID="1" SoldBy="280"/>  
    </Order>  
    .....  
</ROOT>  
```  
  
### <a name="b-specifying-sqlkey-fields-to-produce-proper-nesting-in-the-result"></a><span data-ttu-id="14332-136">B.</span><span class="sxs-lookup"><span data-stu-id="14332-136">B.</span></span> <span data-ttu-id="14332-137">Especificar sql:key-fields para produzir o aninhamento adequado no resultado</span><span class="sxs-lookup"><span data-stu-id="14332-137">Specifying sql:key-fields to produce proper nesting in the result</span></span>  
 <span data-ttu-id="14332-138">No esquema a seguir, não há nenhuma hierarquia especificada usando **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="14332-138">In the following schema, there is no hierarchy specified using **\<sql:relationship>**.</span></span> <span data-ttu-id="14332-139">O esquema ainda requer que a anotação `sql:key-fields` seja especificada para identificar os funcionários de forma exclusiva na tabela HumanResources.Employee.</span><span class="sxs-lookup"><span data-stu-id="14332-139">The schema still requires specifying the `sql:key-fields` annotation to uniquely identify employees in the HumanResources.Employee table.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="HumanResources.Employee" sql:key-fields="EmployeeID" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Title">  
          <xsd:complexType>  
            <xsd:simpleContent>  
              <xsd:extension base="xsd:string">  
                 <xsd:attribute name="EmployeeID" type="xsd:integer" />  
              </xsd:extension>  
            </xsd:simpleContent>  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
   </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-create-a-working-sample-of-this-schema"></a><span data-ttu-id="14332-140">Para criar um exemplo de funcionamento deste esquema</span><span class="sxs-lookup"><span data-stu-id="14332-140">To create a working sample of this schema</span></span>  
  
1.  <span data-ttu-id="14332-141">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="14332-141">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="14332-142">Salve o arquivo como KeyFields2.xml.</span><span class="sxs-lookup"><span data-stu-id="14332-142">Save the file as KeyFields2.xml.</span></span>  
  
2.  <span data-ttu-id="14332-143">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="14332-143">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="14332-144">Salve o arquivo como KeyFields2T.xml no mesmo diretório em que você salvou KeyFields2.xml.</span><span class="sxs-lookup"><span data-stu-id="14332-144">Save the file as KeyFields2T.xml in the same directory where you saved KeyFields2.xml.</span></span> <span data-ttu-id="14332-145">A consulta XPath no modelo retorna todos os **\<HumanResources.Employee>** elementos:</span><span class="sxs-lookup"><span data-stu-id="14332-145">The XPath query in the template returns all the **\<HumanResources.Employee>** elements:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="KeyFields2.xml">  
        /HumanResources.Employee  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="14332-146">O caminho de diretório especificado para o esquema de mapeamento (KeyFields2.xml) é relativo ao diretório onde o modelo está salvo.</span><span class="sxs-lookup"><span data-stu-id="14332-146">The directory path specified for the mapping schema (KeyFields2.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="14332-147">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="14332-147">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\KeyFields2.xml"  
    ```  
  
3.  <span data-ttu-id="14332-148">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="14332-148">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="14332-149">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="14332-149">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="14332-150">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="14332-150">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <HumanResources.Employee>  
    <Title EmployeeID="1">Production Technician - WC60</Title>   
  </HumanResources.Employee>  
  <HumanResources.Employee>  
    <Title EmployeeID="2">Marketing Assistant</Title>   
  </HumanResources.Employee>  
  <HumanResources.Employee>  
    <Title EmployeeID="3">Engineering Manager</Title>   
  </HumanResources.Employee>  
  ...  
</ROOT>  
```  
  
  
