---
title: 'Recuperando dados não consumidos usando o campo SQL: overflow-field (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- unconsumed data
- storing unconsumed data
- retrieving unconsumed data
- annotated XSD schemas, unconsumed data
- overflow data [SQLXML]
- sql:overflow-field
ms.assetid: 8526998d-b47d-4a32-8dc2-7f50a8d11097
author: rothja
ms.author: jroth
ms.openlocfilehash: 796fda9428954c5f18c5d37b353de9fd4122551e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582372"
---
# <a name="retrieving-unconsumed-data-using-the-sqloverflow-field-sqlxml-40"></a><span data-ttu-id="6deec-102">Recuperando dados não consumidos usando sql:overflow-field (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="6deec-102">Retrieving Unconsumed Data Using the sql:overflow-field (SQLXML 4.0)</span></span>
  <span data-ttu-id="6deec-103">Quando forem inseridos registros em um banco de dados a partir de um documento XML usando a função OPENXML do [!INCLUDE[tsql](../../includes/tsql-md.md)], todos os dados não consumidos no documento XML de origem poderão ser armazenados em uma coluna.</span><span class="sxs-lookup"><span data-stu-id="6deec-103">When records are inserted in a database from an XML document by using the [!INCLUDE[tsql](../../includes/tsql-md.md)] OPENXML function, all the unconsumed data from the source XML document can be stored in a column.</span></span> <span data-ttu-id="6deec-104">Ao recuperar os dados de um banco de dados usando esquemas anotados, o atributo `sql:overflow-field` pode ser especificado para identificar a coluna da tabela na qual os dados de estouro estão armazenados.</span><span class="sxs-lookup"><span data-stu-id="6deec-104">When you retrieve data from a database by using annotated schemas, you can specify the `sql:overflow-field` attribute to identify the column in the table in which the overflow data is stored.</span></span> <span data-ttu-id="6deec-105">O `sql:overflow-field` atributo pode ser especificado em **\<element>** .</span><span class="sxs-lookup"><span data-stu-id="6deec-105">The `sql:overflow-field` attribute can be specified on **\<element>**.</span></span>  
  
 <span data-ttu-id="6deec-106">Em seguida, esses dados são recuperados destas formas:</span><span class="sxs-lookup"><span data-stu-id="6deec-106">This data is then retrieved in these ways:</span></span>  
  
-   <span data-ttu-id="6deec-107">Os atributos armazenados na coluna de estouro são adicionados ao elemento que contém a anotação `sql:overflow-field`.</span><span class="sxs-lookup"><span data-stu-id="6deec-107">Attributes stored in the overflow column are added to the element that contains the `sql:overflow-field` annotation.</span></span>  
  
-   <span data-ttu-id="6deec-108">Os elementos filhos e seus descendentes, armazenados na coluna de estouro do banco de dados, são adicionados como elementos filhos, após o conteúdo que é especificado explicitamente no esquema.</span><span class="sxs-lookup"><span data-stu-id="6deec-108">The child elements and their descendents, stored in the overflow column in the database, are added as child elements following the content that is explicitly specified in the schema.</span></span> <span data-ttu-id="6deec-109">(Nenhuma ordem é preservada.)</span><span class="sxs-lookup"><span data-stu-id="6deec-109">(No order is preserved.)</span></span>  
  
## <a name="examples"></a><span data-ttu-id="6deec-110">Exemplos</span><span class="sxs-lookup"><span data-stu-id="6deec-110">Examples</span></span>  
 <span data-ttu-id="6deec-111">Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="6deec-111">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="6deec-112">Para obter mais informações, consulte [Requirements for running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="6deec-112">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-sqloverflow-field-for-an-element"></a><span data-ttu-id="6deec-113">a.</span><span class="sxs-lookup"><span data-stu-id="6deec-113">A.</span></span> <span data-ttu-id="6deec-114">Especificando sql:overflow-field para um elemento</span><span class="sxs-lookup"><span data-stu-id="6deec-114">Specifying sql:overflow-field for an element</span></span>  
 <span data-ttu-id="6deec-115">Este exemplo presume que o seguinte script foi executado de forma que existe uma tabela chamada Customers2 no banco de dados tempdb:</span><span class="sxs-lookup"><span data-stu-id="6deec-115">This example assumes that the following script has been run so that a table named Customers2 exists in the tempdb database:</span></span>  
  
```  
USE tempdb  
CREATE TABLE Customers2 (  
CustomerID       VARCHAR(10),   
ContactName    VARCHAR(30),   
AddressOverflow    NVARCHAR(500))  
  
GO  
INSERT INTO Customers2 VALUES (  
'ALFKI',   
'Joe',  
'<Address>  
  <Address1>Maple St.</Address1>  
  <Address2>Apt. E105</Address2>  
  <City>Seattle</City>  
  <State>WA</State>  
  <Zip>98147</Zip>  
 </Address>')  
GO  
```  
  
 <span data-ttu-id="6deec-116">Além disso, você deve criar um diretório virtual para o banco de dados tempdb-e um nome virtual de modelo do `template` tipo chamado "template".</span><span class="sxs-lookup"><span data-stu-id="6deec-116">In addition, you must create a virtual directory for the tempdb database-and a template virtual name of `template` type named "template".</span></span>  
  
 <span data-ttu-id="6deec-117">No exemplo a seguir, o esquema de mapeamento recupera os dados não consumidos que são armazenados na coluna AddressOverflow tabela Customers2:</span><span class="sxs-lookup"><span data-stu-id="6deec-117">In the following example, the mapping schema retrieves the unconsumed data that is stored in the AddressOverflow column of the Customers2 table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Customers2" sql:overflow-field="AddressOverflow" >  
    <xsd:complexType>  
      <xsd:attribute name="CustomerID"  type="xsd:integer"/>  
      <xsd:attribute name="ContactName"  type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="6deec-118">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="6deec-118">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="6deec-119">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="6deec-119">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="6deec-120">Salve o arquivo como Overflow.xml.</span><span class="sxs-lookup"><span data-stu-id="6deec-120">Save the file as Overflow.xml.</span></span>  
  
2.  <span data-ttu-id="6deec-121">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="6deec-121">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="6deec-122">Salve o arquivo como OverflowT.xml no mesmo diretório em que você salvou Overflow.xml.</span><span class="sxs-lookup"><span data-stu-id="6deec-122">Save the file as OverflowT.xml in the same directory where you saved Overflow.xml.</span></span> <span data-ttu-id="6deec-123">A consulta no modelo seleciona os registros na tabela Customer2.</span><span class="sxs-lookup"><span data-stu-id="6deec-123">The query in the template selects the records in the Customers2 table.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="Overflow.xml">  
            /Customers2  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="6deec-124">O caminho de diretório especificado para o esquema de mapeamento (Overflow.xml) é relativo ao diretório no qual o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="6deec-124">The directory path specified for the mapping schema (Overflow.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="6deec-125">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="6deec-125">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\Overflow.xml"  
    ```  
  
3.  <span data-ttu-id="6deec-126">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="6deec-126">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="6deec-127">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="6deec-127">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="6deec-128">Este é o conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="6deec-128">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Customers2 CustomerID="ALFKI" ContactName="Joe">  
    <Address1>Maple St.</Address1>   
    <Address2>Apt. E105</Address2>   
    <City>Seattle</City>   
    <State>WA</State>   
    <Zip>98147</Zip>   
  </Customers2>  
</ROOT>  
```  
  
  
