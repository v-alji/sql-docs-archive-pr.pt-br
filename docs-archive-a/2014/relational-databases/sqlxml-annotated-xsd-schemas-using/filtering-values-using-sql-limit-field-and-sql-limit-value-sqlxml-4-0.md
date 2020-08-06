---
title: 'Filtrando valores usando SQL: limit-field e SQL: limit-value (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, filtering values
- limiting values [SQLXML]
- limit-value annotation
- limit-field annotation
- sql:limit-field
- sql:limit-value
- filtering [SQLXML]
ms.assetid: c0f7ae92-eeec-430e-a66a-f22c3ae64a5e
author: rothja
ms.author: jroth
ms.openlocfilehash: 7886a9a6f51c76ed693576ca6f4659f4051d1f20
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685483"
---
# <a name="filtering-values-using-sqllimit-field-and-sqllimit-value-sqlxml-40"></a><span data-ttu-id="1fa8b-102">Filtrando valores usando sql:limit-field e sql:limit-value (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="1fa8b-102">Filtering Values Using sql:limit-field and sql:limit-value (SQLXML 4.0)</span></span>
  <span data-ttu-id="1fa8b-103">Você pode limitar as linhas retornadas de uma consulta de banco de dados com base em algum valor limitador.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-103">You can limit rows that are returned from a database query on the basis of some limiting value.</span></span> <span data-ttu-id="1fa8b-104">As anotações `sql:limit-field` e `sql:limit-value` são usadas para identificar a coluna de banco de dados que contém os valores limitadores e especificar um valor limitador específico a ser usado para filtrar os dados retornados.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-104">The `sql:limit-field` and `sql:limit-value` annotations are used to identify the database column that contains limiting values and to specify a specific limiting value to be used to filter the data returned.</span></span>  
  
 <span data-ttu-id="1fa8b-105">A anotação `sql:limit-field` é usada para identificar uma coluna que contém um valor limitador; ela é permitida em cada elemento ou atributo mapeado.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-105">The `sql:limit-field` annotation is used to identify a column that contains a limiting value; it is allowed on each mapped element or attribute.</span></span>  
  
 <span data-ttu-id="1fa8b-106">A anotação `sql:limit-value` é usada para especificar o valor limitado na coluna especificada na anotação `sql:limit-field`.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-106">The `sql:limit-value` annotation is used to specify the limited value in the column that is specified in the `sql:limit-field` annotation.</span></span> <span data-ttu-id="1fa8b-107">A anotação `sql:limit-value` é opcional.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-107">The `sql:limit-value` annotation is optional.</span></span> <span data-ttu-id="1fa8b-108">Se `sql:limit-value` não for especificado, um valor NULL será assumido.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-108">If `sql:limit-value` is not specified, a NULL value is assumed.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="1fa8b-109">Ao trabalhar com um `sql:limit-field` onde a coluna SQL mapeada é do tipo `real`, o SQLXML 4.0 executa a conversão no `sql:limit-value` conforme especificado em esquemas XML como um valor especificado por `nvarchar`.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-109">When working with a `sql:limit-field` where the mapped SQL column is of type `real`, SQLXML 4.0 performs conversion on the `sql:limit-value` as specified in XML schemas as an `nvarchar` specified value.</span></span> <span data-ttu-id="1fa8b-110">Isso exige que os valores de limite decimal sejam especificados usando notação científica completa.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-110">This requires that decimal limit values be specified using full scientific notation.</span></span> <span data-ttu-id="1fa8b-111">Para obter mais informações, veja o Exemplo B a seguir.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-111">For more information, see Example B below.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="1fa8b-112">Exemplos</span><span class="sxs-lookup"><span data-stu-id="1fa8b-112">Examples</span></span>  
 <span data-ttu-id="1fa8b-113">Para testar os exemplos a seguir, é necessário ter estes programas instalados:</span><span class="sxs-lookup"><span data-stu-id="1fa8b-113">To create working samples using these examples, you need to have the following installed:</span></span>  
  
-   <span data-ttu-id="1fa8b-114">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span><span class="sxs-lookup"><span data-stu-id="1fa8b-114">Microsoft [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client</span></span>  
  
-   <span data-ttu-id="1fa8b-115">MDAC 2.6 ou posterior</span><span class="sxs-lookup"><span data-stu-id="1fa8b-115">MDAC 2.6 or later</span></span>  
  
 <span data-ttu-id="1fa8b-116">Nestes exemplos, são usados modelos para especificar consultas XPath com base no esquema XSD de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-116">In these examples, templates are used to specify XPath queries against the mapping XSD schema.</span></span>  
  
### <a name="a-limiting-the-customer-addresses-returned-to-a-specific-address-type"></a><span data-ttu-id="1fa8b-117">a.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-117">A.</span></span> <span data-ttu-id="1fa8b-118">Limitar os endereços de cliente retornados para um tipo de endereço específico</span><span class="sxs-lookup"><span data-stu-id="1fa8b-118">Limiting the customer addresses returned to a specific address type</span></span>  
 <span data-ttu-id="1fa8b-119">Neste exemplo, um banco de dados contém duas tabelas:</span><span class="sxs-lookup"><span data-stu-id="1fa8b-119">In this example, a database contains two tables:</span></span>  
  
-   <span data-ttu-id="1fa8b-120">Customer (CustomerID, CompanyName)</span><span class="sxs-lookup"><span data-stu-id="1fa8b-120">Customer (CustomerID, CompanyName)</span></span>  
  
-   <span data-ttu-id="1fa8b-121">Addresses (CustomerID, AddressType, StreetAddress)</span><span class="sxs-lookup"><span data-stu-id="1fa8b-121">Addresses (CustomerID, AddressType, StreetAddress)</span></span>  
  
 <span data-ttu-id="1fa8b-122">Um cliente pode ter um endereço para cobrança e/ou um endereço para entrega.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-122">A customer can have a shipping address and/or a billing address.</span></span> <span data-ttu-id="1fa8b-123">Os valores da coluna AddressType são Shipping e Billing.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-123">The AddressType column values are Shipping and Billing.</span></span>  
  
 <span data-ttu-id="1fa8b-124">Esse é o esquema de mapeamento no qual o atributo de esquema **NomeDoDestinatário** é mapeado para a coluna StreetAddress na relação de endereços.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-124">This is the mapping schema in which the **ShipTo** schema attribute maps to the StreetAddress column in the Addresses relation.</span></span> <span data-ttu-id="1fa8b-125">Os valores retornados para esse atributo são limitados somente aos endereços para entrega especificando as anotações `sql:limit-field` e `sql:limit-value`.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-125">The values that are returned for this attribute are limited to only shipping addresses by specifying the `sql:limit-field` and `sql:limit-value` annotations.</span></span> <span data-ttu-id="1fa8b-126">Da mesma forma, o atributo de esquema **billTo** retorna apenas o endereço de cobrança de um cliente.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-126">Similarly, the **BillTo** schema attribute returns only the billing address of a customer.</span></span>  
  
 <span data-ttu-id="1fa8b-127">Este é o esquema:</span><span class="sxs-lookup"><span data-stu-id="1fa8b-127">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustAddr"  
        parent="Customer"  
        parent-key="CustomerID"  
        child="Addresses"  
        child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Customer" >  
   <xsd:complexType>  
        <xsd:sequence>  
        <xsd:element name="BillTo"   
                       type="xsd:string"   
                       sql:relation="Addresses"   
                       sql:field="StreetAddress"  
                       sql:limit-field="AddressType"  
                       sql:limit-value="billing"  
                       sql:relationship="CustAddr" >  
        </xsd:element>  
        <xsd:element name="ShipTo"   
                       type="xsd:string"   
                       sql:relation="Addresses"   
                       sql:field="StreetAddress"  
                       sql:limit-field="AddressType"  
                       sql:limit-value="shipping"  
                       sql:relationship="CustAddr" >  
        </xsd:element>  
        </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:int" />   
        <xsd:attribute name="CompanyName"  type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="1fa8b-128">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="1fa8b-128">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="1fa8b-129">Crie duas tabelas no banco de dados **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="1fa8b-129">Create two tables in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Customer (CustomerID int primary key,   
                           CompanyName varchar(30))  
    CREATE TABLE Addresses(CustomerID int,   
                           StreetAddress varchar(50),  
                           AddressType varchar(10))  
    ```  
  
2.  <span data-ttu-id="1fa8b-130">Adicione os dados de exemplo:</span><span class="sxs-lookup"><span data-stu-id="1fa8b-130">Add the sample data:</span></span>  
  
    ```  
    INSERT INTO Customer values (1, 'Company A')  
    INSERT INTO Customer values (2, 'Company B')  
  
    INSERT INTO Addresses values  
               (1, 'Obere Str. 57 Berlin', 'billing')  
    INSERT INTO Addresses values  
               (1, 'Avda. de la Constituci??n 2222 M??xico D.F.', 'shipping')  
    INSERT INTO Addresses values  
               (2, '120 Hanover Sq., London', 'billing')  
    INSERT INTO Addresses values  
               (2, 'Forsterstr. 57, Mannheim', 'shipping')  
    ```  
  
3.  <span data-ttu-id="1fa8b-131">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-131">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="1fa8b-132">Salve o arquivo como LimitFieldValue.xml.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-132">Save the file as LimitFieldValue.xml.</span></span>  
  
4.  <span data-ttu-id="1fa8b-133">Crie o modelo a seguir (LimitFieldValueT.xml) e salve-o no mesmo local onde você salvou o esquema (LimitFieldValue.xml) na etapa anterior:</span><span class="sxs-lookup"><span data-stu-id="1fa8b-133">Create the following template (LimitFieldValueT.xml), and save it in the same where you saved the schema (LimitFieldValue.xml) in the previous step:</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="LimitFieldValue.xml">  
            /Customer  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="1fa8b-134">O caminho de diretório especificado para o esquema de mapeamento (LimitFieldValue.xml) é relativo ao diretório em que o modelo está salvo.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-134">The directory path specified for the mapping schema (LimitFieldValue.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="1fa8b-135">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="1fa8b-135">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\LimitFieldValue.xml"  
    ```  
  
5.  <span data-ttu-id="1fa8b-136">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-136">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="1fa8b-137">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="1fa8b-137">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="1fa8b-138">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="1fa8b-138">This is the result:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer CustomerID="1" CompanyName="Company A">   
     <BillTo>Obere Str. 57 Berlin</BillTo>   
     <ShipTo>Avda. de la Constituci??n 2222 M??xico D.F.</ShipTo>   
  </Customer>   
  <Customer CustomerID="2" CompanyName="Company B">   
     <BillTo>120 Hanover Sq., London</BillTo>   
     <ShipTo>Forsterstr. 57, Mannheim</ShipTo>   
   </Customer>   
</ROOT>  
```  
  
### <a name="b-limiting-results-based-on-a-discount-value-of-type-real-data"></a><span data-ttu-id="1fa8b-139">B.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-139">B.</span></span> <span data-ttu-id="1fa8b-140">Limitar os resultados com base em um valor de desconto de dados de tipos reais</span><span class="sxs-lookup"><span data-stu-id="1fa8b-140">Limiting results based on a discount value of type real data</span></span>  
 <span data-ttu-id="1fa8b-141">Neste exemplo, um banco de dados contém duas tabelas:</span><span class="sxs-lookup"><span data-stu-id="1fa8b-141">In this example, a database contains two tables:</span></span>  
  
-   <span data-ttu-id="1fa8b-142">Orders (OrderID)</span><span class="sxs-lookup"><span data-stu-id="1fa8b-142">Orders (OrderID)</span></span>  
  
-   <span data-ttu-id="1fa8b-143">OrderDetails (OrderID, ProductID, UnitPrice, Quantity, Price, Discount)</span><span class="sxs-lookup"><span data-stu-id="1fa8b-143">OrderDetails (OrderID, ProductID, UnitPrice, Quantity, Price, Discount)</span></span>  
  
 <span data-ttu-id="1fa8b-144">Esse é o esquema de mapeamento no qual o atributo **OrderID** nos detalhes da ordem é mapeado para a coluna OrderID na relação Orders.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-144">This is the mapping schema in which the **OrderID** attribute on the order details maps to the OrderID column in the orders relation.</span></span> <span data-ttu-id="1fa8b-145">Os valores retornados para esse atributo são limitados apenas aos que têm um valor de 2.0000000 e-001 (0,2) conforme especificado para o atributo de **desconto** usando as `sql:limit-field` `sql:limit-value` anotações e.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-145">The values that are returned for this attribute are limited to only those that have a value of 2.0000000e-001 (0.2) as specified for the **Discount** attribute using the `sql:limit-field` and `sql:limit-value` annotations.</span></span>  
  
 <span data-ttu-id="1fa8b-146">Este é o esquema:</span><span class="sxs-lookup"><span data-stu-id="1fa8b-146">This is the schema:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:annotation>  
   <xsd:appinfo>  
    <sql:relationship name="OrderOrderDetails"  
        parent="Orders"  
        parent-key="OrderID"  
        child="OrderDetails"  
        child-key="OrderID" />  
   </xsd:appinfo>  
  </xsd:annotation>  
  <xsd:element name="root" sql:is-constant="1">  
   <xsd:complexType>  
     <xsd:sequence>  
       <xsd:element name="Order" sql:relation="Orders" >  
          <xsd:complexType>  
             <xsd:sequence>  
                <xsd:element name="orderDetail"   
                       sql:relation="OrderDetails"   
                       sql:limit-field="Discount"                       sql:limit-value="2.0000000e-001"  
                       sql:relationship="OrderOrderDetails">  
                   <xsd:complexType>  
                     <xsd:attribute name="OrderID"   />   
                     <xsd:attribute name="ProductID" />   
                     <xsd:attribute name="Discount"  />   
                     <xsd:attribute name="Quantity"  />   
                     <xsd:attribute name="UnitPrice" />   
                   </xsd:complexType>  
                </xsd:element>  
            </xsd:sequence>  
           <xsd:attribute name="OrderID"/>   
          </xsd:complexType>  
       </xsd:element>  
     </xsd:sequence>  
   </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="1fa8b-147">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="1fa8b-147">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="1fa8b-148">Crie duas tabelas no banco de dados **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="1fa8b-148">Create two tables in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Orders ([OrderID] int NOT NULL ) ON [PRIMARY]  
    ALTER TABLE Orders WITH NOCHECK ADD   
    CONSTRAINT [PK_Orders] PRIMARY KEY  CLUSTERED (  
       [OrderID]  
     )  ON [PRIMARY]   
    CREATE TABLE [OrderDetails] (  
       [OrderID] int NOT NULL ,  
       [ProductID] int NOT NULL ,  
       [UnitPrice] money NULL ,  
       [Quantity] smallint NOT NULL ,  
       [Discount] real NOT NULL   
    ) ON [PRIMARY]  
    ```  
  
2.  <span data-ttu-id="1fa8b-149">Adicione os dados de exemplo:</span><span class="sxs-lookup"><span data-stu-id="1fa8b-149">Add the sample data:</span></span>  
  
    ```  
    INSERT INTO Orders ([OrderID]) values (10248)  
    INSERT INTO Orders ([OrderID]) values (10250)  
    INSERT INTO Orders ([OrderID]) values (10251)  
    INSERT INTO Orders ([OrderID]) values (10257)  
    INSERT INTO Orders ([OrderID]) values (10258)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10248,11,14,12,0)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10250,51,42.4,35,0.15)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10251,22,16.8,6,0.05)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10257,77,10.4,15,0)  
    INSERT INTO [OrderDetails] ([OrderID],[ProductID],[UnitPrice],[Quantity],[Discount]) values (10258,2,15.2,50,0.2)  
    ```  
  
3.  <span data-ttu-id="1fa8b-150">Salve o esquema (LimitFieldValue.xml) em um diretório.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-150">Save the schema (LimitFieldValue.xml) in a directory.</span></span>  
  
4.  <span data-ttu-id="1fa8b-151">Crie o script de teste (TestQuery.vbs) a seguir, modifique MyServer para o nome do computador SQL Server e salve-o no mesmo diretório que você usou na etapa anterior para salvar o esquema:</span><span class="sxs-lookup"><span data-stu-id="1fa8b-151">Create the following test script (TestQuery.vbs), modify MyServer to the name of your SQL Server computer and save it in the same directory as you used in the previous step to save the schema:</span></span>  
  
    ```  
    Set conn = CreateObject("ADODB.Connection")  
    conn.Open "Provider=SQLOLEDB;Data Source=MyServer;Database=tempdb;Integrated Security=SSPI"  
    conn.Properties("SQLXML Version") = "sqlxml.4.0"   
    Set cmd = CreateObject("ADODB.Command")  
    Set stm = CreateObject("ADODB.Stream")  
    Set cmd.ActiveConnection = conn  
    stm.open  
    result ="none"  
    strXPathQuery="/root"  
    DBGUID_XPATH = "{EC2A4293-E898-11D2-B1B7-00C04F680C56}"  
    cmd.Dialect = DBGUID_XPATH  
    cmd.CommandText = strXPathQuery  
    cmd.Properties("Mapping schema") = "LimitFieldReal.xml"  
    cmd.Properties("Output Stream").Value = stm  
    cmd.Properties("Output Encoding") = "utf-8"  
    WScript.Echo "executing for xml query"  
    On Error Resume Next  
    cmd.Execute , ,1024  
    if err then  
    Wscript.Echo err.description  
    Wscript.Echo err.Number  
    Wscript.Echo err.source  
    On Error GoTo 0  
    else  
    stm.Position = 0  
    result  = stm.ReadText  
    end if  
    WScript.Echo result  
    Wscript.Echo "done"  
    ```  
  
5.  <span data-ttu-id="1fa8b-152">Execute o arquivo TestQuery.vbs clicando nele no Windows Explorer.</span><span class="sxs-lookup"><span data-stu-id="1fa8b-152">Execute the TestQuery.vbs file by clicking on it in Windows Explorer.</span></span>  
  
     <span data-ttu-id="1fa8b-153">Este é o resultado:</span><span class="sxs-lookup"><span data-stu-id="1fa8b-153">This is the result:</span></span>  
  
    ```  
    <root>  
      <Order OrderID="10248"/>  
      <Order OrderID="10250"/>  
      <Order OrderID="10251"/>  
      <Order OrderID="10257"/>  
      <Order OrderID="10258">  
        <orderDetail OrderID="10258"   
                     ProductID="2"   
                     Discount="0.2"   
                     Quantity="50"/>  
      </Order>  
    </root>  
    ```  
  
## <a name="see-also"></a><span data-ttu-id="1fa8b-154">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="1fa8b-154">See Also</span></span>  
 <span data-ttu-id="1fa8b-155">[&#41;de Transact-SQL de &#40;flutuante e real](/sql/t-sql/data-types/float-and-real-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1fa8b-155">[float and real &#40;Transact-SQL&#41;](/sql/t-sql/data-types/float-and-real-transact-sql) </span></span>  
 <span data-ttu-id="1fa8b-156">[nchar e nvarchar &#40;&#41;de Transact-SQL](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="1fa8b-156">[nchar and nvarchar &#40;Transact-SQL&#41;](/sql/t-sql/data-types/nchar-and-nvarchar-transact-sql) </span></span>  
 <span data-ttu-id="1fa8b-157">[Instalando o SQL Server Native Client](../../relational-databases/native-client/applications/installing-sql-server-native-client.md) </span><span class="sxs-lookup"><span data-stu-id="1fa8b-157">[Installing SQL Server Native Client](../../relational-databases/native-client/applications/installing-sql-server-native-client.md) </span></span>  
 [<span data-ttu-id="1fa8b-158">Usando esquemas XSD anotados em consultas &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="1fa8b-158">Using Annotated XSD Schemas in Queries &#40;SQLXML 4.0&#41;</span></span>](../../relational-databases/sqlxml/annotated-xsd-schemas/using-annotated-xsd-schemas-in-queries-sqlxml-4-0.md)  
  
  
