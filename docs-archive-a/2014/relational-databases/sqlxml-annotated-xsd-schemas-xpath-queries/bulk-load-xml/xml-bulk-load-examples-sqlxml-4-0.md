---
title: Exemplos de carregamento em massa de XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- overflow-field annotation
- ConnectionCommand property
- XMLFragment property
- relationship chains [SQLXML]
- multiple table bulk loading
- examples [SQLXML], XML Bulk Load
- overflow data [SQLXML]
- sql:datatype
- transaction mode [SQLXML]
- CheckConstraints property
- sql:overflow-field
- XML Bulk Load [SQLXML], examples
- TempFilePath property
- datatype annotation
- Transaction property
- KeepIdentity property
- Execute method
- streaming XML data
- xml data type [SQL Server], SQLXML
- bulk load [SQLXML], examples
ms.assetid: 970e4553-b41d-4a12-ad50-0ee65d1f305d
author: rothja
ms.author: jroth
ms.openlocfilehash: c7eaec77ef068efd28c4da65833afa5047b222f9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87678680"
---
# <a name="xml-bulk-load-examples-sqlxml-40"></a><span data-ttu-id="098b4-102">Exemplos do XML Bulk Load (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="098b4-102">XML Bulk Load Examples (SQLXML 4.0)</span></span>
  <span data-ttu-id="098b4-103">Os exemplos a seguir ilustram a funcionalidade do XML Bulk Load no Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="098b4-103">The following examples illustrate the XML Bulk Load functionality in Microsoft [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="098b4-104">Cada exemplo fornece um esquema XSD e seu esquema XDR equivalente.</span><span class="sxs-lookup"><span data-stu-id="098b4-104">Each example provides an XSD schema and its equivalent XDR schema.</span></span>  
  
## <a name="bulk-loader-script-validateandbulkloadvbs"></a><span data-ttu-id="098b4-105">Script de Carregador em Massa (ValidateAndBulkload.vbs)</span><span class="sxs-lookup"><span data-stu-id="098b4-105">Bulk Loader Script (ValidateAndBulkload.vbs)</span></span>  
 <span data-ttu-id="098b4-106">O script a seguir, escrito na [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript), carrega um documento XML no DOM XML; o valida em relação a um esquema; e, se o documento for válido, executará um carregamento em massa XML para carregar o XML em uma [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tabela.</span><span class="sxs-lookup"><span data-stu-id="098b4-106">The following script, written in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Visual Basic Scripting Edition (VBScript), loads an XML document into the XML DOM; validates it against a schema; and, if the document is valid, executes an XML bulk load to load the XML into a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] table.</span></span> <span data-ttu-id="098b4-107">Esse script pode ser usado com cada um dos exemplos individuais que farão referência a ele posteriormente neste tópico.</span><span class="sxs-lookup"><span data-stu-id="098b4-107">This script can be used with each of the individual examples that refer to it later in this topic.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="098b4-108">O XML Bulk Load não lançará um aviso ou um erro se nenhum conteúdo for carregado do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="098b4-108">XML Bulk Load does not throw a warning or an error if no content is uploaded from the data file.</span></span> <span data-ttu-id="098b4-109">Portanto, é uma prática recomendada validar seu arquivo de dados XML antes de executar uma operação de carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="098b4-109">Therefore, it is a good practice to validate your XML data file prior to executing a bulk load operation.</span></span>  
  
```  
Dim FileValid  
  
set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=MyServer;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
  
'Validate the data file prior to bulkload  
Dim sOutput   
sOutput = ValidateFile("SampleXMLData.xml", "", "SampleSchema.xml")  
WScript.Echo sOutput  
  
If FileValid Then  
   ' Check constraints and initiate transaction (if needed)  
   ' objBL.CheckConstraints = True  
   ' objBL.Transaction=True  
  'Execute XML bulkload using file.  
  objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
  set objBL=Nothing  
End If  
  
Function ValidateFile(strXmlFile,strUrn,strXsdFile)  
  
   ' Create a schema cache and add SampleSchema.xml to it.  
   Dim xs, fso, sAppPath  
   Set fso = CreateObject("Scripting.FileSystemObject")   
   Set xs = CreateObject("MSXML2.XMLSchemaCache.6.0")  
   sAppPath = fso.GetFolder(".")   
   xs.Add strUrn, sAppPath & "\" & strXsdFile  
  
   ' Create an XML DOMDocument object.  
   Dim xd   
   Set xd = CreateObject("MSXML2.DOMDocument.6.0")  
  
   ' Assign the schema cache to the DOM document.  
   ' schemas collection.  
   Set xd.schemas = xs  
  
   ' Load XML document as DOM document.  
   xd.async = False  
   xd.Load sAppPath & "\" & strXmlFile  
  
   ' Return validation results in message to the user.  
   If xd.parseError.errorCode <> 0 Then  
        ValidateFile = "Validation failed on " & _  
             strXmlFile & vbCrLf & _  
             "=======" & vbCrLf & _  
             "Reason: " & xd.parseError.reason & _  
             vbCrLf & "Source: " & _  
             xd.parseError.srcText & _  
             vbCrLf & "Line: " & _  
             xd.parseError.Line & vbCrLf  
             FileValid = False  
    Else  
        ValidateFile = "Validation succeeded for " & _  
             strXmlFile & vbCrLf & _  
             "========" & _  
             vbCrLf & "Contents to be bulkloaded" & vbCrLf  
             FileValid = True  
    End If  
End Function  
```  
  
## <a name="a-bulk-loading-xml-in-a-table"></a><span data-ttu-id="098b4-110">a.</span><span class="sxs-lookup"><span data-stu-id="098b4-110">A.</span></span> <span data-ttu-id="098b4-111">Carregando o XML em massa em uma tabela</span><span class="sxs-lookup"><span data-stu-id="098b4-111">Bulk loading XML in a table</span></span>  
 <span data-ttu-id="098b4-112">Este exemplo estabelece uma conexão com a instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] que é especificada na propriedade ConnectionString (meuservidor).</span><span class="sxs-lookup"><span data-stu-id="098b4-112">This example establishes a connection to the instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] that is specified in the ConnectionString property (MyServer).</span></span> <span data-ttu-id="098b4-113">O exemplo também especifica a Propriedade LogFile.</span><span class="sxs-lookup"><span data-stu-id="098b4-113">The example also specifies the ErrorLogFile property.</span></span> <span data-ttu-id="098b4-114">Portanto, a saída de erro é salva no arquivo especificado ("C:\error.log") que você também poderá decidir alterar para um local diferente.</span><span class="sxs-lookup"><span data-stu-id="098b4-114">Therefore, the error output is saved in the specified file ("C:\error.log"), which you might also decide to change to a different location.</span></span> <span data-ttu-id="098b4-115">Observe também que o método Execute tem como seus parâmetros o arquivo de esquema de mapeamento (SampleSchema.xml) e o arquivo de dados XML (SampleXMLData.xml).</span><span class="sxs-lookup"><span data-stu-id="098b4-115">Notice also that the Execute method has as its parameters both the mapping schema file (SampleSchema.xml) and the XML data file (SampleXMLData.xml).</span></span> <span data-ttu-id="098b4-116">Quando o carregamento em massa for executado, a tabela Cust que você criou no banco de dados **tempdb** conterá novos registros com base no conteúdo do arquivo de dados XML.</span><span class="sxs-lookup"><span data-stu-id="098b4-116">When the bulk load executes, the Cust table you have created in **tempdb** database will contain new records based upon the contents of the XML data file.</span></span>  
  
#### <a name="to-test-a-sample-bulk-load"></a><span data-ttu-id="098b4-117">Para testar um exemplo de carregamento em massa</span><span class="sxs-lookup"><span data-stu-id="098b4-117">To test a sample bulk load</span></span>  
  
1.  <span data-ttu-id="098b4-118">Crie esta tabela:</span><span class="sxs-lookup"><span data-stu-id="098b4-118">Create this table:</span></span>  
  
    ```  
    CREATE TABLE Cust(CustomerID  int PRIMARY KEY,  
                      CompanyName varchar(20),  
                      City        varchar(20));  
    GO  
    ```  
  
2.  <span data-ttu-id="098b4-119">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-119">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="098b4-120">Para este arquivo, adicione o seguinte esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="098b4-120">To this file, add the following XSD schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
       <xsd:element name="ROOT" sql:is-constant="1" >  
         <xsd:complexType>  
           <xsd:sequence>  
             <xsd:element name="Customers" sql:relation="Cust" maxOccurs="unbounded">  
               <xsd:complexType>  
                 <xsd:sequence>  
                   <xsd:element name="CustomerID"  type="xsd:integer" />  
                   <xsd:element name="CompanyName" type="xsd:string" />  
                   <xsd:element name="City"        type="xsd:string" />  
                 </xsd:sequence>  
               </xsd:complexType>  
             </xsd:element>  
           </xsd:sequence>  
          </xsd:complexType>  
         </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="098b4-121">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleXMLD.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-121">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="098b4-122">Para esse arquivo, adicione o seguinte documento XML:</span><span class="sxs-lookup"><span data-stu-id="098b4-122">To this file, add the following XML document:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Sean Chai</CompanyName>  
        <City>New York</City>  
      </Customers>  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Tom Johnston</CompanyName>  
         <City>Los Angeles</City>  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Institute of Art</CompanyName>  
        <City>Chicago</City>  
      </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="098b4-123">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="098b4-123">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="098b4-124">Para esse arquivo, adicione o código VBScript que foi fornecido anteriormente, no início deste tópico.</span><span class="sxs-lookup"><span data-stu-id="098b4-124">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="098b4-125">Modifique a cadeia de conexão para fornecer o nome do servidor apropriado.</span><span class="sxs-lookup"><span data-stu-id="098b4-125">Modify the connection string to provide the appropriate server name.</span></span> <span data-ttu-id="098b4-126">Especifique o caminho apropriado para os arquivos que são especificados como parâmetros para o método execute.</span><span class="sxs-lookup"><span data-stu-id="098b4-126">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
5.  <span data-ttu-id="098b4-127">Execute o código VBScript.</span><span class="sxs-lookup"><span data-stu-id="098b4-127">Execute the VBScript code.</span></span> <span data-ttu-id="098b4-128">O XML Bulk Load carrega o XML para a tabela Cust.</span><span class="sxs-lookup"><span data-stu-id="098b4-128">XML Bulk Load loads the XML into the Cust table.</span></span>  
  
 <span data-ttu-id="098b4-129">Este é o esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="098b4-129">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers"  sql:relation="Cust" >  
      <element type="CustomerID"  sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City"        sql:field="City" />  
  
   </ElementType>  
</Schema>  
```  
  
## <a name="b-bulk-loading-xml-data-in-multiple-tables"></a><span data-ttu-id="098b4-130">B.</span><span class="sxs-lookup"><span data-stu-id="098b4-130">B.</span></span> <span data-ttu-id="098b4-131">Carregando dados XML em massa em várias tabelas</span><span class="sxs-lookup"><span data-stu-id="098b4-131">Bulk loading XML data in multiple tables</span></span>  
 <span data-ttu-id="098b4-132">Neste exemplo, o documento XML consiste nos **\<Customer>** **\<Order>** elementos e.</span><span class="sxs-lookup"><span data-stu-id="098b4-132">In this example, the XML document consists of the **\<Customer>** and **\<Order>** elements.</span></span>  
  
```  
<ROOT>  
  <Customers>  
    <CustomerID>1111</CustomerID>  
    <CompanyName>Sean Chai</CompanyName>  
    <City>NY</City>  
    <Order OrderID="1" />  
    <Order OrderID="2" />  
  </Customers>  
  <Customers>  
    <CustomerID>1112</CustomerID>  
    <CompanyName>Tom Johnston</CompanyName>  
     <City>LA</City>    
    <Order OrderID="3" />  
  </Customers>  
  <Customers>  
    <CustomerID>1113</CustomerID>  
    <CompanyName>Institute of Art</CompanyName>  
    <Order OrderID="4" />  
  </Customers>  
</ROOT>  
```  
  
 <span data-ttu-id="098b4-133">Este exemplo carrega em massa os dados XML em duas tabelas, **cust** e **CustOrder**:</span><span class="sxs-lookup"><span data-stu-id="098b4-133">This example bulk loads the XML data into two tables, **Cust** and **CustOrder**:</span></span>  
  
```  
Cust(CustomerID, CompanyName, City)  
CustOrder(OrderID, CustomerID)  
```  
  
 <span data-ttu-id="098b4-134">O seguinte esquema XSD define a exibição XML dessas tabelas.</span><span class="sxs-lookup"><span data-stu-id="098b4-134">The following XSD schema defines the XML view of these tables.</span></span> <span data-ttu-id="098b4-135">O esquema especifica a relação pai-filho entre os **\<Customer>** **\<Order>** elementos e.</span><span class="sxs-lookup"><span data-stu-id="098b4-135">The schema specifies the parent-child relationship between the **\<Customer>** and **\<Order>** elements.</span></span>  
  
```  
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
  <xsd:element name="ROOT" sql:is-constant="1" >  
    <xsd:complexType>  
      <xsd:sequence>  
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
      </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="098b4-136">O carregamento em massa de XML usa a relação de chave primária/chave estrangeira especificada acima entre os **\<Cust>** **\<CustOrder>** elementos e para carregar em massa os dados em ambas as tabelas.</span><span class="sxs-lookup"><span data-stu-id="098b4-136">XML Bulk Load uses the primary key/foreign key relationship specified above between the **\<Cust>** and **\<CustOrder>** elements to bulk load the data into both tables.</span></span>  
  
#### <a name="to-test-a-sample-bulk-load"></a><span data-ttu-id="098b4-137">Para testar um exemplo de carregamento em massa</span><span class="sxs-lookup"><span data-stu-id="098b4-137">To test a sample bulk load</span></span>  
  
1.  <span data-ttu-id="098b4-138">Crie duas tabelas no banco de dados **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="098b4-138">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust(  
           CustomerID  int PRIMARY KEY,  
           CompanyName varchar(20),  
           City        varchar(20));  
    CREATE TABLE CustOrder(        OrderID     int PRIMARY KEY,   
            CustomerID int FOREIGN KEY REFERENCES Cust(CustomerID));  
    ```  
  
2.  <span data-ttu-id="098b4-139">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-139">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="098b4-140">Adicione ao arquivo o esquema XSD que é fornecido neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="098b4-140">Add the XSD schema that is provided in this example to the file.</span></span>  
  
3.  <span data-ttu-id="098b4-141">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleData.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-141">Create a file in your preferred text or XML editor, and save it as SampleData.xml.</span></span> <span data-ttu-id="098b4-142">Adicione ao arquivo o documento XML que foi fornecido anteriormente neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="098b4-142">Add the XML document that was provided earlier in this example to the file.</span></span>  
  
4.  <span data-ttu-id="098b4-143">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="098b4-143">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="098b4-144">Para esse arquivo, adicione o código VBScript que foi fornecido anteriormente, no início deste tópico.</span><span class="sxs-lookup"><span data-stu-id="098b4-144">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="098b4-145">Modifique a cadeia de conexão para fornecer o nome apropriado de servidor e de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="098b4-145">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="098b4-146">Especifique o caminho apropriado para os arquivos que são especificados como parâmetros para o método execute.</span><span class="sxs-lookup"><span data-stu-id="098b4-146">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
5.  <span data-ttu-id="098b4-147">Execute o código VBScript anterior.</span><span class="sxs-lookup"><span data-stu-id="098b4-147">Execute the VBScript code above.</span></span> <span data-ttu-id="098b4-148">O XML Bulk Load carrega o documento XML para as tabelas Cust e CustOrder.</span><span class="sxs-lookup"><span data-stu-id="098b4-148">XML Bulk Load loads the XML document into the Cust and CustOrder tables.</span></span>  
  
 <span data-ttu-id="098b4-149">Este é o esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="098b4-149">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >   
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust" >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
<sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
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
  
## <a name="c-using-chain-relationships-in-the-schema-to-bulk-load-xml"></a><span data-ttu-id="098b4-150">C.</span><span class="sxs-lookup"><span data-stu-id="098b4-150">C.</span></span> <span data-ttu-id="098b4-151">Usando relações de cadeia no esquema para carregamento em massa do XML</span><span class="sxs-lookup"><span data-stu-id="098b4-151">Using chain relationships in the schema to bulk load XML</span></span>  
 <span data-ttu-id="098b4-152">Este exemplo ilustra como a relação M:N especificada no esquema de mapeamento é usada pelo XML Bulk Load para carregar dados em uma tabela que representa uma relação M:N.</span><span class="sxs-lookup"><span data-stu-id="098b4-152">This example illustrates how the M:N relationship that is specified in the mapping schema is used by XML Bulk Load to load data in a table that represents an M:N relationship.</span></span>  
  
 <span data-ttu-id="098b4-153">Por exemplo, considere este esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="098b4-153">For example, consider this XSD schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrderOD"  
          parent="Ord"  
          parent-key="OrderID"  
          child="OrderDetail"  
          child-key="OrderID" />  
  
    <sql:relationship name="ODProduct"  
          parent="OrderDetail"  
          parent-key="ProductID"  
          child="Product"  
          child-key="ProductID"   
          inverse="true"/>  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="ROOT" sql:is-constant="1" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Ord"   
                     sql:key-fields="OrderID" >  
          <xsd:complexType>  
            <xsd:sequence>  
             <xsd:element name="Product"  
                          sql:relation="Product"   
                          sql:key-fields="ProductID"  
                          sql:relationship="OrderOD ODProduct">  
               <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
               </xsd:complexType>  
             </xsd:element>  
           </xsd:sequence>  
           <xsd:attribute name="OrderID"   type="xsd:integer" />   
           <xsd:attribute name="CustomerID"   type="xsd:string" />  
         </xsd:complexType>  
       </xsd:element>  
      </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="098b4-154">O esquema especifica um **\<Order>** elemento com um **\<Product>** elemento filho.</span><span class="sxs-lookup"><span data-stu-id="098b4-154">The schema specifies an **\<Order>** element with a **\<Product>** child element.</span></span> <span data-ttu-id="098b4-155">O **\<Order>** elemento é mapeado para a tabela Ord e o **\<Product>** elemento é mapeado para a tabela Product no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="098b4-155">The **\<Order>** element maps to Ord table and the **\<Product>** element maps to the Product table in the database.</span></span> <span data-ttu-id="098b4-156">A relação de cadeia especificada no **\<Product>** elemento identifica uma relação de M:N representada pela tabela OrderDetail.</span><span class="sxs-lookup"><span data-stu-id="098b4-156">The chain relationship specified on the **\<Product>** element identifies a M:N relationship represented by the OrderDetail table.</span></span> <span data-ttu-id="098b4-157">(Uma ordem pode incluir vários produtos, e um produto pode ser incluído em muitos pedidos.)</span><span class="sxs-lookup"><span data-stu-id="098b4-157">(An order can include many products, and a product can be included in many orders.)</span></span>  
  
 <span data-ttu-id="098b4-158">Quando você está carregando em massa um documento XML com esse esquema, os registros são adicionados às tabelas Ord, Product e OrderDetail.</span><span class="sxs-lookup"><span data-stu-id="098b4-158">When you are bulk loading an XML document with this schema, records are added to the Ord, Product, and OrderDetail tables.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="098b4-159">Para testar um exemplo de funcionamento</span><span class="sxs-lookup"><span data-stu-id="098b4-159">To test a working sample</span></span>  
  
1.  <span data-ttu-id="098b4-160">Crie três tabelas:</span><span class="sxs-lookup"><span data-stu-id="098b4-160">Create three tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int  PRIMARY KEY,  
             CustomerID  varchar(5));  
    GO  
    CREATE TABLE Product (  
             ProductID   int PRIMARY KEY,  
             ProductName varchar(20));  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID));  
    GO  
    ```  
  
2.  <span data-ttu-id="098b4-161">Salve o esquema fornecido anteriormente neste exemplo como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-161">Save the schema that is provided above in this example as SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="098b4-162">Salve os dados XML de exemplo a seguir como SampleXMLData.xml:</span><span class="sxs-lookup"><span data-stu-id="098b4-162">Save the following sample XML data as SampleXMLData.xml:</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="1" CustomerID="ALFKI">  
        <Product ProductID="1" ProductName="Chai" />  
        <Product ProductID="2" ProductName="Chang" />  
      </Order>  
      <Order OrderID="2" CustomerID="ANATR">  
        <Product ProductID="3" ProductName="Aniseed Syrup" />  
        <Product ProductID="4" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="098b4-163">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="098b4-163">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="098b4-164">Para esse arquivo, adicione o código VBScript que foi fornecido anteriormente, no início deste tópico.</span><span class="sxs-lookup"><span data-stu-id="098b4-164">To this file, add the VBScript code that is provided above at the beginning of this topic.</span></span> <span data-ttu-id="098b4-165">Modifique a cadeia de conexão para fornecer o nome apropriado de servidor e de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="098b4-165">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="098b4-166">Remova os comentários das linhas a seguir do código fonte para obter este exemplo.</span><span class="sxs-lookup"><span data-stu-id="098b4-166">Uncomment the following lines from the source code for this example.</span></span>  
  
    ```  
    objBL.CheckConstraints = True  
    objBL.Transaction=True  
    ```  
  
5.  <span data-ttu-id="098b4-167">Execute o código VBScript.</span><span class="sxs-lookup"><span data-stu-id="098b4-167">Execute the VBScript code.</span></span> <span data-ttu-id="098b4-168">O XML Bulk Load carrega o documento XML para as tabelas Ord e Product.</span><span class="sxs-lookup"><span data-stu-id="098b4-168">XML Bulk Load loads the XML document into the Ord and Product tables.</span></span>  
  
## <a name="d-bulk-loading-in-identity-type-columns"></a><span data-ttu-id="098b4-169">D.</span><span class="sxs-lookup"><span data-stu-id="098b4-169">D.</span></span> <span data-ttu-id="098b4-170">Carregamento em massa em colunas de tipo de identidade</span><span class="sxs-lookup"><span data-stu-id="098b4-170">Bulk loading in identity type columns</span></span>  
 <span data-ttu-id="098b4-171">Este exemplo ilustra como o carregamento em massa trata colunas de tipo de identidade.</span><span class="sxs-lookup"><span data-stu-id="098b4-171">This example illustrates how bulk load handles identity type columns.</span></span> <span data-ttu-id="098b4-172">No exemplo, os dados são carregados em massa para três tabelas (Ord, Product e OrderDetail).</span><span class="sxs-lookup"><span data-stu-id="098b4-172">In the example, data is bulk loaded into three tables (Ord, Product, and OrderDetail).</span></span>  
  
 <span data-ttu-id="098b4-173">Nestas tabelas:</span><span class="sxs-lookup"><span data-stu-id="098b4-173">In these tables:</span></span>  
  
-   <span data-ttu-id="098b4-174">OrderID na tabela Ord é uma coluna de tipo de identidade</span><span class="sxs-lookup"><span data-stu-id="098b4-174">OrderID in the Ord table is an identity type column</span></span>  
  
-   <span data-ttu-id="098b4-175">ProductID na tabela Product é uma coluna de tipo de identidade.</span><span class="sxs-lookup"><span data-stu-id="098b4-175">ProductID in the Product table is an identity type column.</span></span>  
  
-   <span data-ttu-id="098b4-176">As colunas OrderID e ProductID na tabela OrderDetail são colunas de chave estrangeira que se referem a colunas de chave primária nas tabelas Ord e Product.</span><span class="sxs-lookup"><span data-stu-id="098b4-176">OrderID and ProductID columns in the OrderDetail are foreign key columns referring to corresponding primary key columns in the Ord and Product tables.</span></span>  
  
 <span data-ttu-id="098b4-177">A seguir, são descritos os esquemas de tabela para este exemplo:</span><span class="sxs-lookup"><span data-stu-id="098b4-177">The following are the table schemas for this example:</span></span>  
  
```  
Ord (OrderID, CustomerID)  
Product (ProductID, ProductName)  
OrderDetail (OrderID, ProductID)  
```  
  
 <span data-ttu-id="098b4-178">Neste exemplo de carregamento em massa de XML, a Propriedade KeepIdentity do modelo de objeto carregamento em massa é definida como false.</span><span class="sxs-lookup"><span data-stu-id="098b4-178">In this example of XML Bulk Load, the KeepIdentity property of the BulkLoad object model is set to false.</span></span> <span data-ttu-id="098b4-179">Portanto, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] gera valores de identidade para as colunas ProductID e OrderID nas tabelas Product e Ord, respectivamente (todos os valores fornecidos nos documentos a serem carregados em massa são ignorados).</span><span class="sxs-lookup"><span data-stu-id="098b4-179">Therefore, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] generates identity values for the ProductID and OrderID columns in the Product and Ord tables, respectively (any values provided in the documents to be bulk loaded are ignored).</span></span>  
  
 <span data-ttu-id="098b4-180">Neste caso, o XML Bulk Load identifica a relação de chave primária/chave estrangeira entre as tabelas.</span><span class="sxs-lookup"><span data-stu-id="098b4-180">In this case, XML Bulk Load identifies the primary key/foreign key relationship among tables.</span></span> <span data-ttu-id="098b4-181">O Bulk Load primeiro insere registros nas tabelas com a chave primária e, em seguida, propaga o valor de identidade gerado pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para as tabelas com colunas de chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="098b4-181">Bulk Load first inserts records in the tables with the primary key, then propagates the identity value generated by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to the tables with foreign key columns.</span></span> <span data-ttu-id="098b4-182">No exemplo a seguir, o XML Bulk Load insere dados nas tabelas nesta ordem:</span><span class="sxs-lookup"><span data-stu-id="098b4-182">In the following example, XML Bulk Load inserts data in tables in this order:</span></span>  
  
1.  <span data-ttu-id="098b4-183">Produto</span><span class="sxs-lookup"><span data-stu-id="098b4-183">Product</span></span>  
  
2.  <span data-ttu-id="098b4-184">Ord</span><span class="sxs-lookup"><span data-stu-id="098b4-184">Ord</span></span>  
  
3.  <span data-ttu-id="098b4-185">OrderDetail</span><span class="sxs-lookup"><span data-stu-id="098b4-185">OrderDetail</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="098b4-186">Para propagar os valores de identidade gerados nas tabelas Products e Orders, a lógica de processamento exige que o XML Bulk Load acompanhe a inserção mais recente desses valores na tabela OrderDetails.</span><span class="sxs-lookup"><span data-stu-id="098b4-186">In order to propagate identity values generated in the Products and Orders tables, the processing logic requires XML Bulk Load to keep track of these values for later insertion into the OrderDetails table.</span></span> <span data-ttu-id="098b4-187">Para fazer isso, o XML Bulk Load cria tabelas intermediárias, popula os dados nessas tabelas e depois os remove.</span><span class="sxs-lookup"><span data-stu-id="098b4-187">To do that, XML Bulk Load creates intermediate tables, populates the data in these tables, and later removes them.</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="098b4-188">Para testar um exemplo de funcionamento</span><span class="sxs-lookup"><span data-stu-id="098b4-188">To test a working sample</span></span>  
  
1.  <span data-ttu-id="098b4-189">Crie estas tabelas:</span><span class="sxs-lookup"><span data-stu-id="098b4-189">Create these tables:</span></span>  
  
    ```  
    CREATE TABLE Ord (  
             OrderID     int identity(1,1)  PRIMARY KEY,  
             CustomerID  varchar(5));  
    GO  
    CREATE TABLE Product (  
             ProductID   int identity(1,1) PRIMARY KEY,  
             ProductName varchar(20));  
    GO  
    CREATE TABLE OrderDetail (  
           OrderID     int FOREIGN KEY REFERENCES Ord(OrderID),  
           ProductID   int FOREIGN KEY REFERENCES Product(ProductID),  
                       CONSTRAINT OD_key PRIMARY KEY (OrderID, ProductID));  
    GO  
    ```  
  
2.  <span data-ttu-id="098b4-190">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-190">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="098b4-191">Adicione este esquema XSD a este arquivo.</span><span class="sxs-lookup"><span data-stu-id="098b4-191">Add this XSD schema to this file.</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
     <xsd:annotation>  
       <xsd:appinfo>  
        <sql:relationship name="OrderOD"  
              parent="Ord"  
              parent-key="OrderID"  
              child="OrderDetail"  
              child-key="OrderID" />  
        <sql:relationship name="ODProduct"  
              parent="OrderDetail"  
              parent-key="ProductID"  
              child="Product"  
              child-key="ProductID"   
              inverse="true"/>  
       </xsd:appinfo>  
     </xsd:annotation>  
  
      <xsd:element name="Order" sql:relation="Ord"   
                                sql:key-fields="OrderID" >  
       <xsd:complexType>  
         <xsd:sequence>  
            <xsd:element name="Product" sql:relation="Product"   
                         sql:key-fields="ProductID"  
                         sql:relationship="OrderOD ODProduct">  
              <xsd:complexType>  
                 <xsd:attribute name="ProductID" type="xsd:int" />  
                 <xsd:attribute name="ProductName" type="xsd:string" />  
              </xsd:complexType>  
            </xsd:element>  
         </xsd:sequence>  
            <xsd:attribute name="OrderID"   type="xsd:integer" />   
            <xsd:attribute name="CustomerID"   type="xsd:string" />  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="098b4-192">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleXMLD.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-192">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="098b4-193">Adicione o documento XML a seguir.</span><span class="sxs-lookup"><span data-stu-id="098b4-193">Add the following XML document.</span></span>  
  
    ```  
    <ROOT>    
      <Order OrderID="11" CustomerID="ALFKI">  
        <Product ProductID="11" ProductName="Chai" />  
        <Product ProductID="22" ProductName="Chang" />  
      </Order>  
      <Order OrderID="22" CustomerID="ANATR">  
         <Product ProductID="33" ProductName="Aniseed Syrup" />  
        <Product ProductID="44" ProductName="Gumbo Mix" />  
      </Order>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="098b4-194">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="098b4-194">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="098b4-195">Para este arquivo, adicione o código VBScript a seguir.</span><span class="sxs-lookup"><span data-stu-id="098b4-195">To this file, add the following VBScript code.</span></span> <span data-ttu-id="098b4-196">Modifique a cadeia de conexão para fornecer o nome apropriado de servidor e de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="098b4-196">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="098b4-197">Especifique o caminho apropriado para os arquivos que servem como parâmetros para o `Execute` método.</span><span class="sxs-lookup"><span data-stu-id="098b4-197">Specify the appropriate path for the files that serve as parameters to the `Execute` method.</span></span>  
  
    ```  
    Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "C:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Transaction = False  
    objBL.KeepIdentity = False  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    Set objBL = Nothing  
    MsgBox "Done."  
    ```  
  
5.  <span data-ttu-id="098b4-198">Execute o código VBScript.</span><span class="sxs-lookup"><span data-stu-id="098b4-198">Execute the VBScript code.</span></span> <span data-ttu-id="098b4-199">O XML Bulk Load carregará os dados nas tabelas apropriadas.</span><span class="sxs-lookup"><span data-stu-id="098b4-199">The XML Bulk Load will load the data into the appropriate tables.</span></span>  
  
## <a name="e-generating-table-schemas-before-bulk-loading"></a><span data-ttu-id="098b4-200">E.</span><span class="sxs-lookup"><span data-stu-id="098b4-200">E.</span></span> <span data-ttu-id="098b4-201">Gerando esquemas de tabela antes do carregamento em massa</span><span class="sxs-lookup"><span data-stu-id="098b4-201">Generating table schemas before bulk loading</span></span>  
 <span data-ttu-id="098b4-202">O XML Bulk Load poderá opcionalmente gerar as tabelas se elas não existirem antes do carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="098b4-202">XML Bulk Load can optionally generate the tables if they do not exist before bulk loading.</span></span> <span data-ttu-id="098b4-203">A definição da propriedade SchemaGen do objeto SQLXMLBulkLoad como TRUE faz isso.</span><span class="sxs-lookup"><span data-stu-id="098b4-203">Setting the SchemaGen property of the SQLXMLBulkLoad object to TRUE does this.</span></span> <span data-ttu-id="098b4-204">Opcionalmente, você também pode solicitar o carregamento em massa de XML para descartar todas as tabelas existentes e recriá-las, definindo a propriedade SGDropTables como TRUE.</span><span class="sxs-lookup"><span data-stu-id="098b4-204">You can also optionally request XML Bulk Load to drop any existing tables and re-create them by setting the SGDropTables property to TRUE.</span></span> <span data-ttu-id="098b4-205">O exemplo de VBScript a seguir ilustra o uso dessas propriedades.</span><span class="sxs-lookup"><span data-stu-id="098b4-205">The following VBScript example illustrates the use of these properties.</span></span>  
  
 <span data-ttu-id="098b4-206">Além disso, este exemplo define duas propriedades adicionais como TRUE:</span><span class="sxs-lookup"><span data-stu-id="098b4-206">Also, this example sets two additional properties to TRUE:</span></span>  
  
-   <span data-ttu-id="098b4-207">CHECKCONSTRAINTS.</span><span class="sxs-lookup"><span data-stu-id="098b4-207">CheckConstraints.</span></span> <span data-ttu-id="098b4-208">A definição desta propriedade como TRUE assegura que os dados que estão sendo inseridos nas tabelas não violem nenhuma restrição especificada (neste caso, as restrições PRIMARY KEY/FOREIGN KEY especificadas entre as tabelas Cust e CustOrder.</span><span class="sxs-lookup"><span data-stu-id="098b4-208">Setting this property to TRUE ensures that the data being inserted into the tables does not violate any constraints that have been specified on the tables (in this case the PRIMARY KEY/FOREIGN KEY constraints specified between the Cust and CustOrder tables).</span></span> <span data-ttu-id="098b4-209">Se houver uma violação de restrição, o carregamento em massa falhará.</span><span class="sxs-lookup"><span data-stu-id="098b4-209">If there is a constraint violation, the bulk load fails.</span></span>  
  
-   <span data-ttu-id="098b4-210">XMLFragment.</span><span class="sxs-lookup"><span data-stu-id="098b4-210">XMLFragment.</span></span> <span data-ttu-id="098b4-211">Esta propriedade deve ser definida como TRUE porque o exemplo de documento XML (fonte de dados) não contém nenhum elemento de alto nível único (e é, assim, um fragmento).</span><span class="sxs-lookup"><span data-stu-id="098b4-211">This property must be set to TRUE because the sample XML document (data source) contains no single, top-level element (and is thus a fragment).</span></span>  
  
 <span data-ttu-id="098b4-212">Este é o código VBScript:</span><span class="sxs-lookup"><span data-stu-id="098b4-212">This is the VBScript code:</span></span>  
  
```  
Dim objBL   
Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
  
objBL.CheckConstraints=true  
objBL.XMLFragment = True  
objBL.SchemaGen = True  
objBL.SGDropTables = True  
  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
Set objBL = Nothing  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="098b4-213">Para testar um exemplo de funcionamento</span><span class="sxs-lookup"><span data-stu-id="098b4-213">To test a working sample</span></span>  
  
1.  <span data-ttu-id="098b4-214">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-214">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="098b4-215">Adicione ao arquivo o esquema XSD fornecido no exemplo anterior, "Usando relações de cadeia no esquema para carregamento em massa do XML".</span><span class="sxs-lookup"><span data-stu-id="098b4-215">Add the XSD schema that is provided in the earlier example, "Using chain relationships in the schema to bulk load XML", to the file.</span></span>  
  
2.  <span data-ttu-id="098b4-216">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleXMLD.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-216">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="098b4-217">Adicione ao arquivo o documento XML fornecido no exemplo anterior, "Usando relações de cadeia no esquema para carregamento em massa do XML".</span><span class="sxs-lookup"><span data-stu-id="098b4-217">Add the XML document that is provided in the earlier example, "Using chain relationships in the schema to bulk load XML", to the file.</span></span> <span data-ttu-id="098b4-218">Remova o \<ROOT> elemento do documento (para torná-lo um fragmento).</span><span class="sxs-lookup"><span data-stu-id="098b4-218">Remove the \<ROOT> element from the document (to make it a fragment).</span></span>  
  
3.  <span data-ttu-id="098b4-219">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="098b4-219">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="098b4-220">Para este arquivo, adicione o código VBScript neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="098b4-220">To this file, add the VBScript code in this example.</span></span> <span data-ttu-id="098b4-221">Modifique a cadeia de conexão para fornecer o nome apropriado de servidor e de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="098b4-221">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="098b4-222">Especifique o caminho apropriado para os arquivos que são especificados como parâmetros para o método execute.</span><span class="sxs-lookup"><span data-stu-id="098b4-222">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
4.  <span data-ttu-id="098b4-223">Execute o código VBScript.</span><span class="sxs-lookup"><span data-stu-id="098b4-223">Execute the VBScript code.</span></span> <span data-ttu-id="098b4-224">O XML Bulk Load cria as tabelas necessárias na base do esquema de mapeamento fornecido e carrega em massa os dados nele.</span><span class="sxs-lookup"><span data-stu-id="098b4-224">The XML Bulk Load creates the necessary tables on the basis of the mapping schema that is provided and bulk loads the data in it.</span></span>  
  
## <a name="f-bulk-loading-from-a-stream"></a><span data-ttu-id="098b4-225">F.</span><span class="sxs-lookup"><span data-stu-id="098b4-225">F.</span></span> <span data-ttu-id="098b4-226">Carregando em massa de um fluxo</span><span class="sxs-lookup"><span data-stu-id="098b4-226">Bulk loading from a stream</span></span>  
 <span data-ttu-id="098b4-227">O método Execute do modelo de objeto de carregamento em massa XML usa dois parâmetros.</span><span class="sxs-lookup"><span data-stu-id="098b4-227">The Execute method of the XML Bulk Load object model takes two parameters.</span></span> <span data-ttu-id="098b4-228">O primeiro parâmetro é o arquivo de esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="098b4-228">The first parameter is the mapping schema file.</span></span> <span data-ttu-id="098b4-229">O segundo parâmetro fornece os dados XML que devem ser carregados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="098b4-229">The second parameter provides the XML data that is to be loaded in the database.</span></span> <span data-ttu-id="098b4-230">Há duas maneiras de passar os dados XML para o método Execute do carregamento em massa de XML:</span><span class="sxs-lookup"><span data-stu-id="098b4-230">There are two ways to pass the XML data to the Execute method of XML Bulk Load:</span></span>  
  
-   <span data-ttu-id="098b4-231">Especifique o nome do arquivo como o parâmetro.</span><span class="sxs-lookup"><span data-stu-id="098b4-231">Specify the file name as the parameter.</span></span>  
  
-   <span data-ttu-id="098b4-232">Transmita um fluxo que contenha os dados XML.</span><span class="sxs-lookup"><span data-stu-id="098b4-232">Pass a stream that contains the XML data.</span></span>  
  
 <span data-ttu-id="098b4-233">Este exemplo ilustra como carregar em massa de um fluxo.</span><span class="sxs-lookup"><span data-stu-id="098b4-233">This example illustrates how to bulk load from a stream.</span></span>  
  
 <span data-ttu-id="098b4-234">O VBScript primeiro executa uma instrução SELECT para recuperar informações de cliente da tabela Customers no banco de dados Northwind.</span><span class="sxs-lookup"><span data-stu-id="098b4-234">VBScript first executes a SELECT statement to retrieve customer information from the Customers table in the Northwind database.</span></span> <span data-ttu-id="098b4-235">Como a cláusula FOR XML é especificada (com a opção ELEMENTS) na instrução SELECT, a consulta retorna um documento XML centralizado no elemento desta forma:</span><span class="sxs-lookup"><span data-stu-id="098b4-235">Because the FOR XML clause is specified (with the ELEMENTS option) in the SELECT statement, the query returns an element-centric XML document of this form:</span></span>  
  
```  
<Customer>  
  <CustomerID>..</CustomerID>  
  <CompanyName>..</CompanyName>  
  <City>..</City>  
</Customer>  
...  
```  
  
 <span data-ttu-id="098b4-236">Em seguida, o script passa o XML como um fluxo para o método execute como seu segundo parâmetro.</span><span class="sxs-lookup"><span data-stu-id="098b4-236">The script then passes the XML as a stream to the Execute method as its second parameter.</span></span> <span data-ttu-id="098b4-237">O método execute carrega os dados em massa na tabela Cust.</span><span class="sxs-lookup"><span data-stu-id="098b4-237">The Execute method bulk loads the data into the Cust table.</span></span>  
  
 <span data-ttu-id="098b4-238">Como esse script define a propriedade SchemaGen como TRUE e a propriedade SGDropTables como TRUE, o carregamento em massa de XML cria a tabela Cust no banco de dados especificado.</span><span class="sxs-lookup"><span data-stu-id="098b4-238">Because this script sets the SchemaGen property to TRUE and SGDropTables property to TRUE, XML Bulk Load creates the Cust table in the specified database.</span></span> <span data-ttu-id="098b4-239">(Se a tabela já existir, o XML Bulk Load primeiro descartará a tabela e depois a recriará.)</span><span class="sxs-lookup"><span data-stu-id="098b4-239">(If the table already exists, it first drops the table and then re-creates it.)</span></span>  
  
 <span data-ttu-id="098b4-240">Este é exemplo de VBScript:</span><span class="sxs-lookup"><span data-stu-id="098b4-240">This is the VBScript example:</span></span>  
  
```  
Set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
Set objCmd = CreateObject("ADODB.Command")  
Set objConn = CreateObject("ADODB.Connection")  
Set objStrmOut = CreateObject ("ADODB.Stream")  
  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile     = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.SchemaGen        = True  
objBL.SGDropTables     = True  
objBL.XMLFragment      = True  
' Open a connection to the instance of SQL Server to get the source data.  
  
objConn.Open "provider=SQLOLEDB;server=(local);database=tempdb;integrated security=SSPI"  
Set objCmd.ActiveConnection = objConn  
objCmd.CommandText = "SELECT CustomerID, CompanyName, City FROM Customers FOR XML AUTO, ELEMENTS"  
  
' Open the return stream and execute the command.  
Const adCRLF = -1  
Const adExecuteStream = 1024  
objStrmOut.Open  
objStrmOut.LineSeparator = adCRLF  
objCmd.Properties("Output Stream").Value = objStrmOut  
objCmd.Execute , , adExecuteStream  
objStrmOut.Position = 0  
  
' Execute bulk load. Read source XML data from the stream.  
objBL.Execute "SampleSchema.xml", objStrmOut  
  
Set objBL = Nothing  
```  
  
 <span data-ttu-id="098b4-241">O seguinte esquema de mapeamento XSD fornece as informações necessárias para criar a tabela:</span><span class="sxs-lookup"><span data-stu-id="098b4-241">The following XSD mapping schema provides the necessary information to create the table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:element name="ROOT" sql:is-constant="true" >  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element ref="Customers"/>  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="Customers" sql:relation="Cust" >  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element name="CustomerID"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(5)"/>  
      <xsd:element name="CompanyName"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(40)"/>  
      <xsd:element name="City"  
                   type="xsd:string"  
                   sql:datatype="nvarchar(40)"/>  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="098b4-242">Este é esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="098b4-242">This is equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
    </ElementType>  
</Schema>  
```  
  
### <a name="opening-a-stream-on-an-existing-file"></a><span data-ttu-id="098b4-243">Abrindo um fluxo em um arquivo existente</span><span class="sxs-lookup"><span data-stu-id="098b4-243">Opening a Stream on an Existing File</span></span>  
 <span data-ttu-id="098b4-244">Você também pode abrir um fluxo em um arquivo de dados XML existente e passar o fluxo como um parâmetro para o método Execute (em vez de passar o nome do arquivo como o parâmetro).</span><span class="sxs-lookup"><span data-stu-id="098b4-244">You can also open a stream on an existing XML data file and pass the stream as a parameter to the Execute method (instead of passing the file name as the parameter).</span></span>  
  
 <span data-ttu-id="098b4-245">Este é um exemplo do Visual Basic de transmitir um fluxo como o parâmetro:</span><span class="sxs-lookup"><span data-stu-id="098b4-245">This is a Visual Basic example of passing a stream as the parameter:</span></span>  
  
```  
Private Sub Form_Load()  
Dim objBL As New SQLXMLBulkLoad  
Dim objStrm As New ADODB.Stream  
Dim objFileSystem As New Scripting.FileSystemObject  
Dim objFile As Scripting.TextStream  
  
MsgBox "Begin BulkLoad..."  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.SchemaGen = True  
objBL.SGDropTables = True  
' Here again a stream is specified that contains the source data   
' (instead of the file name). But this is just an illustration.  
' Usually this is useful if you have an XML data   
' stream that is created by some other means that you want to bulk   
' load. This example starts with an XML text file, so it may not be the   
' best to use a stream (you can specify the file name directly).  
' Here you could have specified the file name itself.   
Set objFile = objFileSystem.OpenTextFile("c:\SampleData.xml")  
objStrm.Open  
objStrm.WriteText objFile.ReadAll  
objStrm.Position = 0  
objBL.Execute "c:\SampleSchema.xml", objStrm  
  
Set objBL = Nothing  
MsgBox "Done."  
End Sub  
```  
  
 <span data-ttu-id="098b4-246">Para testar o aplicativo, use o seguinte documento XML em um arquivo (SampleData.xml) e o esquema XSD que é fornecido neste exemplo:</span><span class="sxs-lookup"><span data-stu-id="098b4-246">To test the application, use the following XML document in a file (SampleData.xml) and the XSD schema that is provided in this example:</span></span>  
  
 <span data-ttu-id="098b4-247">Estes são os dados de origem de XML (SampleData.xml):</span><span class="sxs-lookup"><span data-stu-id="098b4-247">This is the XML source data (SampleData.xml):</span></span>  
  
```  
<ROOT>  
  <Customers>  
    <CustomerID>1111</CustomerID>  
    <CompanyName>Hanari Carnes</CompanyName>  
    <City>NY</City>  
    <Order OrderID="1" />  
    <Order OrderID="2" />  
  </Customers>  
  
  <Customers>  
    <CustomerID>1112</CustomerID>  
    <CompanyName>Toms Spezialitten</CompanyName>  
     <City>LA</City>  
    <Order OrderID="3" />  
  </Customers>  
  <Customers>  
    <CustomerID>1113</CustomerID>  
    <CompanyName>Victuailles en stock</CompanyName>  
    <Order CustomerID= "4444" OrderID="4" />  
</Customers>  
</ROOT>  
```  
  
 <span data-ttu-id="098b4-248">Este é o esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="098b4-248">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
             <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
</Schema>  
```  
  
## <a name="g-bulk-loading-in-overflow-columns"></a><span data-ttu-id="098b4-249">G.</span><span class="sxs-lookup"><span data-stu-id="098b4-249">G.</span></span> <span data-ttu-id="098b4-250">Carregando em massa em colunas de estouro</span><span class="sxs-lookup"><span data-stu-id="098b4-250">Bulk loading in overflow columns</span></span>  
 <span data-ttu-id="098b4-251">Se o esquema de mapeamento especificar uma coluna de estouro usando a anotação `sql:overflow-field`, o XML Bulk Load copiará todos os dados não utilizados do documento de origem nesta coluna.</span><span class="sxs-lookup"><span data-stu-id="098b4-251">If the mapping schema specifies an overflow column by using the `sql:overflow-field` annotation, XML Bulk Load copies all unconsumed data from the source document into this column.</span></span>  
  
 <span data-ttu-id="098b4-252">Considere este esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="098b4-252">Consider this XSD schema:</span></span>  
  
```  
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
  <xsd:element name="Customers" sql:relation="Cust"  
                                sql:overflow-field="OverflowColumn" >  
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
          <xsd:attribute name="CustomerID" type="xsd:integer" />  
         </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="098b4-253">O esquema identifica uma coluna de estouro (OverflowColumn) para a tabela Cust.</span><span class="sxs-lookup"><span data-stu-id="098b4-253">The schema identifies an overflow column (OverflowColumn) for the Cust table.</span></span> <span data-ttu-id="098b4-254">Como resultado, todos os dados XML não consumidos para cada **\<Customer>** elemento são adicionados a essa coluna.</span><span class="sxs-lookup"><span data-stu-id="098b4-254">As a result, all unconsumed XML data for each **\<Customer>** element is added to this column.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="098b4-255">Todos os elementos abstratos (elementos para os quais **Abstract = "true"** é especificado) e todos os atributos proibidos (atributos para os quais **proibido = "true"** é especificado) são considerados estouro pelo carregamento em massa de XML e são adicionados à coluna de estouro, se especificado.</span><span class="sxs-lookup"><span data-stu-id="098b4-255">All abstract elements (elements for which **abstract="true"** is specified) and all prohibited attributes (attributes for which **prohibited="true"** is specified) are considered overflow by XML Bulk Load and are added to the overflow column, if specified.</span></span> <span data-ttu-id="098b4-256">(Caso contrário, eles serão ignorados.)</span><span class="sxs-lookup"><span data-stu-id="098b4-256">(Otherwise, they are ignored.)</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="098b4-257">Para testar um exemplo de funcionamento</span><span class="sxs-lookup"><span data-stu-id="098b4-257">To test a working sample</span></span>  
  
1.  <span data-ttu-id="098b4-258">Crie duas tabelas no banco de dados **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="098b4-258">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust (  
                  CustomerID     int         PRIMARY KEY,  
                  CompanyName    varchar(20) NOT NULL,  
                  City           varchar(20) DEFAULT 'Seattle',  
                  OverflowColumn nvarchar(200));  
    GO  
    CREATE TABLE CustOrder (  
                  OrderID    int PRIMARY KEY,  
                  CustomerID int FOREIGN KEY   
                                 REFERENCES Cust(CustomerID));  
    GO  
    ```  
  
2.  <span data-ttu-id="098b4-259">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-259">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="098b4-260">Adicione ao arquivo o esquema XSD que é fornecido neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="098b4-260">Add the XSD schema that is provided in this example to the file.</span></span>  
  
3.  <span data-ttu-id="098b4-261">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleXMLD.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-261">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="098b4-262">Adicione o seguinte documento XML ao arquivo:</span><span class="sxs-lookup"><span data-stu-id="098b4-262">Add the following XML document to the file:</span></span>  
  
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
         <![CDATA[LA]]>   
        <!-- <xyz><address>111 Maple, Seattle</address></xyz>   -->  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="098b4-263">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="098b4-263">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="098b4-264">Para esse arquivo, adicione o código do Microsoft Visual Basic Scripting Edition (VBScript) a seguir.</span><span class="sxs-lookup"><span data-stu-id="098b4-264">To this file, add the following Microsoft Visual Basic Scripting Edition (VBScript) code.</span></span> <span data-ttu-id="098b4-265">Modifique a cadeia de conexão para fornecer o nome apropriado de servidor e de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="098b4-265">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="098b4-266">Especifique o caminho apropriado para os arquivos que são especificados como parâmetros para o método execute.</span><span class="sxs-lookup"><span data-stu-id="098b4-266">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="098b4-267">Execute o código VBScript.</span><span class="sxs-lookup"><span data-stu-id="098b4-267">Execute the VBScript code.</span></span>  
  
 <span data-ttu-id="098b4-268">Este é o esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="098b4-268">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
    <ElementType name="Order" sql:relation="CustOrder" >  
      <AttributeType name="OrderID" />  
      <AttributeType name="CustomerID" />  
      <attribute type="OrderID" />  
      <attribute type="CustomerID" />  
    </ElementType>  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"   
                       sql:overflow-field="OverflowColumn"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
             <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
                foreign-relation="CustOrder" />  
      </element>  
   </ElementType>  
</Schema>  
```  
  
## <a name="h-specifying-the-file-path-for-temp-files-in-transaction-mode"></a><span data-ttu-id="098b4-269">H.</span><span class="sxs-lookup"><span data-stu-id="098b4-269">H.</span></span> <span data-ttu-id="098b4-270">Especificando o caminho do arquivo para arquivos temporários em modo de transação</span><span class="sxs-lookup"><span data-stu-id="098b4-270">Specifying the file path for temp files in transaction mode</span></span>  
 <span data-ttu-id="098b4-271">Quando você estiver carregando em massa no modo de transação (ou seja, quando a propriedade Transaction for definida como TRUE), você também deverá definir a propriedade TempFilePath quando qualquer uma das seguintes condições for verdadeira:</span><span class="sxs-lookup"><span data-stu-id="098b4-271">When you are bulk loading in transaction mode (that is, when the Transaction property is set to TRUE), you also must set the TempFilePath property when either of the following conditions is true:</span></span>  
  
-   <span data-ttu-id="098b4-272">Você estiver carregando em massa para um servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="098b4-272">You are bulk loading to a remote server.</span></span>  
  
-   <span data-ttu-id="098b4-273">Você desejar usar uma unidade local ou pasta alternativa (uma que não seja o caminho especificado pela variável de ambiente TEMP) para armazenar os arquivos temporários que são criados no modo de transação.</span><span class="sxs-lookup"><span data-stu-id="098b4-273">You want to use an alternate local drive or folder (one other than the path that is specified by the TEMP environment variable) to store the temporary files that are created in the transaction mode.</span></span>  
  
 <span data-ttu-id="098b4-274">Por exemplo, o código VBScript a seguir carrega em massa dados do arquivo SampleXMLData.xml para as tabelas de banco de dados no modo de transação.</span><span class="sxs-lookup"><span data-stu-id="098b4-274">For example, the following VBScript code bulk loads data from the SampleXMLData.xml file into the database tables in transaction mode.</span></span> <span data-ttu-id="098b4-275">A propriedade TempFilePath é especificada para definir o caminho para os arquivos temporários que são gerados no modo de transação.</span><span class="sxs-lookup"><span data-stu-id="098b4-275">The TempFilePath property is specified to set the path for the temporary files that are generated in transaction mode.</span></span>  
  
```  
set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
objBL.Transaction=True  
objBL.TempFilePath="\\Server\MyDir"  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
set objBL=Nothing  
```  
  
> [!NOTE]  
>  <span data-ttu-id="098b4-276">O caminho do arquivo temporário deve ser um local compartilhado que seja acessível à conta de serviço da instância de destino do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e à conta que está executando o aplicativo de carregamento em massa.</span><span class="sxs-lookup"><span data-stu-id="098b4-276">The temporary file path must be a shared location that is accessible to the service account of the target instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] and to the account that is running the bulk load application.</span></span> <span data-ttu-id="098b4-277">A menos que você esteja carregando em massa em um servidor local, o caminho do arquivo temporário deve ser um caminho UNC (como \\ \Servername\Sharename).</span><span class="sxs-lookup"><span data-stu-id="098b4-277">Unless you are bulk loading on a local server, the temporary file path must be a UNC path (such as \\\servername\sharename).</span></span>  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="098b4-278">Para testar um exemplo de funcionamento</span><span class="sxs-lookup"><span data-stu-id="098b4-278">To test a working sample</span></span>  
  
1.  <span data-ttu-id="098b4-279">Criar esta tabela no banco de dados **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="098b4-279">Create this table in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust (     CustomerID uniqueidentifier,   
          LastName  varchar(20));  
    GO  
    ```  
  
2.  <span data-ttu-id="098b4-280">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-280">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="098b4-281">Adicione o seguinte esquema XSD ao arquivo:</span><span class="sxs-lookup"><span data-stu-id="098b4-281">Add the following XSD schema to the file:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:attribute name="CustomerID"  type="xsd:string" />  
         <xsd:attribute name="LastName" type="xsd:string" />  
       </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="098b4-282">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleXMLD.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-282">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="098b4-283">Adicione o seguinte documento XML ao arquivo:</span><span class="sxs-lookup"><span data-stu-id="098b4-283">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
    <Customers CustomerID="6F9619FF-8B86-D011-B42D-00C04FC964FF"   
               LastName="Smith" />  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="098b4-284">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como ValidateAndBulkload.vbs.</span><span class="sxs-lookup"><span data-stu-id="098b4-284">Create a file in your preferred text or XML editor, and save it as ValidateAndBulkload.vbs.</span></span> <span data-ttu-id="098b4-285">Para este arquivo, adicione o código VBScript a seguir.</span><span class="sxs-lookup"><span data-stu-id="098b4-285">To this file, add the following VBScript code.</span></span> <span data-ttu-id="098b4-286">Modifique a cadeia de conexão para fornecer o nome apropriado de servidor e de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="098b4-286">Modify the connection string to provide the appropriate server and database name.</span></span> <span data-ttu-id="098b4-287">Especifique o caminho apropriado para os arquivos que são especificados como parâmetros para o método execute.</span><span class="sxs-lookup"><span data-stu-id="098b4-287">Specify the appropriate path for the files that are specified as parameters to the Execute method.</span></span> <span data-ttu-id="098b4-288">Especifique também o caminho apropriado para a propriedade TempFilePath.</span><span class="sxs-lookup"><span data-stu-id="098b4-288">Also specify the appropriate path for the TempFilePath property.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=localhost;database=tempdb;integrated security=SSPI"  
    objBL.ErrorLogFile = "c:\error.log"  
    objBL.CheckConstraints = True  
    objBL.Transaction=True  
    objBL.TempFilePath="\\server\folder"  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="098b4-289">Execute o código VBScript.</span><span class="sxs-lookup"><span data-stu-id="098b4-289">Execute the VBScript code.</span></span>  
  
     <span data-ttu-id="098b4-290">O esquema deve especificar o correspondente `sql:datatype` para o atributo **CustomerID** quando o valor de **CustomerID** é especificado como um GUID que inclui chaves ({e}), como:</span><span class="sxs-lookup"><span data-stu-id="098b4-290">The schema must specify the corresponding `sql:datatype` for the **CustomerID** attribute when the value for **CustomerID** is specified as a GUID that includes braces ({ and }), such as:</span></span>  
  
    ```  
    <ROOT>  
    <Customers CustomerID="{6F9619FF-8B86-D011-B42D-00C04FC964FF}"   
               LastName="Smith" />  
    </ROOT>  
    ```  
  
     <span data-ttu-id="098b4-291">Este é o esquema atualizado:</span><span class="sxs-lookup"><span data-stu-id="098b4-291">This is the updated schema:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
  
      <xsd:element name="Customers" sql:relation="Cust" >  
       <xsd:complexType>  
         <xsd:attribute name="CustomerID"  type="xsd:string"   
                        sql:datatype="uniqueidentifier" />  
         <xsd:attribute name="LastName" type="xsd:string" />  
       </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
     <span data-ttu-id="098b4-292">Quando `sql:datatype` é especificado identificando o tipo de coluna como `uniqueidentifier` , a operação de carregamento em massa remove as chaves ({e}) do valor **CustomerID** antes de inseri-la na coluna.</span><span class="sxs-lookup"><span data-stu-id="098b4-292">When `sql:datatype` is specified identifying the column type as `uniqueidentifier`, the bulk load operation removes the braces ({ and }) from the **CustomerID** value before inserting it in the column.</span></span>  
  
 <span data-ttu-id="098b4-293">Este é o esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="098b4-293">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
<ElementType name="ROOT" sql:is-constant="1">  
      <element type="Customers" />  
</ElementType>  
<ElementType name="Customers" sql:relation="Cust" >  
  <AttributeType name="CustomerID"  sql:datatype="uniqueidentifier" />  
  <AttributeType name="LastName"   />  
  
  <attribute type="CustomerID" />  
  <attribute type="LastName"   />  
</ElementType>  
</Schema>  
```  
  
## <a name="i-using-an-existing-database-connection-with-the-connectioncommand-property"></a><span data-ttu-id="098b4-294">I.</span><span class="sxs-lookup"><span data-stu-id="098b4-294">I.</span></span> <span data-ttu-id="098b4-295">Usando uma conexão de banco de dados existente com a propriedade ConnectionCommand</span><span class="sxs-lookup"><span data-stu-id="098b4-295">Using an existing database connection with the ConnectionCommand property</span></span>  
 <span data-ttu-id="098b4-296">Você pode usar uma conexão existente do ADO para carregamento em massa do XML.</span><span class="sxs-lookup"><span data-stu-id="098b4-296">You can use an existing ADO connection to bulk load XML.</span></span> <span data-ttu-id="098b4-297">Isto será útil se o XML Bulk Load for apenas uma de muitas operações que serão executados em uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="098b4-297">This is useful if XML Bulk Load is just one of many operations that will be performed on a data source.</span></span>  
  
 <span data-ttu-id="098b4-298">A propriedade ConnectionCommand permite que você use uma conexão ADO existente usando um objeto de comando ADO.</span><span class="sxs-lookup"><span data-stu-id="098b4-298">The ConnectionCommand property enables you to use an existing ADO connection by using an ADO command object.</span></span> <span data-ttu-id="098b4-299">Isso é ilustrado no seguinte exemplo do Visual Basic:</span><span class="sxs-lookup"><span data-stu-id="098b4-299">This is illustrated in the following Visual Basic example:</span></span>  
  
```  
Private Sub Form_Load()  
Dim objBL As New SQLXMLBulkLoad4  
Dim objCmd As New ADODB.Command  
Dim objConn As New ADODB.Connection  
  
'Open a connection to an instance of SQL Server.  
objConn.Open "provider=SQLOLEDB;data source=(local);database=tempdb;integrated security=SSPI"  
'Ask the Command object to use the connection just established.  
Set objCmd.ActiveConnection = objConn  
  
'Tell Bulk Load to use the active command object that is using the Connection obj.  
objBL.ConnectionCommand = objCmd  
objBL.ErrorLogFile = "c:\error.log"  
objBL.CheckConstraints = True  
'The Transaction property must be set to True if you use ConnectionCommand.  
objBL.Transaction = True  
objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
Set objBL = Nothing  
End Sub  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="098b4-300">Para testar um exemplo de funcionamento</span><span class="sxs-lookup"><span data-stu-id="098b4-300">To test a working sample</span></span>  
  
1.  <span data-ttu-id="098b4-301">Crie duas tabelas no banco de dados **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="098b4-301">Create two tables in **tempdb** database:</span></span>  
  
    ```  
    USE tempdb;  
    CREATE TABLE Cust(  
                   CustomerID   varchar(5) PRIMARY KEY,  
                   CompanyName  varchar(30),  
                   City         varchar(20));  
    GO  
    CREATE TABLE CustOrder(  
                   CustomerID  varchar(5) references Cust (CustomerID),  
                   OrderID     varchar(5) PRIMARY KEY);  
    GO  
    ```  
  
2.  <span data-ttu-id="098b4-302">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-302">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="098b4-303">Adicione o seguinte esquema XSD ao arquivo:</span><span class="sxs-lookup"><span data-stu-id="098b4-303">Add the following XSD schema to the file:</span></span>  
  
    ```  
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
      <xsd:element name="ROOT" sql:is-constant="true" >  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element ref="Customers" />  
          </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
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
              <xsd:attribute name="CustomerID" type="xsd:integer" />  
             </xsd:complexType>  
           </xsd:element>  
         </xsd:sequence>  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="098b4-304">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleXMLD.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-304">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="098b4-305">Adicione o seguinte documento XML ao arquivo:</span><span class="sxs-lookup"><span data-stu-id="098b4-305">Add the following XML document to the file:</span></span>  
  
    ```  
    <ROOT>  
      <Customers>  
        <CustomerID>1111</CustomerID>  
        <CompanyName>Hanari Carnes</CompanyName>  
        <City>NY</City>  
        <Order OrderID="1" />  
        <Order OrderID="2" />  
      </Customers>  
  
      <Customers>  
        <CustomerID>1112</CustomerID>  
        <CompanyName>Toms Spezialitten</CompanyName>  
         <City>LA</City>  
        <Order OrderID="3" />  
      </Customers>  
      <Customers>  
        <CustomerID>1113</CustomerID>  
        <CompanyName>Victuailles en stock</CompanyName>  
        <Order OrderID="4" />  
    </Customers>  
    </ROOT>  
    ```  
  
4.  <span data-ttu-id="098b4-306">Crie um aplicativo Visual Basic (EXE Padrão) e o código anterior.</span><span class="sxs-lookup"><span data-stu-id="098b4-306">Create a Visual Basic (Standard EXE) application and the preceding code.</span></span> <span data-ttu-id="098b4-307">Adicione estas referências ao projeto:</span><span class="sxs-lookup"><span data-stu-id="098b4-307">Add these references to the project:</span></span>  
  
    ```  
    Microsoft XML BulkLoad for SQL Server 4.0 Type Library  
    Microsoft ActiveX Data objects 2.6 Library  
    ```  
  
5.  <span data-ttu-id="098b4-308">Execute o aplicativo.</span><span class="sxs-lookup"><span data-stu-id="098b4-308">Execute the application.</span></span>  
  
 <span data-ttu-id="098b4-309">Este é o esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="098b4-309">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"   
        xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
        xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
  
   <ElementType name="CustomerID" dt:type="int" />  
   <ElementType name="CompanyName" dt:type="string" />  
   <ElementType name="City" dt:type="string" />  
  
   <ElementType name="root" sql:is-constant="1">  
      <element type="Customers" />  
   </ElementType>  
  
   <ElementType name="Customers" sql:relation="Cust"  >  
      <element type="CustomerID" sql:field="CustomerID" />  
      <element type="CompanyName" sql:field="CompanyName" />  
      <element type="City" sql:field="City" />  
      <element type="Order" >  
         <sql:relationship  
                key-relation="Cust"  
                key="CustomerID"  
                foreign-key="CustomerID"  
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
  
## <a name="j-bulk-loading-in-xml-data-type-columns"></a><span data-ttu-id="098b4-310">J.</span><span class="sxs-lookup"><span data-stu-id="098b4-310">J.</span></span> <span data-ttu-id="098b4-311">Carregamento em massa em colunas de tipo de dados xml</span><span class="sxs-lookup"><span data-stu-id="098b4-311">Bulk loading in xml Data Type columns</span></span>  
 <span data-ttu-id="098b4-312">Se o esquema de mapeamento especificar uma coluna de [tipo de dados XML](/sql/t-sql/xml/xml-transact-sql) usando a `sql:datatype="xml"` anotação, o carregamento em massa de XML poderá copiar elementos filho XML para o campo mapeado do documento de origem para esta coluna.</span><span class="sxs-lookup"><span data-stu-id="098b4-312">If the mapping schema specifies a [xml data type](/sql/t-sql/xml/xml-transact-sql) column by using the `sql:datatype="xml"` annotation, XML Bulk Load can copy XML child elements for the mapped field from the source document into this column.</span></span>  
  
 <span data-ttu-id="098b4-313">Considere o esquema XSD a seguir, o qual mapeia uma exibição da tabela Production.ProductModel no banco de dados AdventureWorks de exemplo.</span><span class="sxs-lookup"><span data-stu-id="098b4-313">Consider the following XSD schema, which maps a view of the Production.ProductModel table in the AdventureWorks sample database.</span></span> <span data-ttu-id="098b4-314">Nesta tabela, o campo CatalogDescription do `xml` tipo de dados é mapeado para um **\<Desc>** elemento usando as `sql:field` `sql:datatype="xml"` anotações e.</span><span class="sxs-lookup"><span data-stu-id="098b4-314">In this table, the CatalogDescription field of `xml` data type is mapped to a **\<Desc>** element using the `sql:field` and `sql:datatype="xml"` annotations.</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
           xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
           xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">   
  <xsd:element name="ProductModel"  sql:relation="Production.ProductModel" >  
    <xsd:complexType>  
      <xsd:sequence>  
        <xsd:element name="Name" type="xs:string"></xsd:element>  
        <xsd:element name="Desc" sql:field="CatalogDescription" sql:datatype="xml">  
        <xsd:complexType>  
          <xsd:sequence>  
            <xsd:element name="ProductDescription">  
              <xsd:complexType>  
                <xsd:sequence>  
                  <xsd:element name="Summary" type="xs:anyType"/>  
                </xsd:sequence>  
              </xsd:complexType>  
            </xsd:element>  
          </xsd:sequence>  
        </xsd:complexType>  
        </xsd:element>   
     </xsd:sequence>  
     <xsd:attribute name="ProductModelID" sql:field="ProductModelID" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
#### <a name="to-test-a-working-sample"></a><span data-ttu-id="098b4-315">Para testar um exemplo de funcionamento</span><span class="sxs-lookup"><span data-stu-id="098b4-315">To test a working sample</span></span>  
  
1.  <span data-ttu-id="098b4-316">Verifique se o banco de dados AdventureWorks de exemplo está instalado.</span><span class="sxs-lookup"><span data-stu-id="098b4-316">Verify that the AdventureWorks sample database is installed.</span></span>  
  
2.  <span data-ttu-id="098b4-317">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-317">Create a file in your preferred text or XML editor, and save it as SampleSchema.xml.</span></span> <span data-ttu-id="098b4-318">Copie o esquema XSD anterior, cole-o no arquivo e salve-o.</span><span class="sxs-lookup"><span data-stu-id="098b4-318">Copy the XSD schema above and paste it into the file and save it.</span></span>  
  
3.  <span data-ttu-id="098b4-319">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como SampleXMLD.xml.</span><span class="sxs-lookup"><span data-stu-id="098b4-319">Create a file in your preferred text or XML editor, and save it as SampleXMLData.xml.</span></span> <span data-ttu-id="098b4-320">Copie o documento XML a seguir, cole-o no arquivo e salve-o na mesma pasta que foi usada para a etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="098b4-320">Copy the following XML document below and paste it into the file and save it in the same folder as was used for the previous step.</span></span>  
  
    ```  
    <ProductModel ProductModelID="2005">  
        <Name>Mountain-100 (2005 model)</Name>  
        <Desc><?xml-stylesheet href="ProductDescription.xsl" type="text/xsl"?>  
            <p1:ProductDescription xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription"   
                  xmlns:wm="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"   
                  xmlns:wf="http://www.adventure-works.com/schemas/OtherFeatures"   
                  xmlns:html="http://www.w3.org/1999/xhtml"   
                  xmlns="">  
                <p1:Summary>  
                    <html:p>Our top-of-the-line competition mountain bike.   
          Performance-enhancing options include the innovative HL Frame,   
          super-smooth front suspension, and traction for all terrain.  
                            </html:p>  
                </p1:Summary>  
                <p1:Manufacturer>  
                    <p1:Name>AdventureWorks</p1:Name>  
                    <p1:Copyright>2002-2005</p1:Copyright>  
                    <p1:ProductURL>HTTP://www.Adventure-works.com</p1:ProductURL>  
                </p1:Manufacturer>  
                <p1:Features>These are the product highlights.   
                     <wm:Warranty>  
                        <wm:WarrantyPeriod>3 years</wm:WarrantyPeriod>  
                        <wm:Description>parts and labor</wm:Description>  
                    </wm:Warranty><wm:Maintenance>  
                        <wm:NoOfYears>10 years</wm:NoOfYears>  
                        <wm:Description>maintenance contract available through your dealer or any AdventureWorks retail store.</wm:Description>  
                    </wm:Maintenance><wf:wheel>High performance wheels.</wf:wheel><wf:saddle>  
                        <html:i>Anatomic design</html:i> and made from durable leather for a full-day of riding in comfort.</wf:saddle><wf:pedal>  
                        <html:b>Top-of-the-line</html:b> clipless pedals with adjustable tension.</wf:pedal><wf:BikeFrame>Each frame is hand-crafted in our Bothell facility to the optimum diameter   
          and wall-thickness required of a premium mountain frame.   
          The heat-treated welded aluminum frame has a larger diameter tube that absorbs the bumps.</wf:BikeFrame><wf:crankset> Triple crankset; alumunim crank arm; flawless shifting. </wf:crankset></p1:Features>  
                <!-- add one or more of these elements... one for each specific product in this product model -->  
                <p1:Picture>  
                    <p1:Angle>front</p1:Angle>  
                    <p1:Size>small</p1:Size>  
                    <p1:ProductPhotoID>118</p1:ProductPhotoID>  
                </p1:Picture>  
                <!-- add any tags in <specifications> -->  
                <p1:Specifications> These are the product specifications.  
                       <Material>Almuminum Alloy</Material><Color>Available in most colors</Color><ProductLine>Mountain bike</ProductLine><Style>Unisex</Style><RiderExperience>Advanced to Professional riders</RiderExperience></p1:Specifications>  
            </p1:ProductDescription>  
        </Desc>  
    </ProductModel>  
    ```  
  
4.  <span data-ttu-id="098b4-321">Crie um arquivo em seu editor de texto ou editor XML preferido e salve-o como BulkloadXml.vbs.</span><span class="sxs-lookup"><span data-stu-id="098b4-321">Create a file in your preferred text or XML editor, and save it as BulkloadXml.vbs.</span></span> <span data-ttu-id="098b4-322">Copie o código VBScript a seguir e cole-o no arquivo.</span><span class="sxs-lookup"><span data-stu-id="098b4-322">Copy the following VBScript code and paste it into the file.</span></span> <span data-ttu-id="098b4-323">Salve-o na mesma pasta que foi usada para os arquivos de dados e de esquema XML anteriores.</span><span class="sxs-lookup"><span data-stu-id="098b4-323">Save it in the same folder as was used for the previous XML data and schema files.</span></span>  
  
    ```  
    set objBL = CreateObject("SQLXMLBulkLoad.SQLXMLBulkload.4.0")  
    objBL.ConnectionString = "provider=SQLOLEDB;data source=MyServer;database=AdventureWorks;integrated security=SSPI"  
  
    Dim fso, sAppPath  
    Set fso = CreateObject("Scripting.FileSystemObject")   
    sAppPath = fso.GetFolder(".")   
  
    objBL.ErrorLogFile = sAppPath & "\error.log"  
  
    'Execute XML bulkload using file.  
    objBL.Execute "SampleSchema.xml", "SampleXMLData.xml"  
    set objBL=Nothing  
    ```  
  
5.  <span data-ttu-id="098b4-324">Execute o script BulkloadXml.vbs.</span><span class="sxs-lookup"><span data-stu-id="098b4-324">Execute the BulkloadXml.vbs script.</span></span>  
  
  
