---
title: Especificando um esquema de mapeamento anotado em um updategram (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- annotated XSD schemas, updategrams
- data types [SQLXML], mapping schema in updategrams
- updategrams [SQLXML], annotated mapping schemas
- annotated XDR schemas, updategrams
- inverse attribute
- parent-child relationships [SQLXML]
- mapping-schema attribute
- mapping schema [SQLXML], updategrams
- sql:inverse
ms.assetid: 2e266ed9-4cfb-434a-af55-d0839f64bb9a
author: rothja
ms.author: jroth
ms.openlocfilehash: a181b3081b51cca160709703364c248e495e0214
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575742"
---
# <a name="specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-40"></a><span data-ttu-id="86284-102">Especificando um esquema de mapeamento anotado em um diagrama de atualização (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="86284-102">Specifying an Annotated Mapping Schema in an Updategram (SQLXML 4.0)</span></span>
  <span data-ttu-id="86284-103">Este tópico explica como o esquema de mapeamento (XSD ou XDR), especificado em um diagrama de atualização, é usado para processar as atualizações.</span><span class="sxs-lookup"><span data-stu-id="86284-103">This topic explains how the mapping schema (XSD or XDR) that is specified in an updategram is used to process the updates.</span></span> <span data-ttu-id="86284-104">Em um updategram, você pode fornecer o nome de um esquema de mapeamento anotado a ser usado no mapeamento dos elementos e atributos no updategram para tabelas e colunas no [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="86284-104">In an updategram, you can provide the name of an annotated mapping schema to use in mapping the elements and attributes in the updategram to tables and columns in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="86284-105">Quando um esquema de mapeamento é especificado em um diagrama de atualização, os nomes de elementos e atributos especificados no diagrama deverão ser mapeados para os elementos e atributos do esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="86284-105">When a mapping schema is specified in an updategram, the element and attribute names that are specified in the updategram must map to the elements and attributes in the mapping schema.</span></span>  
  
 <span data-ttu-id="86284-106">Para especificar um esquema de mapeamento, use o `mapping-schema` atributo do **\<sync>** elemento.</span><span class="sxs-lookup"><span data-stu-id="86284-106">To specify a mapping schema, you use the `mapping-schema` attribute of the **\<sync>** element.</span></span> <span data-ttu-id="86284-107">Os exemplos a seguir mostram dois diagramas de atualização: um que usa um esquema de mapeamento simples e outro que usa um esquema mais complexo.</span><span class="sxs-lookup"><span data-stu-id="86284-107">The following examples show two updategrams: one that uses a simple mapping schema, and one that uses a more complex schema.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="86284-108">Esta documentação parte do pressuposto de que você esteja familiarizado com suporte a modelos e ao esquema de mapeamento no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="86284-108">This documentation assumes that you are familiar with templates and mapping schema support in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="86284-109">Para obter mais informações, consulte [introdução aos esquemas XSD anotados &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="86284-109">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="86284-110">Para aplicativos herdados que usam XDR, consulte [esquemas XDR anotados &#40;preteridos no SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="86284-110">For legacy applications that use XDR, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="dealing-with-data-types"></a><span data-ttu-id="86284-111">Lidando com tipos de dados</span><span class="sxs-lookup"><span data-stu-id="86284-111">Dealing with Data Types</span></span>  
 <span data-ttu-id="86284-112">Se o esquema especificar o `image` `binary` tipo de dados, ou `varbinary` [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (usando `sql:datatype` ) e não especificar um tipo de dados XML, o updategram assumirá que o tipo de dados XML é `binary base 64` .</span><span class="sxs-lookup"><span data-stu-id="86284-112">If the schema specifies the `image`, `binary`, or `varbinary`[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type (by using `sql:datatype`) and does not specify an XML data type, the updategram assumes that the XML data type is `binary base 64`.</span></span> <span data-ttu-id="86284-113">Se seus dados forem do tipo `bin.base`, você deverá especificar explicitamente o tipo (`dt:type=bin.base` ou `type="xsd:hexBinary"`).</span><span class="sxs-lookup"><span data-stu-id="86284-113">If your data is `bin.base` type, you must explicitly specify the type (`dt:type=bin.base` or `type="xsd:hexBinary"`).</span></span>  
  
 <span data-ttu-id="86284-114">Se o esquema especificar o tipo de dados XSD `dateTime`, `date` ou `time`, você também deverá especificar o tipo de dados [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] correspondente usando `sql:datatype="dateTime"`.</span><span class="sxs-lookup"><span data-stu-id="86284-114">If the schema specifies the `dateTime`, `date`, or `time` XSD data type, you must also specify the corresponding [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] data type by using `sql:datatype="dateTime"`.</span></span>  
  
 <span data-ttu-id="86284-115">Ao manipular parâmetros do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `money` tipo, você deve especificar explicitamente `sql:datatype="money"` no nó apropriado no esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="86284-115">When handling parameters of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] `money` type, you must explicitly specify `sql:datatype="money"` on the appropriate node in the mapping schema.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="86284-116">Exemplos</span><span class="sxs-lookup"><span data-stu-id="86284-116">Examples</span></span>  
 <span data-ttu-id="86284-117">Para criar exemplos de trabalho usando os exemplos a seguir, você deve atender aos requisitos especificados em [requisitos para executar exemplos do SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="86284-117">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
### <a name="a-creating-an-updategram-with-a-simple-mapping-schema"></a><span data-ttu-id="86284-118">a.</span><span class="sxs-lookup"><span data-stu-id="86284-118">A.</span></span> <span data-ttu-id="86284-119">Criando um diagrama de atualização com um esquema de mapeamento simples</span><span class="sxs-lookup"><span data-stu-id="86284-119">Creating an updategram with a simple mapping schema</span></span>  
 <span data-ttu-id="86284-120">O seguinte esquema XSD (SampleSchema.xml) é um esquema de mapeamento que mapeia o **\<Customer>** elemento para a tabela Sales. Customer:</span><span class="sxs-lookup"><span data-stu-id="86284-120">The following XSD schema (SampleSchema.xml) is a mapping schema that maps the **\<Customer>** element to the Sales.Customer table:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="Customer" sql:relation="Sales.Customer" >  
   <xsd:complexType>  
        <xsd:attribute name="CustID"    
                       sql:field="CustomerID"   
                       type="xsd:string" />  
        <xsd:attribute name="RegionID"    
                       sql:field="TerritoryID"    
                       type="xsd:string" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="86284-121">O diagrama de atualização a seguir insere um registro na tabela Sales.Customer e usa o esquema de mapeamento anterior para mapear adequadamente esses dados para a tabela.</span><span class="sxs-lookup"><span data-stu-id="86284-121">The following updategram inserts a record into the Sales.Customer table and relies on the previous mapping schema to properly map this data to the table.</span></span> <span data-ttu-id="86284-122">Observe que o updategram usa o mesmo nome de elemento, **\<Customer>** , conforme definido no esquema.</span><span class="sxs-lookup"><span data-stu-id="86284-122">Notice that the updategram uses the same element name, **\<Customer>**, as defined in the schema.</span></span> <span data-ttu-id="86284-123">Isso é obrigatório porque o diagrama especifica um esquema específico.</span><span class="sxs-lookup"><span data-stu-id="86284-123">This is mandatory because the updategram specifies a particular schema.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="86284-124">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="86284-124">To test the updategram</span></span>  
  
1.  <span data-ttu-id="86284-125">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="86284-125">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="86284-126">Salve o arquivo como SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="86284-126">Save the file as SampleUpdateSchema.xml.</span></span>  
  
2.  <span data-ttu-id="86284-127">Copie o modelo de diagrama abaixo e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="86284-127">Copy the updategram template below and paste it into a text file.</span></span> <span data-ttu-id="86284-128">Salve o arquivo como SampleUpdategram.xml no mesmo diretório em que você salvou SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="86284-128">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
    ```  
    <ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
      <updg:sync mapping-schema="SampleUpdateSchema.xml">  
        <updg:before>  
          <Customer CustID="1" RegionID="1"  />  
        </updg:before>  
        <updg:after>  
          <Customer CustID="1" RegionID="2" />  
        </updg:after>  
      </updg:sync>  
    </ROOT>  
    ```  
  
     <span data-ttu-id="86284-129">O caminho de diretório especificado para o esquema de mapeamento (SampleUpdateSchema.xml) é relativo ao diretório onde o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="86284-129">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="86284-130">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="86284-130">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
3.  <span data-ttu-id="86284-131">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="86284-131">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="86284-132">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="86284-132">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="86284-133">Este é o esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="86284-133">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
   <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
         xmlns:dt="urn:schemas-microsoft-com:datatypes"   
         xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
     <ElementType name="Customer" sql:relation="Sales.Customer" >  
       <AttributeType name="CustID" />  
       <AttributeType name="RegionID" />  
  
       <attribute type="CustID" sql:field="CustomerID" />  
       <attribute type="RegionID" sql:field="TerritoryID" />  
     </ElementType>  
   </Schema>   
```  
  
### <a name="b-inserting-a-record-by-using-the-parent-child-relationship-specified-in-the-mapping-schema"></a><span data-ttu-id="86284-134">B.</span><span class="sxs-lookup"><span data-stu-id="86284-134">B.</span></span> <span data-ttu-id="86284-135">Inserindo um registro usando a relação pai-filho especificada no esquema de mapeamento</span><span class="sxs-lookup"><span data-stu-id="86284-135">Inserting a record by using the parent-child relationship specified in the mapping schema</span></span>  
 <span data-ttu-id="86284-136">Elementos de esquema podem ser relacionados.</span><span class="sxs-lookup"><span data-stu-id="86284-136">Schema elements can be related.</span></span> <span data-ttu-id="86284-137">O **\<sql:relationship>** elemento Especifica a relação pai-filho entre os elementos do esquema.</span><span class="sxs-lookup"><span data-stu-id="86284-137">The **\<sql:relationship>** element specifies the parent-child relationship between the schema elements.</span></span> <span data-ttu-id="86284-138">Essas informações são usadas para atualizar as tabelas correspondentes que têm relação chave primária/chave estrangeira.</span><span class="sxs-lookup"><span data-stu-id="86284-138">This information is used to update corresponding tables that have primary-key/foreign-key relationship.</span></span>  
  
 <span data-ttu-id="86284-139">O seguinte esquema de mapeamento (SampleSchema.xml) consiste em dois elementos, **\<Order>** e **\<OD>** :</span><span class="sxs-lookup"><span data-stu-id="86284-139">The following mapping schema (SampleSchema.xml) consists of two elements, **\<Order>** and **\<OD>**:</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
    <sql:relationship name="OrderOD"  
          parent="Sales.SalesOrderHeader"  
          parent-key="SalesOrderID"  
          child="Sales.SalesOrderDetail"  
          child-key="SalesOrderID" />  
  </xsd:appinfo>  
</xsd:annotation>  
  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader" >  
   <xsd:complexType>  
     <xsd:sequence>  
        <xsd:element name="OD"   
                     sql:relation="Sales.SalesOrderDetail"  
                     sql:relationship="OrderOD" >  
           <xsd:complexType>  
              <xsd:attribute name="SalesOrderID"   type="xsd:integer" />  
              <xsd:attribute name="ProductID" type="xsd:integer" />  
             <xsd:attribute name="UnitPrice"  type="xsd:decimal" />  
             <xsd:attribute name="OrderQty"   type="xsd:integer" />  
             <xsd:attribute name="UnitPriceDiscount"   type="xsd:decimal" />  
  
           </xsd:complexType>  
        </xsd:element>  
     </xsd:sequence>  
        <xsd:attribute name="CustomerID"   type="xsd:string" />   
        <xsd:attribute name="SalesOrderID"  type="xsd:integer" />  
        <xsd:attribute name="OrderDate"  type="xsd:date" />  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="86284-140">O updategram a seguir usa esse esquema XSD para adicionar um novo registro de detalhes do pedido (um **\<OD>** elemento no **\<after>** bloco) para a ordem 43860.</span><span class="sxs-lookup"><span data-stu-id="86284-140">The following updategram uses this XSD schema to add a new order detail record (an **\<OD>** element in the **\<after>** block) for order 43860.</span></span> <span data-ttu-id="86284-141">O atributo `mapping-schema` é usado para especificar o esquema de mapeamento no diagrama.</span><span class="sxs-lookup"><span data-stu-id="86284-141">The `mapping-schema` attribute is used to specify the mapping schema in the updategram.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="SampleUpdateSchema.xml" >  
    <updg:before>  
       <Order SalesOrderID="43860" />  
    </updg:before>  
    <updg:after>  
      <Order SalesOrderID="43860" >  
           <OD ProductID="753" UnitPrice="$10.00"  
               Quantity="5" Discount="0.0" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="86284-142">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="86284-142">To test the updategram</span></span>  
  
1.  <span data-ttu-id="86284-143">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="86284-143">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="86284-144">Salve o arquivo como SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="86284-144">Save the file as SampleUpdateSchema.xml.</span></span>  
  
2.  <span data-ttu-id="86284-145">Copie o modelo de diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="86284-145">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="86284-146">Salve o arquivo como SampleUpdategram.xml no mesmo diretório em que você salvou SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="86284-146">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
     <span data-ttu-id="86284-147">O caminho de diretório especificado para o esquema de mapeamento (SampleUpdateSchema.xml) é relativo ao diretório onde o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="86284-147">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="86284-148">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="86284-148">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
3.  <span data-ttu-id="86284-149">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="86284-149">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="86284-150">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="86284-150">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="86284-151">Este é o esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="86284-151">This is the equivalent XDR schema:</span></span>  
  
```  
<?xml version="1.0" ?>  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:dt="urn:schemas-microsoft-com:datatypes"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
  
<ElementType name="OD" sql:relation="Sales.SalesOrderDetail" >  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="ProductID" />  
    <AttributeType name="UnitPrice"  dt:type="fixed.14.4" />  
    <AttributeType name="OrderQty" />  
    <AttributeType name="UnitPriceDiscount" />  
  
    <attribute type="SalesOrderID" />  
    <attribute type="ProductID" />  
    <attribute type="UnitPrice" />  
    <attribute type="OrderQty" />  
    <attribute type="UnitPriceDiscount" />  
</ElementType>  
  
<ElementType name="Order" sql:relation="Sales.SalesOrderHeader" >  
    <AttributeType name="CustomerID" />  
    <AttributeType name="SalesOrderID" />  
    <AttributeType name="OrderDate" />  
  
    <attribute type="CustomerID" />  
    <attribute type="SalesOrderID" />  
    <attribute type="OrderDate" />  
    <element type="OD" >  
             <sql:relationship   
                   key-relation="Sales.SalesOrderHeader"  
                   key="SalesOrderID"  
                   foreign-key="SalesOrderID"  
                   foreign-relation="Sales.SalesOrderDetail" />  
    </element>  
</ElementType>  
</Schema>  
```  
  
### <a name="c-inserting-a-record-by-using-the-parent-child-relationship-and-inverse-annotation-specified-in-the-xsd-schema"></a><span data-ttu-id="86284-152">C.</span><span class="sxs-lookup"><span data-stu-id="86284-152">C.</span></span> <span data-ttu-id="86284-153">Inserindo um registro usando a relação pai-filho e a anotação de inverso especificada no esquema XSD</span><span class="sxs-lookup"><span data-stu-id="86284-153">Inserting a record by using the parent-child relationship and inverse annotation specified in the XSD schema</span></span>  
 <span data-ttu-id="86284-154">Este exemplo ilustra como a lógica de diagrama de atualização usa a relação pai-filho especificada no XSD para processar atualizações e como a anotação `inverse` é usada.</span><span class="sxs-lookup"><span data-stu-id="86284-154">This example illustrates how the updategram logic uses the parent-child relationship specified in the XSD to process updates, and how the `inverse` annotation is used.</span></span> <span data-ttu-id="86284-155">Para obter mais informações sobre a `inverse` anotação, consulte [especificando o atributo SQL: inverso em SQL: relationship &#40;SQLXML 4,0&#41;](../../sqlxml-annotated-xsd-schemas-using/specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="86284-155">For more information about the `inverse` annotation, see [Specifying the sql:inverse Attribute on sql:relationship &#40;SQLXML 4.0&#41;](../../sqlxml-annotated-xsd-schemas-using/specifying-the-sql-inverse-attribute-on-sql-relationship-sqlxml-4-0.md).</span></span>  
  
 <span data-ttu-id="86284-156">Este exemplo pressupõe que as tabelas a seguir estão no banco de dados **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="86284-156">This example assumes that the following tables are in the **tempdb** database:</span></span>  
  
-   <span data-ttu-id="86284-157">`Cust (CustomerID, CompanyName)`, onde `CustomerID` é a chave primária</span><span class="sxs-lookup"><span data-stu-id="86284-157">`Cust (CustomerID, CompanyName)`, where `CustomerID` is the primary key</span></span>  
  
-   <span data-ttu-id="86284-158">`Ord (OrderID, CustomerID)`, onde `CustomerID` é uma chave estrangeira que recorre à chave primária `CustomerID` na tabela `Cust`.</span><span class="sxs-lookup"><span data-stu-id="86284-158">`Ord (OrderID, CustomerID)`, where `CustomerID` is a foreign key that refers to the `CustomerID` primary key in the `Cust` table.</span></span>  
  
 <span data-ttu-id="86284-159">O diagrama de atualização usa o seguinte esquema XSD para inserir registros nas tabelas Cust e Ord:</span><span class="sxs-lookup"><span data-stu-id="86284-159">The updategram uses the following XSD schema to insert records into the Cust and Ord tables :</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:annotation>  
  <xsd:appinfo>  
       <sql:relationship name="OrdCust" inverse="true"  
                  parent="Ord"  
                  parent-key="CustomerID"  
                  child-key="CustomerID"  
                  child="Cust"/>  
  </xsd:appinfo>  
</xsd:annotation>  
  
<xsd:element name="Order" sql:relation="Ord">  
  <xsd:complexType>  
    <xsd:sequence>  
      <xsd:element ref="Customer" sql:relationship="OrdCust"/>  
    </xsd:sequence>  
    <xsd:attribute name="OrderID"   type="xsd:int"/>  
    <xsd:attribute name="CustomerID" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:element>  
  
<xsd:element name="Customer" sql:relation="Cust">  
  <xsd:complexType>  
     <xsd:attribute name="CustomerID"  type="xsd:string"/>  
    <xsd:attribute name="CompanyName" type="xsd:string"/>  
  </xsd:complexType>  
</xsd:element>  
  
</xsd:schema>  
```  
  
 <span data-ttu-id="86284-160">O esquema XSD neste exemplo tem **\<Customer>** e **\<Order>** elementos e especifica uma relação pai-filho entre os dois elementos.</span><span class="sxs-lookup"><span data-stu-id="86284-160">The XSD schema in this example has **\<Customer>** and **\<Order>** elements, and it specifies a parent-child relationship between the two elements.</span></span> <span data-ttu-id="86284-161">Ele identifica **\<Order>** como o elemento pai e **\<Customer>** como o elemento filho.</span><span class="sxs-lookup"><span data-stu-id="86284-161">It identifies **\<Order>** as the parent element and **\<Customer>** as the child element.</span></span>  
  
 <span data-ttu-id="86284-162">A lógica de processamento do diagrama de atualização usa as informações sobre a relação pai-filho para determinar a ordem na qual os registros são inseridos nas tabelas.</span><span class="sxs-lookup"><span data-stu-id="86284-162">The updategram processing logic uses the information about the parent-child relationship to determine the order in which records are inserted into tables.</span></span> <span data-ttu-id="86284-163">Neste exemplo, a lógica updategram primeiro tenta inserir um registro na tabela Ord (porque **\<Order>** é o pai) e, em seguida, tenta inserir um registro na tabela Cust (porque **\<Customer>** é o filho).</span><span class="sxs-lookup"><span data-stu-id="86284-163">In this example, the updategram logic first attempts to insert a record into the Ord table (because **\<Order>** is the parent) and then attempts to insert a record into the Cust table (because **\<Customer>** is the child).</span></span> <span data-ttu-id="86284-164">No entanto, devido às informações de chave primária/chave estrangeira contidas no esquema da tabela do banco de dados, esta operação de inserção gera um erro de violação de chave estrangeira no banco de dados e a inserção não é bem sucedida.</span><span class="sxs-lookup"><span data-stu-id="86284-164">However, because of the primary key/foreign key information that is contained in the database table schema, this insert operation causes a foreign key violation in the database and the insert fails.</span></span>  
  
 <span data-ttu-id="86284-165">Para instruir a lógica updategram a reverter a relação pai-filho durante a operação de atualização, a `inverse` anotação é especificada no **\<relationship>** elemento.</span><span class="sxs-lookup"><span data-stu-id="86284-165">To instruct the updategram logic to reverse the parent-child relationship during the update operation, the `inverse` annotation is specified on the **\<relationship>** element.</span></span> <span data-ttu-id="86284-166">Como resultado, os registros são adicionados primeiro na tabela Cust e, depois, na tabela Ord, e a operação é bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="86284-166">As a result, records are added first in the Cust table and then in the Ord table, and the operation succeeds.</span></span>  
  
 <span data-ttu-id="86284-167">O seguinte diagrama de atualização insere um pedido (OrderID=2) na tabela Ord e um cliente (CustomerID='AAAAA') na tabela Cust usando o esquema XSD especificado:</span><span class="sxs-lookup"><span data-stu-id="86284-167">The following updategram inserts an order (OrderID=2) in the Ord table and a customer (CustomerID='AAAAA') in the Cust table by using the specified XSD schema:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema="SampleUpdateSchema.xml" >  
    <updg:before/>  
    <updg:after>  
      <Order OrderID="2" CustomerID="AAAAA" >  
        <Customer CustomerID="AAAAA" CompanyName="AAAAA Company" />  
      </Order>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="86284-168">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="86284-168">To test the updategram</span></span>  
  
1.  <span data-ttu-id="86284-169">Crie essas tabelas no banco de dados **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="86284-169">Create these tables in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Cust(CustomerID varchar(5) primary key,   
                      CompanyName varchar(20))  
    GO  
    CREATE TABLE Ord (OrderID int primary key,   
                      CustomerID varchar(5) references Cust(CustomerID))  
    GO  
    ```  
  
2.  <span data-ttu-id="86284-170">Copie o código de esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="86284-170">Copy the schema code above and paste it into a text file.</span></span> <span data-ttu-id="86284-171">Salve o arquivo como SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="86284-171">Save the file as SampleUpdateSchema.xml.</span></span>  
  
3.  <span data-ttu-id="86284-172">Copie o modelo de diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="86284-172">Copy the updategram template above and paste it into a text file.</span></span> <span data-ttu-id="86284-173">Salve o arquivo como SampleUpdategram.xml no mesmo diretório em que você salvou SampleUpdateSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="86284-173">Save the file as SampleUpdategram.xml in the same directory where you saved SampleUpdateSchema.xml.</span></span>  
  
     <span data-ttu-id="86284-174">O caminho de diretório especificado para o esquema de mapeamento (SampleUpdateSchema.xml) é relativo ao diretório onde o modelo foi salvo.</span><span class="sxs-lookup"><span data-stu-id="86284-174">The directory path specified for the mapping schema (SampleUpdateSchema.xml) is relative to the directory where the template is saved.</span></span> <span data-ttu-id="86284-175">Também é possível especificar um caminho absoluto, por exemplo:</span><span class="sxs-lookup"><span data-stu-id="86284-175">An absolute path also can be specified, for example:</span></span>  
  
    ```  
    mapping-schema="C:\SqlXmlTest\SampleUpdateSchema.xml"  
    ```  
  
4.  <span data-ttu-id="86284-176">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="86284-176">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="86284-177">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="86284-177">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="86284-178">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="86284-178">See Also</span></span>  
 [<span data-ttu-id="86284-179">Considerações de segurança do updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="86284-179">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
