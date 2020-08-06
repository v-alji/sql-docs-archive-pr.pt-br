---
title: Executando um DiffGram usando classes gerenciadas SQLXML | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], Managed Classes
- SQLXML Managed Classes, DiffGrams
- Managed Classes [SQLXML], DiffGrams
- SQLXML, Managed Classes
ms.assetid: 81c687ca-8c9f-4f58-801f-8dabcc508a06
author: rothja
ms.author: jroth
ms.openlocfilehash: f36127c37eea73a2872d4bf0aef7172a88e430a0
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574596"
---
# <a name="executing-a-diffgram-by-using-sqlxml-managed-classes"></a><span data-ttu-id="43072-102">Executando um DiffGram usando as classes gerenciadas SQLXML</span><span class="sxs-lookup"><span data-stu-id="43072-102">Executing a DiffGram by Using SQLXML Managed Classes</span></span>
  <span data-ttu-id="43072-103">Este exemplo mostra como executar um arquivo DiffGram no ambiente de [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework para aplicar atualizações de dados a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tabelas usando classes gerenciadas SQLXML (Microsoft. Data. SQLXML).</span><span class="sxs-lookup"><span data-stu-id="43072-103">This example shows how to execute a DiffGram file in the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] .NET Framework environment to apply data updates to [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tables using SQLXML Managed Classes (Microsoft.Data.SqlXml).</span></span>  
  
 <span data-ttu-id="43072-104">Neste exemplo, o DiffGram atualiza as informações do cliente (CompanyName e ContactName) de ALFKI do cliente.</span><span class="sxs-lookup"><span data-stu-id="43072-104">In this example, the DiffGram updates customer information (CompanyName and ContactName) for customer ALFKI.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
           xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
           xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
      <Customer diffgr:id="Customer1"   
                msdata:rowOrder="0" diffgr:hasChanges="modified"   
                CustomerID="ALFKI">  
          <CompanyName>Bottom Dollar Markets</CompanyName>  
          <ContactName>Antonio Moreno</ContactName>  
      </Customer>  
    </DataInstance>  
    <diffgr:before>  
     <Customer diffgr:id="Customer1"   
               msdata:rowOrder="0"   
               CustomerID="ALFKI">  
        <CompanyName>Alfreds Futterkiste</CompanyName>  
        <ContactName>Maria Anders</ContactName>  
      </Customer>  
    </diffgr:before>  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="43072-105">O **\<before>** bloco inclui um **\<Customer>** elemento (**diffgr: ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="43072-105">The **\<before>** block includes a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="43072-106">O **\<DataInstance>** bloco inclui o **\<Customer>** elemento correspondente com a mesma **ID**. O **\<customer>** elemento em **\<NewDataSet>** também especifica **diffgr: hasChanges = "Modified"**.</span><span class="sxs-lookup"><span data-stu-id="43072-106">The **\<DataInstance>** block includes the corresponding **\<Customer>** element with same **id**. The **\<customer>** element in the **\<NewDataSet>** also specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="43072-107">Isso indica uma operação de atualização e o registro de cliente na tabela Cust é atualizado adequadamente.</span><span class="sxs-lookup"><span data-stu-id="43072-107">This indicates an update operation, and the customer record in the Cust table is updated accordingly.</span></span> <span data-ttu-id="43072-108">Observe que, se o atributo **diffgr: hasChanges** não for especificado, a lógica de processamento de DiffGram ignorará esse elemento e nenhuma atualização será executada.</span><span class="sxs-lookup"><span data-stu-id="43072-108">Note that if the **diffgr:hasChanges** attribute is not specified, the DiffGram processing logic ignores this element and no updates are performed.</span></span>  
  
 <span data-ttu-id="43072-109">Este é o código para um aplicativo de tutorial em C# que mostra como usar as classes gerenciadas SQLXML para executar o DiffGram acima e atualizar duas tabelas (Cust, Ord) que você também criará no banco de dados **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="43072-109">The following is code for a C# tutorial application that shows how to use the SQLXML Managed Classes to execute the above DiffGram and update two tables (Cust, Ord) you will also create in the **tempdb** database.</span></span>  
  
```  
using System;  
using System.Data;  
using Microsoft.Data.SqlXml;  
using System.IO;  
class Test  
{  
   static string ConnString = "Provider=SQLOLEDB;Server=MyServer;database=tempdb;Integrated Security=SSPI;";  
   public static int testParams()  
   {  
      SqlXmlAdapter ad;  
      // Need a memory stream to hold diff gram temporarily  
      MemoryStream ms = new MemoryStream();  
      SqlXmlCommand cmd = new SqlXmlCommand(ConnString);  
      cmd.RootTag = "ROOT";  
      cmd.CommandStream = new FileStream("MyDiffgram.xml", FileMode.Open, FileAccess.Read);  
      cmd.CommandType = SqlXmlCommandType.DiffGram;  
      cmd.SchemaPath = "DiffGramSchema.xml";  
      // Load data set  
      DataSet ds = new DataSet();  
      ad = new SqlXmlAdapter(cmd);  
      ad.Fill(ds);  
      ad.Update(ds);  
      return 0;  
   }  
   public static int Main(String[] args)  
   {  
      testParams();  
      return 0;  
   }  
}  
```  
  
### <a name="to-test-the-application"></a><span data-ttu-id="43072-110">Para testar o aplicativo</span><span class="sxs-lookup"><span data-stu-id="43072-110">To test the application</span></span>  
  
1.  <span data-ttu-id="43072-111">Verifique se o .NET Framework está instalado em seu computador.</span><span class="sxs-lookup"><span data-stu-id="43072-111">Ensure that the .NET Framework is installed on your computer.</span></span>  
  
2.  <span data-ttu-id="43072-112">Salve o seguinte esquema XSD (DiffGramSchema.xml) em uma pasta:</span><span class="sxs-lookup"><span data-stu-id="43072-112">Save the following XSD schema (DiffGramSchema.xml) in a folder:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
     <xsd:annotation>  
      <xsd:documentation>  
        Diffgram Customers/Orders Schema.  
      </xsd:documentation>  
      <xsd:appinfo>  
           <sql:relationship name="CustomersOrders"   
                      parent="Cust"  
                      parent-key="CustomerID"  
                      child-key="CustomerID"  
                      child="Ord"/>  
      </xsd:appinfo>  
     </xsd:annotation>  
     <xsd:element name="Customer" sql:relation="Cust">  
      <xsd:complexType>  
        <xsd:sequence>  
          <xsd:element name="CompanyName"    type="xsd:string"/>  
          <xsd:element name="ContactName"    type="xsd:string"/>  
           <xsd:element name="Order" sql:relation="Ord" sql:relationship="CustomersOrders">  
            <xsd:complexType>  
              <xsd:attribute name="OrderID" type="xsd:int" sql:field="OrderID"/>  
              <xsd:attribute name="CustomerID" type="xsd:string"/>  
            </xsd:complexType>  
          </xsd:element>  
        </xsd:sequence>  
        <xsd:attribute name="CustomerID" type="xsd:string" sql:field="CustomerID"/>  
      </xsd:complexType>  
     </xsd:element>  
    </xsd:schema>  
    ```  
  
3.  <span data-ttu-id="43072-113">Crie essas tabelas no banco de dados **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="43072-113">Create these tables in the **tempdb** database.</span></span>  
  
    ```  
    CREATE TABLE Cust(  
            CustomerID  nchar(5) Primary Key,  
            CompanyName nvarchar(40) NOT NULL ,  
            ContactName nvarchar(60) NULL)  
    GO  
  
    CREATE TABLE Ord(  
       OrderID    int Primary Key,  
       CustomerID nchar(5) Foreign Key REFERENCES Cust(CustomerID))  
    GO  
    ```  
  
4.  <span data-ttu-id="43072-114">Adicione estes dados de exemplo:</span><span class="sxs-lookup"><span data-stu-id="43072-114">Add this sample data:</span></span>  
  
    ```  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ALFKI', N'Alfreds Futterkiste', N'Maria Anders')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANATR', N'Ana Trujillo Emparedados y helados', N'Ana Trujillo')  
    INSERT INTO Cust(CustomerID, CompanyName, ContactName) VALUES  
         (N'ANTON', N'Antonio Moreno Taquer??a', N'Antonio Moreno')  
  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(1, N'ALFKI')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(2, N'ANATR')  
    INSERT INTO Ord(OrderID, CustomerID) VALUES(3, N'ANTON')  
    ```  
  
5.  <span data-ttu-id="43072-115">Copie o DiffGram acima e cole em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="43072-115">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="43072-116">Salve o arquivo como MyDiffGram.xml na mesma pasta usada na etapa 1.</span><span class="sxs-lookup"><span data-stu-id="43072-116">Save the file as MyDiffGram.xml in the same folder used in step 1.</span></span>  
  
6.  <span data-ttu-id="43072-117">Salve o código C# (DiffgramSample.cs) fornecido acima na mesma pasta em que foram armazenados DiffGramSchema.xml e MyDiffGram.xml nas etapas anteriores.</span><span class="sxs-lookup"><span data-stu-id="43072-117">Save the C# code (DiffgramSample.cs) that is provided above in the same folder in which the DiffGramSchema.xml and MyDiffGram.xml were stored in previous steps.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="43072-118">Será necessário atualizar o nome da instância do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] na cadeia de conexão, de '`MyServer`' para o nome real da sua instância instalada do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="43072-118">You will need to update the name of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance in the connection string from '`MyServer`' to the actual name of your installed instance of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="43072-119">Se você armazenar os arquivos em uma pasta diferente, será necessário editar o código e especificar o caminho do diretório apropriado para o esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="43072-119">If you store the files in a different folder, you will have to edit the code and specify the appropriate directory path for the mapping schema.</span></span>  
  
7.  <span data-ttu-id="43072-120">Compile o código.</span><span class="sxs-lookup"><span data-stu-id="43072-120">Compile the code.</span></span> <span data-ttu-id="43072-121">Para compilar o código no prompt de comando, use:</span><span class="sxs-lookup"><span data-stu-id="43072-121">To compile the code at the command prompt, use:</span></span>  
  
    ```  
    csc /reference:Microsoft.Data.SqlXML.dll DiffgramSample.cs  
    ```  
  
     <span data-ttu-id="43072-122">Isso cria um executável (DiffgramSample.exe).</span><span class="sxs-lookup"><span data-stu-id="43072-122">This creates an executable (DiffgramSample.exe).</span></span>  
  
8.  <span data-ttu-id="43072-123">No prompt de comando, execute DiffgramSample.exe.</span><span class="sxs-lookup"><span data-stu-id="43072-123">At the command prompt, execute DiffgramSample.exe.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="43072-124">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="43072-124">See Also</span></span>  
 [<span data-ttu-id="43072-125">Exemplos de DiffGram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="43072-125">DiffGram Examples &#40;SQLXML 4.0&#41;</span></span>](diffgram-examples-sqlxml-4-0.md)  
  
  
