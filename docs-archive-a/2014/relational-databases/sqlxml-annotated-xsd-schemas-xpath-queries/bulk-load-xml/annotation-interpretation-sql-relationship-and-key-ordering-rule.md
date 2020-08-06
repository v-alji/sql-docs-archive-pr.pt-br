---
title: 'SQL: relationship e a regra de ordenação de chave (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- sql:relationship
- key ordering rules [SQLXML]
- relationship annotation
ms.assetid: 914cb152-09f5-4b08-b35d-71940e4e9986
author: rothja
ms.author: jroth
ms.openlocfilehash: 716e911676dc81539fc641bee139d92e29dc49db
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575759"
---
# <a name="sqlrelationship-and-the-key-ordering-rule-sqlxml-40"></a><span data-ttu-id="403f2-102">sql:relationship e a Regra de Ordenação de Chaves (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="403f2-102">sql:relationship and the Key Ordering Rule (SQLXML 4.0)</span></span>
  <span data-ttu-id="403f2-103">Como o XML Bulk Load gera registro à medida que seus nós entram no escopo e envia esses registros para o Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] à medida que seus nós saem do escopo, os dados do registro devem estar presentes no escopo do nó.</span><span class="sxs-lookup"><span data-stu-id="403f2-103">Because XML Bulk Load generates records as their nodes enter into scope and sends those records to Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] as their nodes exit scope, the data for the record must be present within the scope of the node.</span></span>  
  
 <span data-ttu-id="403f2-104">Considere o seguinte esquema XSD, no qual a relação de um para muitos entre **\<Customer>** elementos e **\<Order>** (um cliente pode inserir muitos pedidos) é especificada usando o `<sql:relationship>` elemento:</span><span class="sxs-lookup"><span data-stu-id="403f2-104">Consider the following XSD schema, in which the one-to-many relationship between **\<Customer>** and **\<Order>** elements (one customer can place many orders) is specified by using the `<sql:relationship>` element:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"<>   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustCustOrder"  
          parent="Cust"  
          parent-key="CustomerID"  
          child="CustOrder"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customers" sql:relation="Cust" >  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="CustomerID"  type="xsd:integer" />  
       <xsd:element name="CompanyName" type="xsd:string" />  
       <xsd:element name="City"        type="xsd:string" />  
       <xsd:element name="Order"   
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder" >  
         <xsd:complexType>  
          <xsd:attribute name="OrderID" type="xsd:integer" />  
         </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="403f2-105">Como o **\<Customer>** nó de elemento entra no escopo, o carregamento em massa de XML gera um registro de cliente.</span><span class="sxs-lookup"><span data-stu-id="403f2-105">As the **\<Customer>** element node enters into scope, XML Bulk Load generates a customer record.</span></span> <span data-ttu-id="403f2-106">Esse registro permanece até leituras de carregamento em massa de XML **\</Customer>** .</span><span class="sxs-lookup"><span data-stu-id="403f2-106">This record stays until XML Bulk Load reads **\</Customer>**.</span></span> <span data-ttu-id="403f2-107">Ao processar o **\<Order>** nó do elemento, o carregamento em massa do XML usa `<sql:relationship>` para obter o valor da coluna de chave estrangeira CustomerID da tabela CustOrder do **\<Customer>** elemento pai, porque o **\<Order>** elemento não especifica o atributo **CustomerID** .</span><span class="sxs-lookup"><span data-stu-id="403f2-107">In processing the **\<Order>** element node, XML Bulk Load uses `<sql:relationship>` to obtain the value of the CustomerID foreign key column of the CustOrder table from the **\<Customer>** parent element, because the **\<Order>** element does not specify the **CustomerID** attribute.</span></span> <span data-ttu-id="403f2-108">Isso significa que, ao definir o **\<Customer>** elemento, você deve especificar o atributo **CustomerID** no esquema antes de especificar `<sql:relationship>` .</span><span class="sxs-lookup"><span data-stu-id="403f2-108">This means that in defining the **\<Customer>** element, you must specify the **CustomerID** attribute in the schema before you specify `<sql:relationship>`.</span></span> <span data-ttu-id="403f2-109">Caso contrário, quando um **\<Order>** elemento entra no escopo, o carregamento em massa de XML gera um registro para a tabela CustOrder e, quando o carregamento em massa de XML atinge a **\</Order>** marca de fim, ele envia o registro para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] sem o valor da coluna de chave estrangeira CustomerID.</span><span class="sxs-lookup"><span data-stu-id="403f2-109">Otherwise, when an **\<Order>** element enters into scope, XML Bulk Load generates a record for the CustOrder table, and when the XML Bulk Load reaches the **\</Order>** end tag, it sends the record to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] without the CustomerID foreign key column value.</span></span>  
  
 <span data-ttu-id="403f2-110">Salve o esquema fornecido neste exemplo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="403f2-110">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
### <a name="to-test-a-working-sample"></a><span data-ttu-id="403f2-111">Para testar um exemplo de funcionamento</span><span class="sxs-lookup"><span data-stu-id="403f2-111">To test a working sample</span></span>  
  
1.  <span data-ttu-id="403f2-112">Crie estas tabelas:</span><span class="sxs-lookup"><span data-stu-id="403f2-112">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
                  CustomerID     int          PRIMARY KEY,  
               CompanyName    varchar(20)  NOT NULL,  
                  City           varchar(20)  DEFAULT 'Seattle')  
    GO  
    CREATE TABLE CustOrder (  
                  OrderID        varchar(10) PRIMARY KEY,  
               CustomerID     int         FOREIGN KEY REFERENCES                                          Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="403f2-113">Salve os dados de exemplo a seguir como SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="403f2-113">Save the following sample data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>    
      <Customers>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City>NY</City>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
        <CustomerID>1111</CustomerID>  
      </Customers>  
      <Customers>  
        <CompanyName>Toms Spezialitten</CompanyName>  
         <City>LA</City>    
        <Order OrderID="3" />  
        <CustomerID>1112</CustomerID>  
      </Customers>  
      <Customers>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
        <CustomerID>1113</CustomerID>  
      </Customers>  
    </ROOT>  
    ```  
  
3.  <span data-ttu-id="403f2-114">Para executar o XML Bulk Load, salve e execute o seguinte exemplo do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) como MySample.vbs:</span><span class="sxs-lookup"><span data-stu-id="403f2-114">To execute XML Bulk Load, save and execute the following [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example as MySample.vbs:</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Transaction=True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
     <span data-ttu-id="403f2-115">O resultado é que o XML Bulk Load insere um valor NULL na coluna de chave estrangeira CustomerID da tabela CustOrder.</span><span class="sxs-lookup"><span data-stu-id="403f2-115">The result is that XML Bulk Load inserts a NULL value in the CustomerID foreign key column of the CustOrder table.</span></span> <span data-ttu-id="403f2-116">Se você revisar os dados de exemplo XML para que o **\<CustomerID>** elemento filho apareça antes do **\<Order>** elemento filho, obterá o resultado esperado: o carregamento em massa de XML insere o valor de chave estrangeira especificado na coluna.</span><span class="sxs-lookup"><span data-stu-id="403f2-116">If you revise the XML sample data so that the **\<CustomerID>** child element appears before the **\<Order>** child element, you get the expected result: XML Bulk Load inserts the specified foreign key value into the column.</span></span>  
  
 <span data-ttu-id="403f2-117">Este é o esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="403f2-117">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
   <ElementType name="CustomerID"  />  
   <ElementType name="CompanyName" />  
   <ElementType name="City"        />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust" >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
                 <sql:relationship  
                        key-relation    ="Cust"  
                        key             ="CustomerID"  
                        foreign-key     ="CustomerID"  
                        foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
</Schema>  
```  
  
  