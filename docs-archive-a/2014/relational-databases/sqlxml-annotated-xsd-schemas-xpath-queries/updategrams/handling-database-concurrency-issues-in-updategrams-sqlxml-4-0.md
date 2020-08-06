---
title: Tratamento de problemas de simultaneidade de banco de dados em Updategrams (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- <before> block
- low concurrency protection
- database concurrency [SQLXML]
- timestamp column [SQLXML]
- updategrams [SQLXML], database concurrency
- high concurrency protection [SQLXML]
- optimistic concurrency control
- concurrency [SQLXML]
- intermediate concurrency protection [SQLXML]
ms.assetid: d4b908d1-b25b-4ad9-8478-9cd882e8c44e
author: rothja
ms.author: jroth
ms.openlocfilehash: dd808b2688e8bf05149a5454bee91123878fb2ed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575750"
---
# <a name="handling-database-concurrency-issues-in-updategrams-sqlxml-40"></a><span data-ttu-id="813a4-102">Manipulando problemas de simultaneidade de banco de dados nos diagramas de atualização (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="813a4-102">Handling Database Concurrency Issues in Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="813a4-103">Da mesma forma que outros mecanismos de atualização de banco de dados, os diagramas de atualização devem lidar com atualizações simultâneas dos dados em um ambiente multiusuário.</span><span class="sxs-lookup"><span data-stu-id="813a4-103">Like other database update mechanisms, updategrams must deal with concurrent updates to data in a multiuser environment.</span></span> <span data-ttu-id="813a4-104">Os diagramas de atualização usam o Controle de simultaneidade otimista, que usa a comparação de dados de campos selecionados como instantâneos para garantir que os dados a serem atualizados não foram alterados por outro aplicativo de usuário desde que foram lidos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="813a4-104">Updategrams use the Optimistic Concurrency Control, which uses comparison of select field data as snapshots to ensure that the data to be updated has not been altered by another user application since it was read from the database.</span></span> <span data-ttu-id="813a4-105">Os Updategrams incluem esses valores de instantâneo no **\<before>** bloco de Updategrams.</span><span class="sxs-lookup"><span data-stu-id="813a4-105">Updategrams include these snapshot values in the **\<before>** block of the updategrams.</span></span> <span data-ttu-id="813a4-106">Antes de atualizar o banco de dados, o updategram verifica os valores especificados no **\<before>** bloco em relação aos valores atualmente no banco de dados para garantir que a atualização seja válida.</span><span class="sxs-lookup"><span data-stu-id="813a4-106">Before updating the database, the updategram checks the values that are specified in the **\<before>** block against the values currently in the database to ensure that the update is valid.</span></span>  
  
 <span data-ttu-id="813a4-107">O Controle de simultaneidade otimista oferece três níveis de proteção em um diagrama de atualização: baixo (nenhum), intermediário e alto.</span><span class="sxs-lookup"><span data-stu-id="813a4-107">The Optimistic Concurrency Control offers three levels of protection in an updategram: low (none), intermediate, and high.</span></span> <span data-ttu-id="813a4-108">Você pode decidir qual o nível de proteção necessário especificando o diagrama de atualização de acordo com ele.</span><span class="sxs-lookup"><span data-stu-id="813a4-108">You can decide what level of protection you need by specifying the updategram accordingly.</span></span>  
  
## <a name="lowest-level-of-protection"></a><span data-ttu-id="813a4-109">Nível de proteção mais baixo</span><span class="sxs-lookup"><span data-stu-id="813a4-109">Lowest Level of Protection</span></span>  
 <span data-ttu-id="813a4-110">Este nível é uma atualização cega, no qual a atualização é processada sem referência a outras atualizações que foram feitas desde que o banco de dados foi lido pela última vez.</span><span class="sxs-lookup"><span data-stu-id="813a4-110">This level is a blind update, in which the update is processed without reference to other updates that have been made since the database was last read.</span></span> <span data-ttu-id="813a4-111">Nesse caso, você especifica apenas as colunas de chave primária no **\<before>** bloco para identificar o registro e especifica as informações atualizadas no **\<after>** bloco.</span><span class="sxs-lookup"><span data-stu-id="813a4-111">In such a case, you specify only the primary key column(s) in the **\<before>** block to identify the record, and you specify the updated information in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="813a4-112">Por exemplo, o novo número de telefone de contato no seguinte diagrama de atualização está correto, não importando qual tenha sido o número de telefone anteriormente.</span><span class="sxs-lookup"><span data-stu-id="813a4-112">For example, the new contact phone number in the following updategram is correct, regardless of what the phone number was previously.</span></span> <span data-ttu-id="813a4-113">Observe como o **\<before>** bloco especifica apenas a coluna de chave primária (ContactID).</span><span class="sxs-lookup"><span data-stu-id="813a4-113">Notice how the **\<before>** block specifies only the primary key column (ContactID).</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" />  
</updg:before>  
<updg:after>  
   <Person.Contact ContactID="1" Phone="111-111-1111" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="intermediate-level-of-protection"></a><span data-ttu-id="813a4-114">Nível de proteção intermediário</span><span class="sxs-lookup"><span data-stu-id="813a4-114">Intermediate Level of Protection</span></span>  
 <span data-ttu-id="813a4-115">Neste nível de proteção, o diagrama de atualização compara os valores atuais dos dados que estão sendo atualizados com os valores nas colunas do banco de dados, para garantir que os valores não foram alterados por alguma outra transação desde que o registro foi lido pela sua transação.</span><span class="sxs-lookup"><span data-stu-id="813a4-115">In this level of protection, the updategram compares the current value(s) of the data being updated with the value(s) in the database column(s) to ensure that the values have not been changed by some other transaction since the record was read by your transaction.</span></span>  
  
 <span data-ttu-id="813a4-116">Você pode obter esse nível de proteção especificando as colunas de chave primária e as colunas que você está atualizando no **\<before>** bloco.</span><span class="sxs-lookup"><span data-stu-id="813a4-116">You can get this level of protection by specifying the primary key column(s) and the column(s) that you are updating in the **\<before>** block.</span></span>  
  
 <span data-ttu-id="813a4-117">Por exemplo, este diagrama de atualização altera o valor na coluna Phone da tabela Person.Contact para o contato com ContactID igual a 1.</span><span class="sxs-lookup"><span data-stu-id="813a4-117">For example, this updategram changes the value in the Phone column of the Person.Contact table for the contact with ContactID of 1.</span></span> <span data-ttu-id="813a4-118">O **\<before>** bloco especifica o atributo **Phone** para garantir que esse valor de atributo corresponda ao valor na coluna correspondente no banco de dados antes de aplicar o valor atualizado.</span><span class="sxs-lookup"><span data-stu-id="813a4-118">The **\<before>** block specifies the **Phone** attribute to ensure that this attribute value matches the value in the corresponding column in the database before applying the updated value.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
   <Person.Contact ContactID="1" Phone="398-555-0132" />  
</updg:before>  
<updg:after>  
   <Person.Contact ContactID="1" Phone="111-111-1111" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="high-level-of-protection"></a><span data-ttu-id="813a4-119">Nível de proteção alto</span><span class="sxs-lookup"><span data-stu-id="813a4-119">High Level of Protection</span></span>  
 <span data-ttu-id="813a4-120">Um nível de proteção alto garante que o registro permanecerá o mesmo desde que o seu aplicativo o leu pela última vez (ou seja, desde que o seu aplicativo leu o registro, ele não foi alterado por nenhuma outra transação).</span><span class="sxs-lookup"><span data-stu-id="813a4-120">A high level of protection ensures that the record remains the same since your application last read that record (that is, since your application has read the record, it has not been changed by any other transaction).</span></span>  
  
 <span data-ttu-id="813a4-121">Há duas formas através das quais você pode obter esse nível de proteção alto contra atualizações simultâneas:</span><span class="sxs-lookup"><span data-stu-id="813a4-121">There are two ways you can get this high level of protection against concurrent updates:</span></span>  
  
-   <span data-ttu-id="813a4-122">Especifique colunas adicionais na tabela no **\<before>** bloco.</span><span class="sxs-lookup"><span data-stu-id="813a4-122">Specify additional columns in the table in the **\<before>** block.</span></span>  
  
     <span data-ttu-id="813a4-123">Se você especificar colunas adicionais no **\<before>** bloco, o updategram compara os valores especificados para essas colunas com os valores que estavam no banco de dados antes de aplicar a atualização.</span><span class="sxs-lookup"><span data-stu-id="813a4-123">If you specify additional columns in the **\<before>** block, the updategram compares the values that are specified for these columns with the values that were in the database before applying the update.</span></span> <span data-ttu-id="813a4-124">Se qualquer uma das colunas do registro tiver sido alterada desde que a sua transação leu o registro, o diagrama de atualização não realizará a atualização.</span><span class="sxs-lookup"><span data-stu-id="813a4-124">If any of the record columns has changed since your transaction read the record, the updategram does not perform the update.</span></span>  
  
     <span data-ttu-id="813a4-125">Por exemplo, o updategram a seguir atualiza o nome da mudança, mas especifica colunas adicionais (StartTime, EndTime) no **\<before>** bloco, solicitando assim um nível mais alto de proteção contra atualizações simultâneas.</span><span class="sxs-lookup"><span data-stu-id="813a4-125">For example, the following updategram updates the shift name, but specifies additional columns (StartTime,EndTime) in the **\<before>** block, thereby requesting a higher level of protection against concurrent updates.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync >  
    <updg:before>  
       <HumanResources.Shift ShiftID="1"   
                 Name="Day"   
                 StartTime="1900-01-01 07:00:00.000"   
                 EndTime="1900-01-01 15:00:00.000" />  
    </updg:before>  
    <updg:after>  
       <HumanResources.Shift Name="Morning" />  
    </updg:after>  
    </updg:sync>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="813a4-126">Este exemplo especifica o nível mais alto de proteção especificando todos os valores de coluna para o registro no **\<before>** bloco.</span><span class="sxs-lookup"><span data-stu-id="813a4-126">This example specifies the highest level of protection by specifying all column values for the record in the **\<before>** block.</span></span>  
  
-   <span data-ttu-id="813a4-127">Especifique a coluna de carimbo de data/hora (se disponível) no **\<before>** bloco.</span><span class="sxs-lookup"><span data-stu-id="813a4-127">Specify the timestamp column (if available) in the **\<before>** block.</span></span>  
  
     <span data-ttu-id="813a4-128">Em vez de especificar todas as colunas de registro no `<before` bloco de>, você pode apenas especificar a coluna timestamp (se a tabela tiver uma) junto com as colunas de chave primária no **\<before>** bloco.</span><span class="sxs-lookup"><span data-stu-id="813a4-128">Instead of specifying all the record columns in the `<before`> block, you can just specify the timestamp column (if the table has one) along with the primary key column(s) in the **\<before>** block.</span></span> <span data-ttu-id="813a4-129">O banco de dados atualiza a coluna de carimbo de data e hora com um valor exclusivo depois de cada atualização do registro.</span><span class="sxs-lookup"><span data-stu-id="813a4-129">The database updates the timestamp column to a unique value after each update of the record.</span></span> <span data-ttu-id="813a4-130">Nesse caso, o diagrama de atualização compara o valor do carimbo de data e hora com o valor correspondente no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="813a4-130">In this case, the updategram compares the value of the timestamp with the corresponding value in the database.</span></span> <span data-ttu-id="813a4-131">O valor do carimbo de data e hora armazenado no banco de dados é um valor binário.</span><span class="sxs-lookup"><span data-stu-id="813a4-131">The timestamp value stored in the database is a binary value.</span></span> <span data-ttu-id="813a4-132">Portanto, a coluna de carimbo de data e hora deve ser especificada no esquema como `dt:type="bin.hex"`, `dt:type="bin.base64"`ou `sql:datatype="timestamp"`.</span><span class="sxs-lookup"><span data-stu-id="813a4-132">Therefore, the timestamp column must be specified in the schema as `dt:type="bin.hex"`, `dt:type="bin.base64"`, or `sql:datatype="timestamp"`.</span></span> <span data-ttu-id="813a4-133">(Você pode especificar o `xml` tipo de dados ou o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] tipo de dados.)</span><span class="sxs-lookup"><span data-stu-id="813a4-133">(You can specify either the `xml` data type or the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type.)</span></span>  
  
#### <a name="to-test-the-updategram"></a><span data-ttu-id="813a4-134">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="813a4-134">To test the updategram</span></span>  
  
1.  <span data-ttu-id="813a4-135">Crie esta tabela no banco de dados **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="813a4-135">Create this table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Customer (  
                 CustomerID  varchar(5),  
                 ContactName varchar(20),  
                 LastUpdated timestamp)  
    ```  
  
2.  <span data-ttu-id="813a4-136">Adicione este registro de exemplo:</span><span class="sxs-lookup"><span data-stu-id="813a4-136">Add this sample record:</span></span>  
  
    ```  
    INSERT INTO Customer (CustomerID, ContactName) VALUES   
                         ('C1', 'Andrew Fuller')  
    ```  
  
3.  <span data-ttu-id="813a4-137">Copie o seguinte esquema XSD e cole-o no Bloco de Notas.</span><span class="sxs-lookup"><span data-stu-id="813a4-137">Copy the following XSD schema and paste it into Notepad.</span></span> <span data-ttu-id="813a4-138">Salve como ConcurrencySampleSchema.xml:</span><span class="sxs-lookup"><span data-stu-id="813a4-138">Save it as ConcurrencySampleSchema.xml:</span></span>  
  
    ```  
    <xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
                xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
      <xsd:element name="Customer" sql:relation="Customer" >  
       <xsd:complexType>  
            <xsd:attribute name="CustomerID"    
                           sql:field="CustomerID"   
                           type="xsd:string" />   
  
            <xsd:attribute name="ContactName"    
                           sql:field="ContactName"   
                           type="xsd:string" />  
  
            <xsd:attribute name="LastUpdated"   
                           sql:field="LastUpdated"   
                           type="xsd:hexBinary"   
                 sql:datatype="timestamp" />  
  
        </xsd:complexType>  
      </xsd:element>  
    </xsd:schema>  
    ```  
  
4.  <span data-ttu-id="813a4-139">Copie o seguinte código de diagrama de atualização no Bloco de Notas e salve como ConcurrencySampleTemplate.xml, no mesmo diretório em que você salvou o esquema criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="813a4-139">Copy the following updategram code into Notepad and save it as ConcurrencySampleTemplate.xml in the same directory where you saved the schema created in the previous step.</span></span> <span data-ttu-id="813a4-140">(Observe que o seguinte valor de carimbo de data e hora para LastUpdated será diferente na sua tabela Customer de exemplo, portanto copie o valor real de LastUpdated da tabela e cole-o no diagrama de atualização.)</span><span class="sxs-lookup"><span data-stu-id="813a4-140">(Note the timestamp value below for LastUpdated will differ in your example Customer table, so copy the actual value for LastUpdated from the table and paste it into the updategram.)</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync mapping-schema="SampleSchema.xml" >  
    <updg:before>  
       <Customer CustomerID="C1"   
                 LastUpdated = "0x00000000000007D1" />  
    </updg:before>  
    <updg:after>  
       <Customer ContactName="Robert King" />  
    </updg:after>  
    </updg:sync>  
    </ROOT>  
    ```  
  
5.  <span data-ttu-id="813a4-141">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="813a4-141">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="813a4-142">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="813a4-142">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="813a4-143">Este é o esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="813a4-143">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<ElementType name="Customer" sql:relation="Customer" >  
    <AttributeType name="CustomerID" />  
    <AttributeType name="ContactName" />  
    <AttributeType name="LastUpdated"  dt:type="bin.hex"   
                                       sql:datatype="timestamp" />  
    <attribute type="CustomerID" />  
    <attribute type="ContactName" />  
    <attribute type="LastUpdated" />  
</ElementType>  
</Schema>  
```  
  
## <a name="see-also"></a><span data-ttu-id="813a4-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="813a4-144">See Also</span></span>  
 [<span data-ttu-id="813a4-145">Considerações de segurança do updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="813a4-145">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
