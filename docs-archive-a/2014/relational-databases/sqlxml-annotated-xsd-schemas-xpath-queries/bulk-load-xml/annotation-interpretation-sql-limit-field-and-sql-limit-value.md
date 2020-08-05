---
title: 'SQL: limit-field e SQL: limit-value (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- limiting values [SQLXML]
- limit-value annotation
- limit-field annotation
- sql:limit-field
- sql:limit-value
- filtering [SQLXML]
ms.assetid: 402c21cf-9566-463f-a928-f94270c11db3
author: rothja
ms.author: jroth
ms.openlocfilehash: a6d0383aece7a2bafa5d21b76d0c4da9cb057984
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573888"
---
# <a name="sqllimit-field-and-sqllimit-value-sqlxml-40"></a><span data-ttu-id="1996f-102">sql:limit-field e sql:limit-value (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="1996f-102">sql:limit-field and sql:limit-value (SQLXML 4.0)</span></span>
  <span data-ttu-id="1996f-103">O XML Bulk Load processa as anotações `sql:limit-field` e `sql:limit-value` por suas definições.</span><span class="sxs-lookup"><span data-stu-id="1996f-103">XML Bulk Load processes the `sql:limit-field` and `sql:limit-value` annotations per their definition.</span></span> <span data-ttu-id="1996f-104">Para obter mais informações, consulte [filtrando valores usando SQL: limit-field e SQL: limit-value &#40;SQLXML 4,0&#41;](annotation-interpretation-sql-limit-field-and-sql-limit-value.md).</span><span class="sxs-lookup"><span data-stu-id="1996f-104">For more information, see [Filtering Values Using sql:limit-field and sql:limit-value &#40;SQLXML 4.0&#41;](annotation-interpretation-sql-limit-field-and-sql-limit-value.md).</span></span>  
  
 <span data-ttu-id="1996f-105">Por exemplo, suponha que um banco de dados contenha as seguintes tabelas:</span><span class="sxs-lookup"><span data-stu-id="1996f-105">For example, suppose a database contains the following tables:</span></span>  
  
-   <span data-ttu-id="1996f-106">Customer (CustomerID, CompanyName)</span><span class="sxs-lookup"><span data-stu-id="1996f-106">Customer (CustomerID, CompanyName)</span></span>  
  
-   <span data-ttu-id="1996f-107">Addresses (CustomerID, StreetAddress, AddressType)</span><span class="sxs-lookup"><span data-stu-id="1996f-107">Addresses (CustomerID, StreetAddress, AddressType)</span></span>  
  
 <span data-ttu-id="1996f-108">Um cliente pode ter muitos endereços e cada endereço pode ter um tipo de endereço associado a ele (por exemplo, um endereço para entrega ou para cobrança.</span><span class="sxs-lookup"><span data-stu-id="1996f-108">A customer can have many addresses, and each address has an address type associated with it (for example, a shipping address or a billing address).</span></span>  
  
 <span data-ttu-id="1996f-109">Agora considere esta exibição XML dessas tabelas como especificado no seguinte esquema XSD anotado:</span><span class="sxs-lookup"><span data-stu-id="1996f-109">Now consider this XML view of these tables as specified in the following annotated XSD schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustAddr"  
        parent="Customer"  
        parent-key="CustomerID"  
        child="Address"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Customer" >  
   <xsd:complexType>  
        <xsd:attribute name="CustomerID"   type="xsd:int" />   
        <xsd:attribute name="CompanyName"  type="xsd:string" />  
        <xsd:attribute name="BillTo"   
                       type="xsd:string"   
                       sql:relation="Address"   
                       sql:field="StreetAddress"  
                       sql:limit-field="AddressType"  
                       sql:limit-value="billing"  
                       sql:relationship="CustAddr" >  
        </xsd:attribute>  
        <xsd:attribute name="ShipTo"   
                       type="xsd:string"   
                       sql:relation="Address"   
                       sql:field="StreetAddress"  
                       sql:limit-field="AddressType"  
                       sql:limit-value="shipping"  
                       sql:relationship="CustAddr" >  
        </xsd:attribute>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="1996f-110">Após o recebimento desse esquema e dos dados XML, o XML Bulk Load insere o valor especificado para o atributo BillTo na coluna StreetAddress da tabela CustAddress junto com o valor "billing" da coluna AddressType.</span><span class="sxs-lookup"><span data-stu-id="1996f-110">Upon receiving this schema and XML data, XML Bulk Load inserts the value that is specified for the BillTo attribute into the StreetAddress column of the CustAddress table along with the "billing" value for the AddressType column.</span></span>  
  
 <span data-ttu-id="1996f-111">De modo semelhante, o XML Bulk Load insere o valor especificado para o atributo ShipTo na coluna StreetAddress junto com o valor "shipping" na coluna AddressType.</span><span class="sxs-lookup"><span data-stu-id="1996f-111">Similarly, XML Bulk Load inserts the value that is specified for the ShipTo attribute into the StreetAddress column along with the "shipping" value in the AddressType column.</span></span>  
  
### <a name="to-test-a-working-sample"></a><span data-ttu-id="1996f-112">Para testar um exemplo de funcionamento</span><span class="sxs-lookup"><span data-stu-id="1996f-112">To test a working sample</span></span>  
  
1.  <span data-ttu-id="1996f-113">Salve o esquema fornecido neste exemplo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="1996f-113">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
2.  <span data-ttu-id="1996f-114">Crie estas tabelas:</span><span class="sxs-lookup"><span data-stu-id="1996f-114">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Customer(  
                     CustomerID     int         PRIMARY KEY,  
                     CompanyName    varchar(20) NOT NULL)  
    GO  
    CREATE TABLE Address(  
                      CustomerID     int        FOREIGN KEY REFERENCES   
                                                 Customer(CustomerID),   
                      StreetAddress  varchar(50),  
                      AddressType    varchar(10))  
    GO  
    ```  
  
3.  <span data-ttu-id="1996f-115">Salve os dados de exemplo a seguir como SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="1996f-115">Save the following sample data as SampleXMLData.xml:</span></span>  
  
    ```  
    <Customer CustomerID="1111" CompanyName="Sean Chai" City="NY"   
                 BillTo="111 Maple (Billing) "   
                 ShipTo="111 Maple (Shipping)" />  
    <Customer CustomerID="1112" CompanyName="Dont Know" City="LA"   
                 BillTo="222 Spruce (Billing)"   
                 ShipTo="222 Spruce (Shipping)" />  
    ```  
  
4.  <span data-ttu-id="1996f-116">Para executar o XML Bulk Load, salve e execute este exemplo do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) como Sample.vbs:</span><span class="sxs-lookup"><span data-stu-id="1996f-116">To execute XML Bulk Load, save and execute this [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example as Sample.vbs:</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.XMLFragment = True  
    objBL.CheckConstraints=True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
 <span data-ttu-id="1996f-117">Este é o esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="1996f-117">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  
<ElementType name="Customer" sql:relation="Customer" >  
    <AttributeType name="CustomerID" />  
    <AttributeType name="CompanyName" />  
    <AttributeType name="BillTo" />  
    <AttributeType name="ShipTo" />  
  
    <attribute type="CustomerID" />  
    <attribute type="CompanyName" />  
    <attribute type="BillTo"   
                sql:limit-field="AddressType"  
                sql:limit-value="billing"  
                sql:field="StreetAddress"  
                sql:relation="Address" >  
                <sql:relationship   
                        key="CustomerID"  
                        key-relation="Customer"  
                        foreign-relation="Address"  
                        foreign-key="CustomerID" />  
    </attribute>  
    <attribute type="ShipTo"   
                sql:limit-field="AddressType"  
                sql:limit-value="shipping"  
                sql:field="StreetAddress"  
                sql:relation="Address" >  
                <sql:relationship   
                     key="CustomerID"  
                     key-relation="Customer"  
                     foreign-relation="Address"  
                     foreign-key="CustomerID" />  
    </attribute>  
</ElementType>  
</Schema>  
```  
  
  
