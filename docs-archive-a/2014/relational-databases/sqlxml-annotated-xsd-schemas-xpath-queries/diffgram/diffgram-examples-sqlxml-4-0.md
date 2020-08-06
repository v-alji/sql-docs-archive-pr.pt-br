---
title: Exemplos de DiffGram (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- DiffGrams [SQLXML], examples
- examples [SQLXML], DiffGram
- diffgr:parentID
- parentID annotation
ms.assetid: fc148583-dfd3-4efb-a413-f47b150b0975
author: rothja
ms.author: jroth
ms.openlocfilehash: 04fb355af01f9853149a84af72471375d9135468
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574604"
---
# <a name="diffgram-examples-sqlxml-40"></a><span data-ttu-id="c809f-102">Exemplos de DiffGram (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="c809f-102">DiffGram Examples (SQLXML 4.0)</span></span>
  <span data-ttu-id="c809f-103">Os exemplos deste tópico consistem em DiffGrams que executam operações de inserção, atualização e exclusão no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c809f-103">The examples in this topic consist of DiffGrams that perform insert, update, and delete operations to the database.</span></span> <span data-ttu-id="c809f-104">Antes de usar os exemplos, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c809f-104">Before using the examples, note the following:</span></span>  
  
-   <span data-ttu-id="c809f-105">Os exemplos usarão duas tabelas (Cust e Ord) que devem ser criadas se você quiser testar os exemplos de DiffGram:</span><span class="sxs-lookup"><span data-stu-id="c809f-105">The examples use two tables (Cust and Ord) that must be created if you want to test the DiffGram examples:</span></span>  
  
    ```  
    Cust(CustomerID, CompanyName, ContactName)  
    Ord(OrderID, CustomerID)  
    ```  
  
-   <span data-ttu-id="c809f-106">A maioria dos exemplos deste tópico usa o seguinte Esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="c809f-106">Most of the examples in this topic use the following XSD Schema:</span></span>  
  
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
  
     <span data-ttu-id="c809f-107">Salve este esquema como DiffGramSchema.xml na mesma pasta em que você salva outros arquivos usados nos exemplos.</span><span class="sxs-lookup"><span data-stu-id="c809f-107">Save this schema as DiffGramSchema.xml in the same folder where you save other files used in the examples.</span></span>  
  
## <a name="a-deleting-a-record-by-using-a-diffgram"></a><span data-ttu-id="c809f-108">a.</span><span class="sxs-lookup"><span data-stu-id="c809f-108">A.</span></span> <span data-ttu-id="c809f-109">Excluindo um registro usando um DiffGram</span><span class="sxs-lookup"><span data-stu-id="c809f-109">Deleting a record by using a DiffGram</span></span>  
 <span data-ttu-id="c809f-110">O DiffGram, neste exemplo, exclui um registro de cliente (com CustomerID ALFKI) da tabela Cust e exclui o registro de pedido correspondente (cuja OrderID é 1) da tabela Ord.</span><span class="sxs-lookup"><span data-stu-id="c809f-110">The DiffGram in this example deletes a customer (whose CustomerID is ALFKI) record from the Cust table and deletes the corresponding order record (whose OrderID is 1) from the Ord table.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
           xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
           xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance/>  
  
    <diffgr:before>  
        <Order diffgr:id="Order1"   
               msdata:rowOrder="0"   
               CustomerID="ALFKI"   
               OrderID="1"/>  
        <Customer diffgr:id="Customer1"   
                  msdata:rowOrder="0"   
                  CustomerID="ALFKI">  
           <CompanyName>Alfreds Futterkiste</CompanyName>  
           <ContactName>Maria Anders</ContactName>  
        </Customer>  
    </diffgr:before>  
    <msdata:errors/>  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="c809f-111">No **\<before>** bloco, há um **\<Order>** elemento (**diffgr: ID = "Order1"**) e um **\<Customer>** elemento (**diffgr: ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="c809f-111">In the **\<before>** block, there is an **\<Order>** element (**diffgr:id="Order1"**) and a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="c809f-112">Esses elementos representam registros existentes no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c809f-112">These elements represent existing records in the database.</span></span> <span data-ttu-id="c809f-113">O **\<DataInstance>** elemento não tem os registros correspondentes (com o mesmo **diffgr: ID**).</span><span class="sxs-lookup"><span data-stu-id="c809f-113">The **\<DataInstance>** element does not have the corresponding records (with the same **diffgr:id**).</span></span> <span data-ttu-id="c809f-114">Isso indica um operação de exclusão.</span><span class="sxs-lookup"><span data-stu-id="c809f-114">This indicates a delete operation.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="c809f-115">Para testar o DiffGram</span><span class="sxs-lookup"><span data-stu-id="c809f-115">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="c809f-116">Crie essas tabelas no banco de dados **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="c809f-116">Create these tables in the **tempdb** database.</span></span>  
  
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
  
2.  <span data-ttu-id="c809f-117">Adicione estes dados de exemplo:</span><span class="sxs-lookup"><span data-stu-id="c809f-117">Add this sample data:</span></span>  
  
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
  
3.  <span data-ttu-id="c809f-118">Copie o DiffGram acima e cole em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="c809f-118">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="c809f-119">Salve o arquivo como MyDiffGram.xml na mesma pasta usada na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="c809f-119">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="c809f-120">Copie o DiffGramSchema fornecido anteriormente neste tópico e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="c809f-120">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="c809f-121">Salve o arquivo como DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="c809f-121">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="c809f-122">Crie e use o Script de Teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o DiffGram.</span><span class="sxs-lookup"><span data-stu-id="c809f-122">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="c809f-123">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c809f-123">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="b-inserting-a-record-by-using-a-diffgram"></a><span data-ttu-id="c809f-124">B.</span><span class="sxs-lookup"><span data-stu-id="c809f-124">B.</span></span> <span data-ttu-id="c809f-125">Inserindo um registro usando um DiffGram</span><span class="sxs-lookup"><span data-stu-id="c809f-125">Inserting a record by using a DiffGram</span></span>  
 <span data-ttu-id="c809f-126">Neste exemplo, o DiffGram insere um registro na tabela Cust e um registro na tabela Ord.</span><span class="sxs-lookup"><span data-stu-id="c809f-126">In this example, the DiffGram inserts a record in the Cust table and a record in the Ord table.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"   
      sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
          xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
          xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
       <Customer diffgr:id="Customer1" msdata:rowOrder="0"    
                 diffgr:hasChanges="inserted" CustomerID="ALFKI">  
        <CompanyName>C3Company</CompanyName>  
        <ContactName>C3Contact</ContactName>  
        <Order diffgr:id="Order1"   
               msdata:rowOrder="0"  
               diffgr:hasChanges="inserted"   
               CustomerID="ALFKI" OrderID="1"/>  
      </Customer>  
    </DataInstance>  
  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="c809f-127">Neste DiffGram, o **\<before>** bloco não é especificado (nenhum registro de banco de dados existente foi identificado).</span><span class="sxs-lookup"><span data-stu-id="c809f-127">In this DiffGram the **\<before>** block is not specified (no existing database records identified).</span></span> <span data-ttu-id="c809f-128">Há duas instâncias de registro (identificadas pelos **\<Customer>** **\<Order>** elementos e no **\<DataInstance>** bloco) que são mapeadas para as tabelas Cust e Ord, respectivamente.</span><span class="sxs-lookup"><span data-stu-id="c809f-128">There are two record instances (identified by the **\<Customer>** and **\<Order>** elements in the **\<DataInstance>** block) that map to Cust and Ord tables, respectively.</span></span> <span data-ttu-id="c809f-129">Ambos os elementos especificam o atributo **diffgr: hasChanges** (**HasChanges = "inserted"**).</span><span class="sxs-lookup"><span data-stu-id="c809f-129">Both of these elements specify the **diffgr:hasChanges** attribute (**hasChanges="inserted"**).</span></span> <span data-ttu-id="c809f-130">Isso indica uma operação de inserção.</span><span class="sxs-lookup"><span data-stu-id="c809f-130">This indicates an insert operation.</span></span> <span data-ttu-id="c809f-131">Nesse DiffGram, se você especificar **HasChanges = "Modified"**, você está indicando que deseja modificar um registro que não existe, o que resulta em um erro.</span><span class="sxs-lookup"><span data-stu-id="c809f-131">In this DiffGram, if you specify **hasChanges="modified"**, you are indicating that you want to modify a record that does not exist, which results in an error.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="c809f-132">Para testar o DiffGram</span><span class="sxs-lookup"><span data-stu-id="c809f-132">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="c809f-133">Crie essas tabelas no banco de dados **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="c809f-133">Create these tables in the **tempdb** database.</span></span>  
  
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
  
2.  <span data-ttu-id="c809f-134">Adicione estes dados de exemplo:</span><span class="sxs-lookup"><span data-stu-id="c809f-134">Add this sample data:</span></span>  
  
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
  
3.  <span data-ttu-id="c809f-135">Copie o DiffGram acima e cole em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="c809f-135">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="c809f-136">Salve o arquivo como MyDiffGram.xml na mesma pasta usada na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="c809f-136">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="c809f-137">Copie o DiffGramSchema fornecido anteriormente neste tópico e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="c809f-137">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="c809f-138">Salve o arquivo como DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="c809f-138">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="c809f-139">Crie e use o Script de Teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o DiffGram.</span><span class="sxs-lookup"><span data-stu-id="c809f-139">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="c809f-140">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c809f-140">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="c-updating-an-existing-record-by-using-a-diffgram"></a><span data-ttu-id="c809f-141">C.</span><span class="sxs-lookup"><span data-stu-id="c809f-141">C.</span></span> <span data-ttu-id="c809f-142">Atualizando um registro existente usando um DiffGram</span><span class="sxs-lookup"><span data-stu-id="c809f-142">Updating an existing record by using a DiffGram</span></span>  
 <span data-ttu-id="c809f-143">Neste exemplo, o DiffGram atualiza as informações do cliente (CompanyName e ContactName) de ALFKI do cliente.</span><span class="sxs-lookup"><span data-stu-id="c809f-143">In this example, the DiffGram updates customer information (CompanyName and ContactName) for customer ALFKI.</span></span>  
  
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
  
 <span data-ttu-id="c809f-144">O **\<before>** bloco inclui um **\<Customer>** elemento (**diffgr: ID = "Customer1"**).</span><span class="sxs-lookup"><span data-stu-id="c809f-144">The **\<before>** block includes a **\<Customer>** element (**diffgr:id="Customer1"**).</span></span> <span data-ttu-id="c809f-145">O **\<DataInstance>** bloco inclui o **\<Customer>** elemento correspondente com a mesma **ID**. O **\<customer>** elemento em **\<NewDataSet>** também especifica **diffgr: hasChanges = "Modified"**.</span><span class="sxs-lookup"><span data-stu-id="c809f-145">The **\<DataInstance>** block includes the corresponding **\<Customer>** element with same **id**. The **\<customer>** element in the **\<NewDataSet>** also specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="c809f-146">Isso indica uma operação de atualização e o registro de cliente na tabela **cust** é atualizado de acordo.</span><span class="sxs-lookup"><span data-stu-id="c809f-146">This indicates an update operation, and the customer record in the **Cust** table is updated accordingly.</span></span> <span data-ttu-id="c809f-147">Observe que, se o atributo **diffgr: hasChanges** não for especificado, a lógica de processamento de DiffGram ignorará esse elemento e nenhuma atualização será executada.</span><span class="sxs-lookup"><span data-stu-id="c809f-147">Note that if the **diffgr:hasChanges** attribute is not specified, the DiffGram processing logic ignores this element and no updates are performed.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="c809f-148">Para testar o DiffGram</span><span class="sxs-lookup"><span data-stu-id="c809f-148">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="c809f-149">Crie essas tabelas no banco de dados **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="c809f-149">Create these tables in the **tempdb** database.</span></span>  
  
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
  
2.  <span data-ttu-id="c809f-150">Adicione estes dados de exemplo:</span><span class="sxs-lookup"><span data-stu-id="c809f-150">Add this sample data:</span></span>  
  
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
  
3.  <span data-ttu-id="c809f-151">Copie o DiffGram acima e cole em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="c809f-151">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="c809f-152">Salve o arquivo como MyDiffGram.xml na mesma pasta usada na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="c809f-152">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="c809f-153">Copie o DiffGramSchema fornecido anteriormente neste tópico e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="c809f-153">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="c809f-154">Salve o arquivo como DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="c809f-154">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="c809f-155">Crie e use o Script de Teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o DiffGram.</span><span class="sxs-lookup"><span data-stu-id="c809f-155">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="c809f-156">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c809f-156">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="d-inserting-updating-and-deleting-records-by-using-a-diffgram"></a><span data-ttu-id="c809f-157">D.</span><span class="sxs-lookup"><span data-stu-id="c809f-157">D.</span></span> <span data-ttu-id="c809f-158">Inserindo, atualizando e excluindo registros usando um DiffGram</span><span class="sxs-lookup"><span data-stu-id="c809f-158">Inserting, updating, and deleting records by using a DiffGram</span></span>  
 <span data-ttu-id="c809f-159">Neste exemplo, um DiffGram relativamente complexo é usado para executar operações de inserção, atualização e exclusão.</span><span class="sxs-lookup"><span data-stu-id="c809f-159">In this example, a relatively complex DiffGram is used to perform insert, update, and delete operations.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql" sql:mapping-schema="DiffGramSchema.xml">  
  <diffgr:diffgram   
         xmlns:msdata="urn:schemas-microsoft-com:xml-msdata"   
         xmlns:diffgr="urn:schemas-microsoft-com:xml-diffgram-v1">  
    <DataInstance>  
      <Customer diffgr:id="Customer2" msdata:rowOrder="1"   
                diffgr:hasChanges="modified"   
                CustomerID="ANATR">  
          <CompanyName>Bottom Dollar Markets</CompanyName>  
          <ContactName>Elizabeth Lincoln</ContactName>  
          <Order diffgr:id="Order2" msdata:rowOrder="1"   
               msdata:hiddenCustomerID="ANATR"   
               CustomerID="ANATR" OrderID="2"/>  
      </Customer>  
  
      <Customer diffgr:id="Customer3" msdata:rowOrder="2"   
                CustomerID="ANTON">  
         <CompanyName>Chop-suey Chinese</CompanyName>  
         <ContactName>Yang Wang</ContactName>  
         <Order diffgr:id="Order3" msdata:rowOrder="2"   
               msdata:hiddenCustomerID="ANTON"   
               CustomerID="ANTON" OrderID="3"/>  
      </Customer>  
      <Customer diffgr:id="Customer4" msdata:rowOrder="3"   
                diffgr:hasChanges="inserted"   
                CustomerID="AROUT">  
         <CompanyName>Around the Horn</CompanyName>  
         <ContactName>Thomas Hardy</ContactName>  
         <Order diffgr:id="Order4" msdata:rowOrder="3"   
                diffgr:hasChanges="inserted"   
                msdata:hiddenCustomerID="AROUT"   
               CustomerID="AROUT" OrderID="4"/>  
      </Customer>  
    </DataInstance>  
    <diffgr:before>  
      <Order diffgr:id="Order1" msdata:rowOrder="0"   
             msdata:hiddenCustomerID="ALFKI"   
             CustomerID="ALFKI" OrderID="1"/>  
      <Customer diffgr:id="Customer1" msdata:rowOrder="0"   
                CustomerID="ALFKI">  
        <CompanyName>Alfreds Futterkiste</CompanyName>  
        <ContactName>Maria Anders</ContactName>  
      </Customer>  
      <Customer diffgr:id="Customer2" msdata:rowOrder="1"   
                CustomerID="ANATR">  
        <CompanyName>Ana Trujillo Emparedados y helados</CompanyName>  
        <ContactName>Ana Trujillo</ContactName>  
      </Customer>  
    </diffgr:before>  
  </diffgr:diffgram>  
</ROOT>  
```  
  
 <span data-ttu-id="c809f-160">A lógica do DiffGram processa este DiffGram como a seguir:</span><span class="sxs-lookup"><span data-stu-id="c809f-160">The DiffGram logic processes this DiffGram as follows:</span></span>  
  
-   <span data-ttu-id="c809f-161">De acordo com a lógica de processamento DiffGram, todos os elementos de nível superior no **\<before>** bloco são mapeados para tabelas correspondentes, conforme descrito no esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="c809f-161">In accordance with DiffGram processing logic, all the top-level elements in the **\<before>** block map to corresponding tables, as described in the mapping schema.</span></span>  
  
-   <span data-ttu-id="c809f-162">O **\<before>** bloco tem um **\<Order>** elemento (**dffgr: ID = "Order1"**) e um **\<Customer>** elemento (**diffgr: ID = "Customer1"**) para o qual não há nenhum elemento correspondente no **\<DataInstance>** bloco (com a mesma ID).</span><span class="sxs-lookup"><span data-stu-id="c809f-162">The **\<before>** block has an **\<Order>** element (**dffgr:id="Order1"**) and a **\<Customer>** element (**diffgr:id="Customer1"**) for which there is no corresponding element in the **\<DataInstance>** block (with the same ID).</span></span> <span data-ttu-id="c809f-163">Isto indica uma operação de exclusão e os registros são excluídos das tabelas Cust e Ord.</span><span class="sxs-lookup"><span data-stu-id="c809f-163">This indicates a delete operation, and the records are deleted from the Cust and Ord tables.</span></span>  
  
-   <span data-ttu-id="c809f-164">O **\<before>** bloco tem um **\<Customer>** elemento (**diffgr: ID = "customer2"**) para o qual há um **\<Customer>** elemento correspondente no **\<DataInstance>** bloco (com a mesma ID).</span><span class="sxs-lookup"><span data-stu-id="c809f-164">The **\<before>** block has a **\<Customer>** element (**diffgr:id="Customer2"**) for which there is a corresponding **\<Customer>** element in the **\<DataInstance>** block (with the same ID).</span></span> <span data-ttu-id="c809f-165">O elemento no **\<DataInstance>** bloco especifica **diffgr: hasChanges = "Modified"**.</span><span class="sxs-lookup"><span data-stu-id="c809f-165">The element in the **\<DataInstance>** block specifies **diffgr:hasChanges="modified"**.</span></span> <span data-ttu-id="c809f-166">Esta é uma operação de atualização na qual para clientes ANATR, as informações CompanyName e ContactName são atualizadas na tabela Cust usando valores que são especificados no **\<DataInstance>** bloco.</span><span class="sxs-lookup"><span data-stu-id="c809f-166">This is an update operation in which for customer ANATR, the CompanyName and ContactName information is updated in the Cust table using values that are specified in the **\<DataInstance>** block.</span></span>  
  
-   <span data-ttu-id="c809f-167">O **\<DataInstance>** bloco tem um **\<Customer>** elemento (**diffgr: ID = "Customer3"**) e um **\<Order>** elemento (**diffgr: ID = "Order3"**).</span><span class="sxs-lookup"><span data-stu-id="c809f-167">The **\<DataInstance>** block has a **\<Customer>** element (**diffgr:id="Customer3"**) and an **\<Order>** element (**diffgr:id="Order3"**).</span></span> <span data-ttu-id="c809f-168">Nenhum desses elementos especifica o atributo **diffgr: hasChanges** .</span><span class="sxs-lookup"><span data-stu-id="c809f-168">Neither of these elements specify the **diffgr:hasChanges** attribute.</span></span> <span data-ttu-id="c809f-169">Portanto, a lógica de processamento do DiffGram ignora esses elementos.</span><span class="sxs-lookup"><span data-stu-id="c809f-169">Therefore, the DiffGram processing logic ignores these elements.</span></span>  
  
-   <span data-ttu-id="c809f-170">O **\<DataInstance>** bloco tem um **\<Customer>** elemento (**diffgr: ID = "Customer4"**) e um **\<Order>** elemento (**diffgr: ID = "Order4"**) para o qual não há nenhum elemento correspondente no \<before> bloco.</span><span class="sxs-lookup"><span data-stu-id="c809f-170">The **\<DataInstance>** block has a **\<Customer>** element (**diffgr:id="Customer4"**) and an **\<Order>** element (**diffgr:id="Order4"**) for which there are no corresponding elements in the \<before> block.</span></span> <span data-ttu-id="c809f-171">Esses elementos no **\<DataInstance>** bloco especificam **diffgr: hasChanges = "inserted"**.</span><span class="sxs-lookup"><span data-stu-id="c809f-171">These elements in the **\<DataInstance>** block specify **diffgr:hasChanges="inserted"**.</span></span> <span data-ttu-id="c809f-172">Portanto, um registro novo é adicionado na tabela Cust e na tabela Ord.</span><span class="sxs-lookup"><span data-stu-id="c809f-172">Therefore, a new record is added in the Cust table and in the Ord table.</span></span>  
  
#### <a name="to-test-the-diffgram"></a><span data-ttu-id="c809f-173">Para testar o DiffGram</span><span class="sxs-lookup"><span data-stu-id="c809f-173">To test the DiffGram</span></span>  
  
1.  <span data-ttu-id="c809f-174">Crie as tabelas a seguir no banco de dados **tempdb** .</span><span class="sxs-lookup"><span data-stu-id="c809f-174">Create the following tables in the **tempdb** database.</span></span>  
  
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
  
2.  <span data-ttu-id="c809f-175">Adicione estes dados de exemplo:</span><span class="sxs-lookup"><span data-stu-id="c809f-175">Add this sample data:</span></span>  
  
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
  
3.  <span data-ttu-id="c809f-176">Copie o DiffGram acima e cole em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="c809f-176">Copy the DiffGram above and paste it into a text file.</span></span> <span data-ttu-id="c809f-177">Salve o arquivo como MyDiffGram.xml na mesma pasta usada na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="c809f-177">Save the file as MyDiffGram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="c809f-178">Copie o DiffGramSchema fornecido anteriormente neste tópico e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="c809f-178">Copy the DiffGramSchema provided earlier in this topic and paste it into a text file.</span></span> <span data-ttu-id="c809f-179">Salve o arquivo como DiffGramSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="c809f-179">Save the file as DiffGramSchema.xml.</span></span>  
  
5.  <span data-ttu-id="c809f-180">Crie e use o Script de Teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o DiffGram.</span><span class="sxs-lookup"><span data-stu-id="c809f-180">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the DiffGram.</span></span>  
  
     <span data-ttu-id="c809f-181">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="c809f-181">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="e-applying-updates-by-using-a-diffgram-with-the-diffgrparentid-annotation"></a><span data-ttu-id="c809f-182">E.</span><span class="sxs-lookup"><span data-stu-id="c809f-182">E.</span></span> <span data-ttu-id="c809f-183">Aplicando atualizações usando um DiffGram com a anotação diffgr:parentID</span><span class="sxs-lookup"><span data-stu-id="c809f-183">Applying updates by using a DiffGram with the diffgr:parentID annotation</span></span>  
 <span data-ttu-id="c809f-184">Este exemplo ilustra como a anotação **parentID** especificada no **\<before>** bloco do DiffGram é usada na aplicação das atualizações.</span><span class="sxs-lookup"><span data-stu-id="c809f-184">This example illustrates how the **parentID** annotation that is specified in the **\<before>** block of the DiffGram is used in applying the updates.</span></span>  
  
```  
<NewDataSet />  
<diffgr:before>  
   <Order diffgr:id="Order1" msdata:rowOrder="0" OrderID="2" />  
   <Order diffgr:id="Order3" msdata:rowOrder="2" OrderID="4" />  
  
   <OrderDetail diffgr:id="OrderDetail1"   
                diffgr:parentId="Order1"   
                msdata:rowOrder="0"   
                ProductID="13"   
                OrderID="2" />  
   <OrderDetail diffgr:id="OrderDetail3"   
                diffgr:parentId="Order3"  
                ProductID="77"  
                OrderID="4"/>  
</diffgr:before>  
</diffgr:diffgram>  
```  
  
 <span data-ttu-id="c809f-185">Este DiffGram especifica uma operação de exclusão porque há apenas um **\<before>** bloco.</span><span class="sxs-lookup"><span data-stu-id="c809f-185">This DiffGram specifies a delete operation because there is only a **\<before>** block.</span></span> <span data-ttu-id="c809f-186">No DiffGram, a anotação **parentID** é usada para especificar uma relação pai-filho entre os pedidos e os detalhes do pedido.</span><span class="sxs-lookup"><span data-stu-id="c809f-186">In the DiffGram, the **parentID** annotation is used to specify a parent-child relationship between the orders and order details.</span></span> <span data-ttu-id="c809f-187">Quando SQLXML exclui os registros, ele exclui registros da tabela filho identificada por essa relação e, em seguida, exclui os registros da tabela pai correspondente.</span><span class="sxs-lookup"><span data-stu-id="c809f-187">When SQLXML deletes the records, it deletes records from the child table that is identified by this relationship and then deletes the records from the corresponding parent table.</span></span>  
  
  
