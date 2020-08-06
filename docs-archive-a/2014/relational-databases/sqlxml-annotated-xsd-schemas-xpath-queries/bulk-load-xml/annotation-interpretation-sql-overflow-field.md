---
title: 'SQL: overflow-field (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- overflow-field annotation
- unconsumed data
- overflow data [SQLXML]
- sql:overflow-field
ms.assetid: f005182b-6151-432d-ab22-3bc025742cd3
author: rothja
ms.author: jroth
ms.openlocfilehash: ea52eb642964844a03304d082632c2b7157f723b
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575761"
---
# <a name="sqloverflow-field-sqlxml-40"></a><span data-ttu-id="4c0c1-102">sql:overflow-field (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="4c0c1-102">sql:overflow-field (SQLXML 4.0)</span></span>
  <span data-ttu-id="4c0c1-103">Em um esquema, você pode identificar uma coluna de estouro para receber todos os dados não consumidos do documento XML.</span><span class="sxs-lookup"><span data-stu-id="4c0c1-103">In a schema, you can identify a column as an overflow column to receive all unconsumed data from the XML document.</span></span> <span data-ttu-id="4c0c1-104">Essa coluna é especificada no esquema usando a anotação `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="4c0c1-104">This column is specified in the schema by using the `sql:overflow-field` annotation.</span></span> <span data-ttu-id="4c0c1-105">É possível ter várias colunas de estouro.</span><span class="sxs-lookup"><span data-stu-id="4c0c1-105">It is possible to have multiple overflow columns.</span></span>  
  
 <span data-ttu-id="4c0c1-106">Sempre que um nó de XML (elemento ou atributo) para o qual haja uma anotação `sql:overflow-field` definida entrar no escopo, a coluna de estouro será ativada e receberá os dados não consumidos.</span><span class="sxs-lookup"><span data-stu-id="4c0c1-106">Whenever an XML node (element or attribute) for which there is a `sql:overflow-field` annotation defined enters into scope, the overflow column is activated and receives unconsumed data.</span></span> <span data-ttu-id="4c0c1-107">Quando o nó sair do escopo, a coluna de estouro não ficará mais ativa e o XML Bulk Load tornará o campo de estouro anterior (se houver) ativo.</span><span class="sxs-lookup"><span data-stu-id="4c0c1-107">When the node goes out of scope, the overflow column is no longer active and XML Bulk Load makes the previous overflow field (if any) active.</span></span>  
  
 <span data-ttu-id="4c0c1-108">Conforme ele armazena dados na coluna de estouro, o XML Bulk Load também armazena as marcas de abertura e fechamento do elemento pai para o qual `sql:overflow-field` é definido.</span><span class="sxs-lookup"><span data-stu-id="4c0c1-108">As it stores data in the overflow column, XML Bulk Load also stores the opening and closing tags of the parent element for which `sql:overflow-field` is defined.</span></span>  
  
 <span data-ttu-id="4c0c1-109">Por exemplo, o esquema a seguir descreve **\<Customers>** os **\<CustOrder>** elementos e.</span><span class="sxs-lookup"><span data-stu-id="4c0c1-109">For example, the following schema describes the **\<Customers>** and **\<CustOrder>** elements.</span></span> <span data-ttu-id="4c0c1-110">Cada um destes elementos identifica uma coluna de estouro:</span><span class="sxs-lookup"><span data-stu-id="4c0c1-110">Each of these elements identifies an overflow column:</span></span>  
  
```  
<?xml version="1.0" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
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
 <xsd:element name="ROOT" sql:is-constant="1">  
  <xsd:complexType>  
    <xsd:sequence>   
      <xsd:element name="Customers"   
                   sql:relation="Cust"  
                   sql:overflow-field="OverflowColumn">  
        <xsd:complexType>  
             <xsd:sequence>   
             <xsd:element name="CustomerID" type="xsd:integer"/>  
             <xsd:element name="CompanyName"  type="xsd:string"/>  
             <xsd:element name="City" type="xsd:string"/>  
             <xsd:element name="Order"  
                          sql:relation="CustOrder"  
                          sql:relationship="CustCustOrder"  
                          sql:overflow-field="OverflowColumn">  
               <xsd:complexType>  
                 <xsd:attribute name="OrderID"/>  
                 <xsd:attribute name="CustomerID"/>  
               </xsd:complexType>  
             </xsd:element>  
          </xsd:sequence>   
        </xsd:complexType>  
      </xsd:element>  
    </xsd:sequence>  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="4c0c1-111">No esquema, o **\<Customer>** elemento é mapeado para a tabela Cust e o **\<Order>** elemento é mapeado para a tabela CustOrder.</span><span class="sxs-lookup"><span data-stu-id="4c0c1-111">In the schema, the **\<Customer>** element maps to the Cust table and the **\<Order>** element maps to the CustOrder table.</span></span>  
  
 <span data-ttu-id="4c0c1-112">Os **\<Customer>** elementos e **\<Order>** identificam uma coluna de estouro.</span><span class="sxs-lookup"><span data-stu-id="4c0c1-112">Both the **\<Customer>** and **\<Order>** elements identify an overflow column.</span></span> <span data-ttu-id="4c0c1-113">Assim, o carregamento em massa de XML salva todos os elementos filho e atributos não consumidos do **\<Customer>** elemento na coluna Overflow da tabela Cust e todos os elementos filho e atributos não consumidos do **\<Order>** elemento na coluna Overflow da tabela CustOrder.</span><span class="sxs-lookup"><span data-stu-id="4c0c1-113">Thus, XML Bulk Load saves all the unconsumed child elements and attributes of the **\<Customer>** element in the overflow column of the Cust table, and all the unconsumed child elements and attributes of the **\<Order>** element in the overflow column of the CustOrder table.</span></span>  
  
### <a name="to-test-a-working-sample"></a><span data-ttu-id="4c0c1-114">Para testar um exemplo de funcionamento</span><span class="sxs-lookup"><span data-stu-id="4c0c1-114">To test a working sample</span></span>  
  
1.  <span data-ttu-id="4c0c1-115">Salve o esquema fornecido neste exemplo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="4c0c1-115">Save the schema that is provided in this example as SampleSchema.xml.</span></span>  
  
2.  <span data-ttu-id="4c0c1-116">Crie estas tabelas:</span><span class="sxs-lookup"><span data-stu-id="4c0c1-116">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Cust (  
              CustomerID     int         PRIMARY KEY,  
              CompanyName    varchar(20) NOT NULL,  
              City           varchar(20) DEFAULT 'Seattle',  
              OverflowColumn nvarchar(200))  
    GO  
    CREATE TABLE CustOrder (  
              OrderID        int         PRIMARY KEY,  
              CustomerID     int         FOREIGN KEY REFERENCES  
                                              Cust(CustomerID),  
              OverflowColumn nvarchar(200))  
    GO  
    ```  
  
3.  <span data-ttu-id="4c0c1-117">Salve os dados XML de exemplo a seguir como SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="4c0c1-117">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City><![CDATA[NY]]> </City>  
          <Junk>garbage in overflow</Junk>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
     </Customers>  
     <Customers>  
       <CustomerID>1112</CustomerID>  
       <CompanyName>Toms Spezialitten</CompanyName>  
       <City><![CDATA[LA]]> </City>  
       <xyz><address>111 Maple, Seattle</address></xyz>     
       <Order OrderID="3" />  
     </Customers>  
       <Customers>  
       <CustomerID>1113</CustomerID>  
       <CompanyName>Victuailles en stock</CompanyName>  
       <Order OrderID="4" />  
      </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="4c0c1-118">Para executar o XML Bulk Load, salve e execute este exemplo do [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) como Sample.vbs:</span><span class="sxs-lookup"><span data-stu-id="4c0c1-118">To execute XML Bulk Load, save and execute this [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript) example as Sample.vbs:</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "c:\SampleSchema.xml", "c:\SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
  
