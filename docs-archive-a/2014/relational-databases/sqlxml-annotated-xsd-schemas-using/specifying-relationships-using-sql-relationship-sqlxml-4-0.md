---
title: 'Especificando relações usando SQL: relationship (SQLXML 4,0) | Microsoft Docs'
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- IDREFS relationships [SQLXML]
- parent attribute [SQLXML]
- element relationships [SQLXML]
- multiple element relationships
- attribute relationships [SQLXML]
- sql:relationship
- relationship chains [SQLXML]
- IDREF relationships [SQLXML]
- parent-child relationships [SQLXML]
- relationship annotation
- XSD schemas [SQLXML], relationships
- annotated XSD schemas, relationships
- relationships [SQLXML], specifying
- unnamed relationships
- ID relationships [SQLXML]
- hierarchical relationships [SQLXML]
- named relationships [SQLXML]
ms.assetid: 98820afa-74e1-4e62-b336-6111a3dede4c
author: rothja
ms.author: jroth
ms.openlocfilehash: 42c703de9d564580eb0baa1349a45b193109c87a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573902"
---
# <a name="specifying-relationships-using-sqlrelationship-sqlxml-40"></a><span data-ttu-id="e9d4e-102">Especificando relações usando sql:relationship (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e9d4e-102">Specifying Relationships Using sql:relationship (SQLXML 4.0)</span></span>
  <span data-ttu-id="e9d4e-103">Os elementos em um documento XML podem ser relacionados.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-103">The elements in an XML document can be related.</span></span> <span data-ttu-id="e9d4e-104">Eles podem ser aninhados hierarquicamente e as relações ID, IDREF ou IDREFS entre os elementos podem ser especificadas.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-104">The elements can be nested hierarchically, and ID, IDREF, or IDREFS relationships can be specified between the elements.</span></span>  
  
 <span data-ttu-id="e9d4e-105">Por exemplo, em um esquema XSD, um **\<Customer>** elemento contém **\<Order>** elementos filho.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-105">For example, in an XSD schema, a **\<Customer>** element contains **\<Order>** child elements.</span></span> <span data-ttu-id="e9d4e-106">Quando o esquema é mapeado para o banco de dados AdventureWorks, o elemento é mapeado **\<Customer>** para a tabela Sales. Customer e o **\<Order>** elemento é mapeado para a tabela Sales. SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-106">When the schema is mapped to the AdventureWorks database, the **\<Customer>** element maps to the Sales.Customer table and the **\<Order>** element maps to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="e9d4e-107">Essas tabelas subjacentes, Sales. Customer e Sales. SalesOrderHeader, estão relacionadas porque os clientes colocam pedidos.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-107">These underlying tables, Sales.Customer and Sales.SalesOrderHeader, are related because customers place orders.</span></span> <span data-ttu-id="e9d4e-108">O elemento CustomerID na tabela Sales.SalesOrderHeader é uma chave estrangeira que se refere à chave primária CustomerID na tabela Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-108">The CustomerID in the Sales.SalesOrderHeader table is a foreign key referring to the CustomerID primary key in the Sales.Customer table.</span></span> <span data-ttu-id="e9d4e-109">Você pode estabelecer estas relações entre mapear elementos de esquema usando a anotação `sql:relationship`.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-109">You can establish these relationships among mapping schema elements by using the `sql:relationship` annotation.</span></span>  
  
 <span data-ttu-id="e9d4e-110">No esquema XSD anotado, a anotação `sql:relationship` é usada para aninhar os elementos de esquema hierarquicamente, com base nas relações de chave primária e chave estrangeira entre as tabelas subjacentes para as quais os elementos são mapeados.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-110">In the annotated XSD schema, the `sql:relationship` annotation is used to nest the schema elements hierarchically, on the basis of primary key and foreign key relationships among the underlying tables to which the elements map.</span></span> <span data-ttu-id="e9d4e-111">Na especificação da anotação `sql:relationship`, você deve identificar o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-111">In specifying the `sql:relationship` annotation, you must identify the following:</span></span>  
  
-   <span data-ttu-id="e9d4e-112">A tabela pai (Sales.Customer) e a tabela filha (Sales.SalesOrderHeader).</span><span class="sxs-lookup"><span data-stu-id="e9d4e-112">The parent table (Sales.Customer) and the child table (Sales.SalesOrderHeader).</span></span>  
  
-   <span data-ttu-id="e9d4e-113">A coluna ou as colunas que compõem a relação entre as tabelas pai e filha.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-113">The column or columns that compose the relationship between the parent and child tables.</span></span> <span data-ttu-id="e9d4e-114">Por exemplo, a coluna CustomerID que aparece nas tabelas pai e filha.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-114">For example, the CustomerID column, which appears in both the parent and child tables.</span></span>  
  
 <span data-ttu-id="e9d4e-115">Estas informações são usadas para gerar a hierarquia adequada.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-115">This information is used to generate the proper hierarchy.</span></span>  
  
 <span data-ttu-id="e9d4e-116">Para fornecer os nomes de tabela e as informações de junção necessárias, os seguintes atributos são especificados na anotação `sql:relationship`.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-116">To provide the table names and the necessary join information, the following attributes are specified on the `sql:relationship` annotation.</span></span> <span data-ttu-id="e9d4e-117">Esses atributos são válidos somente com o **\<sql:relationship>** elemento:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-117">These attributes are valid only with the **\<sql:relationship>** element:</span></span>  
  
 <span data-ttu-id="e9d4e-118">**Nome**</span><span class="sxs-lookup"><span data-stu-id="e9d4e-118">**Name**</span></span>  
 <span data-ttu-id="e9d4e-119">Especifica o nome exclusivo da relação.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-119">Specifies the unique name of the relationship.</span></span>  
  
 <span data-ttu-id="e9d4e-120">**Parent**</span><span class="sxs-lookup"><span data-stu-id="e9d4e-120">**Parent**</span></span>  
 <span data-ttu-id="e9d4e-121">Especifica a relação pai (tabela).</span><span class="sxs-lookup"><span data-stu-id="e9d4e-121">Specifies the parent relation (table).</span></span> <span data-ttu-id="e9d4e-122">Este é um atributo opcional. Se o atributo não for especificado, o nome da tabela pai será obtido das informações na hierarquia filha no documento.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-122">This is an optional attribute; if the attribute is not specified, the parent table name is obtained from information in the child hierarchy in the document.</span></span> <span data-ttu-id="e9d4e-123">Se o esquema especificar duas hierarquias pai-filho que usam os mesmos **\<sql:relationship>** elementos pai, mas diferentes, você não especificar o atributo pai no **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="e9d4e-123">If the schema specifies two parent-child hierarchies that use the same **\<sql:relationship>** but different parent elements, you do not specify the parent attribute in **\<sql:relationship>**.</span></span> <span data-ttu-id="e9d4e-124">Essas informações são obtidas da hierarquia no esquema.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-124">This information is obtained from the hierarchy in the schema.</span></span>  
  
 <span data-ttu-id="e9d4e-125">**parent-key**</span><span class="sxs-lookup"><span data-stu-id="e9d4e-125">**parent-key**</span></span>  
 <span data-ttu-id="e9d4e-126">Especifica a chave pai do pai.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-126">Specifies the parent key of the parent.</span></span> <span data-ttu-id="e9d4e-127">Se a chave pai for composta por várias colunas, os valores serão especificados com um espaço entre eles.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-127">If the parent key is composed of multiple columns, values are specified with a space between them.</span></span> <span data-ttu-id="e9d4e-128">Há um mapeamento posicional entre os valores que são especificados para a chave de várias colunas e para a chave filha correspondente.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-128">There is a positional mapping between the values that are specified for the multicolumn key and for the corresponding child key.</span></span>  
  
 <span data-ttu-id="e9d4e-129">**Filho**</span><span class="sxs-lookup"><span data-stu-id="e9d4e-129">**Child**</span></span>  
 <span data-ttu-id="e9d4e-130">Especifica a relação de filho (tabela).</span><span class="sxs-lookup"><span data-stu-id="e9d4e-130">Specifies the child relation (table).</span></span>  
  
 <span data-ttu-id="e9d4e-131">**child-key**</span><span class="sxs-lookup"><span data-stu-id="e9d4e-131">**child-key**</span></span>  
 <span data-ttu-id="e9d4e-132">Especifica a chave filha no filho que se refere à parent-key no pai.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-132">Specifies the child key in the child referring to parent-key in parent.</span></span> <span data-ttu-id="e9d4e-133">Se a chave filha for composta por vários atributos (colunas), os valores de child-key serão especificados com um espaço entre eles.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-133">If the child key is composed of multiple attributes (columns), the child-key values are specified with a space between them.</span></span> <span data-ttu-id="e9d4e-134">Há um mapeamento posicional entre os valores que são especificados para a chave de várias colunas e para a chave pai correspondente.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-134">There is a positional mapping between the values that are specified for the multicolumn key and for the corresponding parent key.</span></span>  
  
 <span data-ttu-id="e9d4e-135">**Inverse**</span><span class="sxs-lookup"><span data-stu-id="e9d4e-135">**Inverse**</span></span>  
 <span data-ttu-id="e9d4e-136">Esse atributo especificado em **\<sql:relationship>** é usado por Updategrams.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-136">This attribute specified on **\<sql:relationship>** is used by updategrams.</span></span> <span data-ttu-id="e9d4e-137">Para obter mais informações, consulte [especificando o atributo SQL: inverso em SQL: relationship](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e9d4e-137">For more information, see [Specifying the sql:inverse Attribute on sql:relationship](specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="e9d4e-138">A `sql:key-fields` anotação deve ser especificada em um elemento que contenha um elemento filho, que tenha um **\<sql:relationship>** definido entre o elemento e o filho, e que não forneça a chave primária da tabela especificada no elemento pai.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-138">The `sql:key-fields` annotation must be specified in an element that contains a child element, that has a **\<sql:relationship>** defined between the element and the child, and that does not provide the primary key of the table specified in the parent element.</span></span> <span data-ttu-id="e9d4e-139">Mesmo que o esquema não especifique **\<sql:relationship>** , você deve especificar `sql:key-fields` para produzir a hierarquia apropriada.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-139">Even if the schema does not specify **\<sql:relationship>**, you must specify `sql:key-fields` to produce the proper hierarchy.</span></span> <span data-ttu-id="e9d4e-140">Para obter mais informações, consulte [identificando colunas de chave usando SQL: key-fields](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e9d4e-140">For more information, see [Identifying Key Columns by Using sql:key-fields](identifying-key-columns-using-sql-key-fields-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="e9d4e-141">Para gerar o aninhamento adequado no resultado, recomenda-se que `sql:key-fields` sejam especificados em todos os esquemas.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-141">To produce proper nesting in the result, it is recommended that `sql:key-fields` are specified in all schemas.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e9d4e-142">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e9d4e-142">Examples</span></span>  
 <span data-ttu-id="e9d4e-143">Para criar exemplos de funcionamento usando os exemplos a seguir, é necessário atender a determinados requisitos.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-143">To create working samples using the following examples, you must meet certain requirements.</span></span> <span data-ttu-id="e9d4e-144">Para obter mais informações, consulte [Requirements for running SQLXML examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="e9d4e-144">For more information, see [Requirements for Running SQLXML Examples](../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-specifying-the-sqlrelationship-annotation-on-an-element"></a><span data-ttu-id="e9d4e-145">a.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-145">A.</span></span> <span data-ttu-id="e9d4e-146">Especificando uma anotação sql:relationship em um elemento</span><span class="sxs-lookup"><span data-stu-id="e9d4e-146">Specifying the sql:relationship annotation on an element</span></span>  
 <span data-ttu-id="e9d4e-147">O esquema XSD anotado a seguir **\<Customer>** inclui **\<Order>** elementos e.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-147">The following annotated XSD schema includes **\<Customer>** and **\<Order>** elements.</span></span> <span data-ttu-id="e9d4e-148">O **\<Order>** elemento é um elemento filho do **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-148">The **\<Order>** element is a child element of the **\<Customer>** element.</span></span>  
  
 <span data-ttu-id="e9d4e-149">No esquema, a `sql:relationship` anotação é especificada no **\<Order>** elemento filho.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-149">In the schema, the `sql:relationship` annotation is specified on the **\<Order>** child element.</span></span> <span data-ttu-id="e9d4e-150">A relação em si é definida no **\<xsd:appinfo>** elemento.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-150">The relationship itself is defined in the **\<xsd:appinfo>** element.</span></span>  
  
 <span data-ttu-id="e9d4e-151">O **\<relationship>** elemento identifica CustomerID na tabela Sales. SalesOrderHeader como uma chave estrangeira que se refere à chave primária CustomerID na tabela Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-151">The **\<relationship>** element identifies CustomerID in the Sales.SalesOrderHeader table as a foreign key that refers to the CustomerID primary key in the Sales.Customer table.</span></span> <span data-ttu-id="e9d4e-152">Portanto, os pedidos que pertencem a um cliente aparecem como um elemento filho desse **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-152">Therefore, orders that belong to a customer appear as a child element of that **\<Customer>** element.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"  
                    sql:relationship="CustOrders" >  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="e9d4e-153">O esquema anterior usa uma relação nomeada.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-153">The previous schema uses a named relationship.</span></span> <span data-ttu-id="e9d4e-154">Você pode também especificar uma relação sem-nome.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-154">You can also specify an unnamed relationship.</span></span> <span data-ttu-id="e9d4e-155">Os resultados são os mesmos.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-155">The results are same.</span></span>  
  
 <span data-ttu-id="e9d4e-156">Este é o esquema revisado no qual uma relação sem-nome é especificada:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-156">This is the revised schema in which an unnamed relationship is specified:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer"  type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader">  
           <xsd:annotation>  
            <xsd:appinfo>  
              <sql:relationship   
                parent="Sales.Customer"  
                parent-key="CustomerID"  
                child="Sales.SalesOrderHeader"  
                child-key="CustomerID" />  
            </xsd:appinfo>  
           </xsd:annotation>  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e9d4e-157">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="e9d4e-157">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e9d4e-158">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-158">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="e9d4e-159">Salve o arquivo como sql-relationship.xml.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-159">Save the file as sql-relationship.xml.</span></span>  
  
2.  <span data-ttu-id="e9d4e-160">Copie o seguinte modelo abaixo e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-160">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="e9d4e-161">Salve o arquivo como sql-relationshipT.xml no mesmo diretório em que você salvou sql-relationship.xml.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-161">Save the file as sql-relationshipT.xml in the same directory where you saved sql-relationship.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="sql-relationship.xml">  
            /Customer[@CustomerID=1]  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e9d4e-162">O caminho de diretório especificado para o esquema de mapeamento (sql-relationship.xml) é relativo ao diretório onde o modelo é salvo.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-162">The directory path specified for the mapping schema (sql-relationship.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e9d4e-163">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-163">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\sql-relationship.xml"  
    ```  
  
3.  <span data-ttu-id="e9d4e-164">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-164">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e9d4e-165">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e9d4e-165">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e9d4e-166">Este é o conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-166">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer CustomerID="1">   
    <Order OrderID="43860" CustomerID="1" />   
    <Order OrderID="44501" CustomerID="1" />   
    <Order OrderID="45283" CustomerID="1" />   
    <Order OrderID="46042" CustomerID="1" />   
  </Customer>   
</ROOT>  
```  
  
### <a name="b-specifying-a-relationship-chain"></a><span data-ttu-id="e9d4e-167">B.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-167">B.</span></span> <span data-ttu-id="e9d4e-168">Especificando uma cadeia de relações</span><span class="sxs-lookup"><span data-stu-id="e9d4e-168">Specifying a relationship chain</span></span>  
 <span data-ttu-id="e9d4e-169">Para obter este exemplo, pressuponha que você deseja o seguinte documento XML que use dados obtidos do banco de dados AdventureWorks:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-169">For this example, assume that you want the following XML document using data obtained from the AdventureWorks database:</span></span>  
  
```  
<Order SalesOrderID="43659">  
  <Product Name="Mountain Bike Socks, M"/>   
  <Product Name="Sport-100 Helmet, Blue"/>  
  ...  
</Order>  
...  
```  
  
 <span data-ttu-id="e9d4e-170">Para cada pedido na tabela Sales. SalesOrderHeader, o documento XML tem um **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-170">For each order in the Sales.SalesOrderHeader table, the XML document has one **\<Order>** element.</span></span> <span data-ttu-id="e9d4e-171">E cada **\<Order>** elemento tem uma lista de **\<Product>** elementos filho, um para cada produto solicitado na ordem.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-171">And each **\<Order>** element has a list of **\<Product>** child elements, one for each product requested in the order.</span></span>  
  
 <span data-ttu-id="e9d4e-172">Para especificar um esquema XSD que gerará esta hierarquia, você deve especificar duas relações: OrderOD e ODProduct.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-172">To specify an XSD schema that will produce this hierarchy, you must specify two relationships: OrderOD and ODProduct.</span></span> <span data-ttu-id="e9d4e-173">A relação OrderOD especifica a relação pai-filho entre as tabelas Sales.SalesOrderHeader e Sales.SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-173">The OrderOD relationship specifies the parent-child relationship between the Sales.SalesOrderHeader and Sales.SalesOrderDetail tables.</span></span> <span data-ttu-id="e9d4e-174">A relação ODProduct especifica a relação entre as tabelas Sales.SalesOrderDetail e Production.Product.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-174">The ODProduct relationship specifies the relationship between the Sales.SalesOrderDetail and Production.Product tables.</span></span>  
  
 <span data-ttu-id="e9d4e-175">No esquema a seguir, a `msdata:relationship` anotação no **\<Product>** elemento especifica dois valores: OrderOD e ODProduct.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-175">In the following schema, the `msdata:relationship` annotation on the **\<Product>** element specifies two values: OrderOD and ODProduct.</span></span> <span data-ttu-id="e9d4e-176">A ordem em que esses valores são especificados é importante.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-176">The order in which these values are specified is important.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <msdata:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  
    <msdata:relationship name="ODProduct"  
          parent="Sales.SalesOrderDetail"  
          parent-key="ProductID"  
          child="Production.Product"  
          child-key="ProductID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Order" msdata:relation="Sales.SalesOrderHeader"   
               msdata:key-fields="SalesOrderID" type="OrderType" />  
   <xsd:complexType name="OrderType" >  
     <xsd:sequence>  
        <xsd:element name="Product" msdata:relation="Production.Product"   
                     msdata:key-fields="ProductID"  
                     msdata:relationship="OrderOD ODProduct">  
          <xsd:complexType>  
             <xsd:attribute name="Name" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="SalesOrderID"   type="xsd:integer" />   
    </xsd:complexType>  
</xsd:schema>  
```  
  
 <span data-ttu-id="e9d4e-177">Em vez de especificar uma relação nomeada, você pode especificar uma relação anônima.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-177">Instead of specifying a named relationship, you can specify an anonymous relationship.</span></span> <span data-ttu-id="e9d4e-178">Nesse caso, todo o conteúdo de **\<annotation>** ... **\</annotation>** , que descreve as duas relações, aparece como um elemento filho de **\<Product>** .</span><span class="sxs-lookup"><span data-stu-id="e9d4e-178">In this case, the entire contents of **\<annotation>**...**\</annotation>**, which describes the two relationships, appear as a child element of **\<Product>**.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:msdata="urn:schemas-microsoft-com:mapping-schema">  
  
  <xsd:element name="Order" msdata:relation="Sales.SalesOrderHeader"   
               msdata:key-fields="SalesOrderID" type="OrderType" />  
  
   <xsd:complexType name="OrderType" >  
     <xsd:sequence>  
        <xsd:element name="Product" msdata:relation="Production.Product"   
                     msdata:key-fields="ProductID" >  
         <xsd:annotation>  
          <xsd:appinfo>  
           <msdata:relationship   
               parent="Sales.SalesOrderHeader"  
               parent-key="SalesOrderID"  
               child="Sales.SalesOrderDetail"  
               child-key="SalesOrderID" />  
  
           <msdata:relationship   
               parent="Sales.SalesOrderDetail"  
               parent-key="ProductID"  
               child="Production.Product"  
               child-key="ProductID" />  
         </xsd:appinfo>  
       </xsd:annotation>  
       <xsd:complexType>  
          <xsd:attribute name="Name" type="xsd:string" />  
       </xsd:complexType>  
     </xsd:element>  
   </xsd:sequence>  
   <xsd:attribute name="SalesOrderID"   type="xsd:integer" />   
  </xsd:complexType>  
 </xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e9d4e-179">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="e9d4e-179">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e9d4e-180">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-180">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="e9d4e-181">Salve o arquivo como relationshipChain.xml.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-181">Save the file as relationshipChain.xml.</span></span>  
  
2.  <span data-ttu-id="e9d4e-182">Copie o seguinte modelo abaixo e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-182">Copy the following template below and paste it into a text file.</span></span> <span data-ttu-id="e9d4e-183">Salve o arquivo como relationshipChainT.xml no mesmo diretório em que você salvou relationshipChain.xml.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-183">Save the file as relationshipChainT.xml in the same directory where you saved relationshipChain.xml.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="relationshipChain.xml">  
            /Order  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e9d4e-184">O caminho de diretório especificado para o esquema de mapeamento (relationshipChain.xml) é relativo ao diretório onde o modelo é salvo.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-184">The directory path specified for the mapping schema (relationshipChain.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e9d4e-185">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-185">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationshipChain.xml"  
    ```  
  
3.  <span data-ttu-id="e9d4e-186">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-186">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e9d4e-187">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e9d4e-187">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e9d4e-188">Este é o conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-188">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Order SalesOrderID="43659">  
    <Product Name="Mountain Bike Socks, M" />   
    <Product Name="Sport-100 Helmet, Blue" />   
    <Product Name="AWC Logo Cap" />   
    <Product Name="Long-Sleeve Logo Jersey, M" />   
    <Product Name="Long-Sleeve Logo Jersey, XL" />   
    ...  
  </Order>  
  ...  
</ROOT>  
```  
  
### <a name="c-specifying-the-relationship-annotation-on-an-attribute"></a><span data-ttu-id="e9d4e-189">C.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-189">C.</span></span> <span data-ttu-id="e9d4e-190">Especificando a anotação de relação em um atributo</span><span class="sxs-lookup"><span data-stu-id="e9d4e-190">Specifying the relationship annotation on an attribute</span></span>  
 <span data-ttu-id="e9d4e-191">O esquema neste exemplo inclui um \<Customer> elemento com um \<CustomerID> elemento filho e um atributo OrderIDList do tipo IDREFS.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-191">The schema in this example includes a \<Customer> element with a \<CustomerID> child element and an OrderIDList attribute of IDREFS type.</span></span> <span data-ttu-id="e9d4e-192">O \<Customer> elemento é mapeado para a tabela Sales. Customer no banco de dados AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-192">The \<Customer> element maps to the Sales.Customer table in the AdventureWorks database.</span></span> <span data-ttu-id="e9d4e-193">Por padrão, o escopo desse mapeamento se aplica a todos os elementos filho ou atributos, a menos que `sql:relation` seja especificado no elemento ou atributo filho; nesse caso, a relação de chave primária/chave estrangeira apropriada deve ser definida usando o \<relationship> elemento.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-193">By default, the scope of this mapping applies to all the child elements or attributes unless `sql:relation` is specified on the child element or attribute, in which case, the appropriate primary-key/foreign-key relationship must be defined using the \<relationship> element.</span></span> <span data-ttu-id="e9d4e-194">E o elemento ou atributo filho, que especifica a tabela diferente usando a anotação `relation`, deve também especificar a anotação `relationship`.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-194">And the child element or attribute, which specifies the different table using the `relation` annotation, must also specify the `relationship` annotation.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
          parent="Sales.Customer"  
          parent-key="CustomerID"  
          child="Sales.SalesOrderHeader"  
          child-key="CustomerID" />  
     </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" type="CustomerType" />  
   <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="CustomerID"   type="xsd:string" />   
     </xsd:sequence>  
     <xsd:attribute name="OrderIDList"   
                     type="xsd:IDREFS"   
                     sql:relation="Sales.SalesOrderHeader"   
                     sql:field="SalesOrderID"  
                     sql:relationship="CustOrders" >  
        </xsd:attribute>  
    </xsd:complexType>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e9d4e-195">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="e9d4e-195">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e9d4e-196">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-196">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="e9d4e-197">Salve o arquivo como relationship-on-attribute.xml.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-197">Save the file as relationship-on-attribute.xml.</span></span>  
  
2.  <span data-ttu-id="e9d4e-198">Copie o seguinte modelo e cole-o em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-198">Copy the following template and paste it into a file.</span></span> <span data-ttu-id="e9d4e-199">Salve o arquivo como relationship-on-attributeT.xml no mesmo diretório onde você salvou relationship-on-attribute.xml.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-199">Save the file as relationship-on-attributeT.xml in the same directory where you saved relationship-on-attribute.xml.</span></span> <span data-ttu-id="e9d4e-200">A consulta no modelo seleciona um cliente com o CustomerID 1.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-200">The query in the template selects a customer with the CustomerID of 1.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="relationship-on-attribute.xml">  
        /Customer[CustomerID=1]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e9d4e-201">O caminho de diretório especificado para o esquema de mapeamento (relationship-on-attribute.xml) é relativo ao diretório onde o modelo é salvo.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-201">The directory path specified for the mapping schema (relationship-on-attribute.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e9d4e-202">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-202">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-on-attribute.xml"  
    ```  
  
3.  <span data-ttu-id="e9d4e-203">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-203">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e9d4e-204">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e9d4e-204">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e9d4e-205">Este é o conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-205">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">   
  <Customer OrderIDList="43860 44501 45283 46042">  
    <CustomerID>1</CustomerID>   
  </Customer>  
</ROOT>  
```  
  
### <a name="d-specifying-sqlrelationship-on-multiple-elements"></a><span data-ttu-id="e9d4e-206">D.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-206">D.</span></span> <span data-ttu-id="e9d4e-207">Especificando sql:relationship em vários elementos</span><span class="sxs-lookup"><span data-stu-id="e9d4e-207">Specifying sql:relationship on multiple elements</span></span>  
 <span data-ttu-id="e9d4e-208">Neste exemplo, o esquema XSD anotado contém os **\<Customer>** elementos, **\<Order>** e **\<OrderDetail>** .</span><span class="sxs-lookup"><span data-stu-id="e9d4e-208">In this example, the annotated XSD schema contains the **\<Customer>**, **\<Order>**, and **\<OrderDetail>** elements.</span></span>  
  
 <span data-ttu-id="e9d4e-209">O **\<Order>** elemento é um elemento filho do **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-209">The **\<Order>** element is a child element of the **\<Customer>** element.</span></span> <span data-ttu-id="e9d4e-210">**\<sql:relationship>** é especificado no **\<Order>** elemento filho; portanto, os pedidos que pertencem a um cliente aparecem como elementos filho de **\<Customer>** .</span><span class="sxs-lookup"><span data-stu-id="e9d4e-210">**\<sql:relationship>** is specified on the **\<Order>** child element; therefore, orders that belong to a customer appear as child elements of **\<Customer>**.</span></span>  
  
 <span data-ttu-id="e9d4e-211">O **\<Order>** elemento inclui o **\<OrderDetail>** elemento filho.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-211">The **\<Order>** element includes the **\<OrderDetail>** child element.</span></span> <span data-ttu-id="e9d4e-212">**\<sql:relationship>** é especificado no **\<OrderDetail>** elemento filho, portanto, os detalhes do pedido que pertencem a uma ordem aparecem como elementos filho desse **\<Order>** elemento.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-212">**\<sql:relationship>** is specified on **\<OrderDetail>** child element, so the order details that pertain to an order appear as child elements of that **\<Order>** element.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="CustOrders"  
        parent="Sales.Customer"  
        parent-key="CustomerID"  
        child="Sales.SalesOrderHeader"  
        child-key="CustomerID" />  
  
    <sql:relationship name="OrderOrderDetail"  
        parent="Sales.SalesOrderHeader"  
        parent-key="SalesOrderID"  
        child="Sales.SalesOrderDetail"  
        child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader"    
              sql:relationship="CustOrders" maxOccurs="unbounded" >  
          <xsd:complexType>  
              <xsd:sequence>  
                <xsd:element name="OrderDetail"   
                             sql:relation="Sales.SalesOrderDetail"   
                             sql:relationship="OrderOrderDetail"   
                             maxOccurs="unbounded" >  
                  <xsd:complexType>  
                    <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
                    <xsd:attribute name="ProductID" type="xsd:string" />  
                    <xsd:attribute name="OrderQty" type="xsd:integer" />  
                  </xsd:complexType>  
                </xsd:element>  
              </xsd:sequence>  
              <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
              <xsd:attribute name="OrderDate" type="xsd:date" />  
              <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
      </xsd:sequence>  
      <xsd:attribute name="CustomerID" type="xsd:string" />  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e9d4e-213">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="e9d4e-213">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e9d4e-214">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-214">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="e9d4e-215">Salve o arquivo como relationship-multiple-elements.xml.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-215">Save the file as relationship-multiple-elements.xml.</span></span>  
  
2.  <span data-ttu-id="e9d4e-216">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-216">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="e9d4e-217">Salve o arquivo como relationship-multiple-elementsT.xml no mesmo diretório onde você salvou relationship-multiple-elements.xml.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-217">Save the file as relationship-multiple-elementsT.xml in the same directory where you saved relationship-multiple-elements.xml.</span></span> <span data-ttu-id="e9d4e-218">A consulta no modelo retorna informações de pedido por um cliente com o CustomerID de 1 e SalesOrderID de 43860.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-218">The query in the template returns order information for a customer with the CustomerID of 1 and SalesOrderID of 43860.</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
      <sql:xpath-query mapping-schema="relationship-multiple-elements.xml">  
        /Customer[@CustomerID=1]/Order[@SalesOrderID=43860]  
      </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e9d4e-219">O caminho de diretório especificado para o esquema de mapeamento (relationship-multiple-elements.xml) é relativo ao diretório onde o modelo é salvo.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-219">The directory path specified for the mapping schema (relationship-multiple-elements.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e9d4e-220">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-220">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-multiple-elements.xml"  
    ```  
  
3.  <span data-ttu-id="e9d4e-221">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-221">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e9d4e-222">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e9d4e-222">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e9d4e-223">Este é o conjunto de resultados:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-223">Here is the result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  <Order SalesOrderID="43860" OrderDate="2001-08-01" CustomerID="1">  
     <OrderDetail SalesOrderID="43860" ProductID="761" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="770" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="758" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="765" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="732" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="762" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="738" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="768" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="753" OrderQty="2" />   
     <OrderDetail SalesOrderID="43860" ProductID="729" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="763" OrderQty="1" />   
     <OrderDetail SalesOrderID="43860" ProductID="756" OrderQty="1" />   
  </Order>  
</ROOT>  
```  
  
### <a name="e-specifying-the-sqlrelationship-without-the-parent-attribute"></a><span data-ttu-id="e9d4e-224">E.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-224">E.</span></span> <span data-ttu-id="e9d4e-225">Especificando o \<sql:relationship> sem o atributo pai</span><span class="sxs-lookup"><span data-stu-id="e9d4e-225">Specifying the \<sql:relationship> without the parent attribute</span></span>  
 <span data-ttu-id="e9d4e-226">Este exemplo ilustra a especificação de **\<sql:relationship>** sem o atributo **pai** .</span><span class="sxs-lookup"><span data-stu-id="e9d4e-226">This example illustrates specifying the **\<sql:relationship>** without the **parent** attribute.</span></span> <span data-ttu-id="e9d4e-227">Por exemplo, pressuponha que você tenha as seguintes tabelas de funcionário:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-227">For example, assume you have the following employee tables:</span></span>  
  
```  
Emp1(SalesPersonID, FirstName, LastName, ReportsTo)  
Emp2(SalesPersonID, FirstName, LastName, ReportsTo)  
```  
  
 <span data-ttu-id="e9d4e-228">O seguinte modo de exibição XML tem os **\<Emp1>** **\<Emp2>** elementos e mapeando para as tabelas Sales. emp1 e Sales. Emp2:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-228">The following XML view has the **\<Emp1>** and **\<Emp2>** elements mapping to the Sales.Emp1 and Sales.Emp2 tables:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="EmpOrders"  
          parent-key="SalesPersonID"  
          child="Sales.SalesOrderHeader"  
          child-key="SalesPersonID" />  
     </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Emp1" sql:relation="Sales.Emp1" type="EmpType" />  
  <xsd:element name="Emp2" sql:relation="Sales.Emp2" type="EmpType" />  
   <xsd:complexType name="EmpType" >  
     <xsd:sequence>  
        <xsd:element name="Order"   
                     sql:relation="Sales.SalesOrderHeader"   
                     sql:relationship="EmpOrders" >  
          <xsd:complexType>  
             <xsd:attribute name="SalesOrderID" type="xsd:integer" />  
             <xsd:attribute name="CustomerID" type="xsd:string" />  
          </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="SalesPersonID"   type="xsd:integer" />   
        <xsd:attribute name="LastName"   type="xsd:string" />   
    </xsd:complexType>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="e9d4e-229">No esquema, o **\<Emp1>** elemento e o **\<Emp2>** elemento são do tipo `EmpType` .</span><span class="sxs-lookup"><span data-stu-id="e9d4e-229">In the schema, both the **\<Emp1>** element and **\<Emp2>** element are of type `EmpType`.</span></span> <span data-ttu-id="e9d4e-230">O tipo `EmpType` descreve um **\<Order>** elemento filho e o correspondente **\<sql:relationship>** .</span><span class="sxs-lookup"><span data-stu-id="e9d4e-230">The type `EmpType` describes an **\<Order>** child element and the corresponding **\<sql:relationship>**.</span></span> <span data-ttu-id="e9d4e-231">Nesse caso, não há um único pai que possa ser identificado no **\<sql:relationship>** usando o atributo **pai** .</span><span class="sxs-lookup"><span data-stu-id="e9d4e-231">In this case, there is no single parent that can be identified in **\<sql:relationship>** by using the **parent** attribute.</span></span> <span data-ttu-id="e9d4e-232">Nessa situação, você não especifica o atributo **pai** em **\<sql:relationship>** ; as informações de atributo **pai** são obtidas da hierarquia no esquema.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-232">In this situation, you don't specify the **parent** attribute in **\<sql:relationship>**; the **parent** attribute information is obtained from the hierarchy in the schema.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e9d4e-233">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="e9d4e-233">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e9d4e-234">Crie estas tabelas no banco de dados AdventureWorks:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-234">Create these tables in the AdventureWorks database:</span></span>  
  
    ```  
    USE AdventureWorks  
    CREATE TABLE Sales.Emp1 (  
           SalesPersonID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    Go  
    CREATE TABLE Sales.Emp2 (  
           SalesPersonID int primary key,   
           FirstName  varchar(20),   
           LastName   varchar(20),   
           ReportsTo int)  
    Go  
    ```  
  
2.  <span data-ttu-id="e9d4e-235">Adicione estes dados de exemplo nas tabelas:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-235">Add this sample data in the tables:</span></span>  
  
    ```  
    INSERT INTO Sales.Emp1 values (279, 'Nancy', 'Devolio',NULL)  
    INSERT INTO Sales.Emp1 values (282, 'Andrew', 'Fuller',1)  
    INSERT INTO Sales.Emp1 values (276, 'Janet', 'Leverling',1)  
    INSERT INTO Sales.Emp2 values (277, 'Margaret', 'Peacock',3)  
    INSERT INTO Sales.Emp2 values (283, 'Steven', 'Devolio',4)  
    INSERT INTO Sales.Emp2 values (275, 'Nancy', 'Buchanan',5)  
    INSERT INTO Sales.Emp2 values (281, 'Michael', 'Suyama',6)  
    ```  
  
3.  <span data-ttu-id="e9d4e-236">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-236">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="e9d4e-237">Salve o arquivo como relationship-noparent.xml.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-237">Save the file as relationship-noparent.xml.</span></span>  
  
4.  <span data-ttu-id="e9d4e-238">Copie o modelo a seguir e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-238">Copy the following template and paste it into a text file.</span></span> <span data-ttu-id="e9d4e-239">Salve o arquivo como relationship-noparentT.xml no mesmo diretório em que você salvou relationship-noparent.xml.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-239">Save the file as relationship-noparentT.xml in the same directory where you saved relationship-noparent.xml.</span></span> <span data-ttu-id="e9d4e-240">A consulta no modelo seleciona todos os \<Emp1> elementos (portanto, o pai é emp1).</span><span class="sxs-lookup"><span data-stu-id="e9d4e-240">The query in the template selects all the \<Emp1> elements (therefore, the parent is Emp1).</span></span>  
  
    ```  
    <ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
        <sql:xpath-query mapping-schema="relationship-noparent.xml">  
            /Emp1  
        </sql:xpath-query>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="e9d4e-241">O caminho de diretório especificado para o esquema de mapeamento (relationship-noparent.xml) é relativo ao diretório onde o modelo é salvo.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-241">The directory path specified for the mapping schema (relationship-noparent.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="e9d4e-242">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-242">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\MyDir\relationship-noparent.xml"  
    ```  
  
5.  <span data-ttu-id="e9d4e-243">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e9d4e-243">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e9d4e-244">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e9d4e-244">For more information, see [Using ADO to Execute SQLXML Queries](../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e9d4e-245">Aqui está um conjunto de resultados parciais:</span><span class="sxs-lookup"><span data-stu-id="e9d4e-245">Here is a partial result set:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
<Emp1 SalesPersonID="276" LastName="Leverling">  
  <Order SalesOrderID="43663" CustomerID="510" />   
  <Order SalesOrderID="43666" CustomerID="511" />   
  <Order SalesOrderID="43859" CustomerID="259" />  
  ...  
</Emp1>  
```  
  
  
