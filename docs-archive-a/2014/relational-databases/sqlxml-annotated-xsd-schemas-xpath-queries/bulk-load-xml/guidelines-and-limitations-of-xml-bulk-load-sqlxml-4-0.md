---
title: Diretrizes e limitações do carregamento em massa de XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- XML Bulk Load [SQLXML], about XML Bulk Load
- bulk load [SQLXML], about bulk load
ms.assetid: c5885d14-c7c1-47b3-a389-455e99a7ece1
author: rothja
ms.author: jroth
ms.openlocfilehash: 08c0020ac7b28702f5a573c6158ec9d50c735b2a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575756"
---
# <a name="guidelines-and-limitations-of-xml-bulk-load-sqlxml-40"></a><span data-ttu-id="58358-102">Diretrizes e limitações de Carregamento em Massa de XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="58358-102">Guidelines and Limitations of XML Bulk Load (SQLXML 4.0)</span></span>
  <span data-ttu-id="58358-103">Ao usar o Carregamento em Massa de XML, você deve estar familiarizado com as diretrizes e limitações a seguir:</span><span class="sxs-lookup"><span data-stu-id="58358-103">When you use XML Bulk Load, you should be familiar with the following guidelines and limitations:</span></span>  
  
-   <span data-ttu-id="58358-104">Não há suporte a esquemas embutidos.</span><span class="sxs-lookup"><span data-stu-id="58358-104">Inline schemas are not supported.</span></span>  
  
     <span data-ttu-id="58358-105">Se houver um esquema embutido no documento XML de origem, o Carregamento em Massa de XML ignorará esse esquema.</span><span class="sxs-lookup"><span data-stu-id="58358-105">If you have an inline schema in the source XML document, XML Bulk Load ignores that schema.</span></span> <span data-ttu-id="58358-106">Você especifica o esquema de mapeamento para o Carregamento em Massa de XML que é externo aos dados XML.</span><span class="sxs-lookup"><span data-stu-id="58358-106">You specify the mapping schema for XML Bulk Load external to the XML data.</span></span> <span data-ttu-id="58358-107">Você não pode especificar o esquema de mapeamento em um nó usando o atributo **xmlns = "x:Schema"** .</span><span class="sxs-lookup"><span data-stu-id="58358-107">You cannot specify the mapping schema at a node by using the **xmlns="x:schema"** attribute.</span></span>  
  
-   <span data-ttu-id="58358-108">Um documento XML é verificado para que esteja bem formado, mas ele não é validado.</span><span class="sxs-lookup"><span data-stu-id="58358-108">An XML document is checked for being well-formed, but it is not validated.</span></span>  
  
     <span data-ttu-id="58358-109">O carregamento em massa de XML verifica o documento XML para determinar se ele está bem formado, ou seja, para garantir que o XML esteja em conformidade com os requisitos de sintaxe da recomendação XML 1,0 do World Wide Web Consortium.</span><span class="sxs-lookup"><span data-stu-id="58358-109">XML Bulk Load checks the XML document to determine whether it is well-formed-that is, to ensure that the XML conforms to the syntax requirements of the World Wide Web Consortium's XML 1.0 recommendation.</span></span> <span data-ttu-id="58358-110">Se o documento não estiver bem formado, o Carregamento em Massa de XML cancelará o processamento e retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="58358-110">If the document is not well-formed, XML Bulk Load cancels processing and returns an error.</span></span> <span data-ttu-id="58358-111">A única exceção é quando o documento é um fragmento (por exemplo, o documento não tem nenhum elemento raiz), caso em que o Carregamento em Massa de XML carregará o documento.</span><span class="sxs-lookup"><span data-stu-id="58358-111">The only exception to this is when the document is a fragment (for example, the document has no single root element), in which case XML Bulk Load will load the document.</span></span>  
  
     <span data-ttu-id="58358-112">O Carregamento em Massa de XML não valida o documento com relação a qualquer esquema DTD ou de Dados XML definido ou referenciado no arquivo de dados XML.</span><span class="sxs-lookup"><span data-stu-id="58358-112">XML Bulk Load does not validate the document with respect to any XML-Data or DTD schema that is defined or referenced within the XML data file.</span></span> <span data-ttu-id="58358-113">Além disso, o Carregamento em Massa de XML não valida o arquivo de dados XML com base no esquema de mapeamento fornecido.</span><span class="sxs-lookup"><span data-stu-id="58358-113">In addition, XML Bulk Load does not validate the XML data file against the mapping schema supplied.</span></span>  
  
-   <span data-ttu-id="58358-114">Quaisquer informações de prólogo XML são ignoradas.</span><span class="sxs-lookup"><span data-stu-id="58358-114">Any XML prolog information is ignored.</span></span>  
  
     <span data-ttu-id="58358-115">O carregamento em massa de XML ignora todas as informações antes e depois do \<root> elemento no documento XML.</span><span class="sxs-lookup"><span data-stu-id="58358-115">XML Bulk Load ignores all the information before and after the \<root> element in the XML document.</span></span> <span data-ttu-id="58358-116">Por exemplo, o Carregamento em Massa de XML ignora qualquer declaração XML, definições de DTD internas, referências de DTD externas, comentários e assim por diante.</span><span class="sxs-lookup"><span data-stu-id="58358-116">For example, XML Bulk Load ignores any XML declarations, internal DTD definitions, external DTD references, comments, and so on.</span></span>  
  
-   <span data-ttu-id="58358-117">Se você tiver um esquema de mapeamento que define um relacionamento de chave primária/chave estrangeira entre duas tabelas (como entre Customer e CustOrder), a tabela com a chave primária deverá ser descrita primeiro no esquema.</span><span class="sxs-lookup"><span data-stu-id="58358-117">If you have a mapping schema that defines a primary key/foreign key relationship between two tables (such as between Customer and CustOrder), the table with the primary key must be described first in the schema.</span></span> <span data-ttu-id="58358-118">A tabela com a coluna de chave estrangeira deve aparecer depois no esquema.</span><span class="sxs-lookup"><span data-stu-id="58358-118">The table with the foreign key column must appear later in the schema.</span></span> <span data-ttu-id="58358-119">O motivo disso é que a ordem na qual as tabelas são identificadas no esquema é a ordem usada para carregá-las no banco de dados. Por exemplo, o esquema XDR a seguir produzirá um erro quando ele for usado no carregamento em massa de XML, pois o **\<Order>** elemento é descrito antes do **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="58358-119">The reason for this is that the order in which the tables are identified in the schema is the order that is used to load them into the database.For example, the following XDR schema will produce an error when it is used in XML Bulk Load because the **\<Order>** element is described before the **\<Customer>** element.</span></span> <span data-ttu-id="58358-120">A coluna CustomerID em CustOrder é uma coluna de chave estrangeira que se refere à coluna de chave primária CustomerID na tabela Cust.</span><span class="sxs-lookup"><span data-stu-id="58358-120">The CustomerID column in CustOrder is a foreign key column that refers to the CustomerID primary key column in the Cust table.</span></span>  
  
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
  
-   <span data-ttu-id="58358-121">Se o esquema não especificar colunas de estouro usando a anotação `sql:overflow-field`, o Carregamento em Massa de XML ignorará todos os dados presentes no documento XML porém não descritos no esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="58358-121">If the schema does not specify overflow columns by using the `sql:overflow-field` annotation, XML Bulk Load ignores any data that is present in the XML document but is not described in the mapping schema.</span></span>  
  
     <span data-ttu-id="58358-122">O Carregamento em Massa de XML aplica o esquema de mapeamento que você especifica sempre que encontra marcas conhecidas no fluxo de dados XML.</span><span class="sxs-lookup"><span data-stu-id="58358-122">XML Bulk Load applies the mapping schema that you have specified whenever it encounters known tags in the XML data stream.</span></span> <span data-ttu-id="58358-123">Ele ignora dados presentes no documento XML mas não descritos no esquema.</span><span class="sxs-lookup"><span data-stu-id="58358-123">It ignores data that is present in the XML document but is not described in the schema.</span></span> <span data-ttu-id="58358-124">Por exemplo, suponha que você tenha um esquema de mapeamento que descreve um **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="58358-124">For example, assume you have a mapping schema that describes a **\<Customer>** element.</span></span> <span data-ttu-id="58358-125">O arquivo de dados XML tem uma **\<AllCustomers>** marca de raiz (que não está descrita no esquema) que inclui todos os **\<Customer>** elementos:</span><span class="sxs-lookup"><span data-stu-id="58358-125">The XML data file has an **\<AllCustomers>** root tag (which is not described in the schema) that encloses all the **\<Customer>** elements:</span></span>  
  
    ```  
    <AllCustomers>  
      <Customer>...</Customer>  
      <Customer>...</Customer>  
       ...  
    </AllCustomers>  
    ```  
  
     <span data-ttu-id="58358-126">Nesse caso, o carregamento em massa de XML ignora o **\<AllCustomers>** elemento e começa o mapeamento no **\<Customer>** elemento.</span><span class="sxs-lookup"><span data-stu-id="58358-126">In this case, XML Bulk Load ignores the **\<AllCustomers>** element and begins mapping at the **\<Customer>** element.</span></span> <span data-ttu-id="58358-127">O Carregamento em Massa de XML ignora os elementos não descritos no esquema mas presentes no documento XML.</span><span class="sxs-lookup"><span data-stu-id="58358-127">XML Bulk Load ignores the elements that are not described in the schema but are present in the XML document.</span></span>  
  
     <span data-ttu-id="58358-128">Considere outro arquivo de dados de origem XML que contenha **\<Order>** elementos.</span><span class="sxs-lookup"><span data-stu-id="58358-128">Consider another XML source data file that contains **\<Order>** elements.</span></span> <span data-ttu-id="58358-129">Esses elementos não são descritos no esquema de mapeamento:</span><span class="sxs-lookup"><span data-stu-id="58358-129">These elements are not described in the mapping schema:</span></span>  
  
    ```  
    <AllCustomers>  
      <Customer>...</Customer>  
        <Order> ... </Order>  
        <Order> ... </Order>  
         ...  
      <Customer>...</Customer>  
        <Order> ... </Order>  
        <Order> ... </Order>  
         ...  
      ...  
    </AllCustomers>  
    ```  
  
     <span data-ttu-id="58358-130">O carregamento em massa de XML ignora esses **\<Order>** elementos.</span><span class="sxs-lookup"><span data-stu-id="58358-130">XML Bulk Load ignores these **\<Order>** elements.</span></span> <span data-ttu-id="58358-131">Mas se você usar a `sql:overflow-field` anotação no esquema para identificar uma coluna como uma coluna de estouro, a carga em massa de XML armazenará todos os dados não consumidos nesta coluna.</span><span class="sxs-lookup"><span data-stu-id="58358-131">But if you use the `sql:overflow-field`annotation in the schema to identify a column as an overflow column, XML Bulk Load stores all unconsumed data in this column.</span></span>  
  
-   <span data-ttu-id="58358-132">As referências de entidade e seções CDATA são traduzidas para os respectivos equivalentes de cadeia de caracteres antes de serem armazenadas no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="58358-132">CDATA sections and entity references are translated to their string equivalents before they are stored in the database.</span></span>  
  
     <span data-ttu-id="58358-133">Neste exemplo, uma seção CDATA encapsula o valor do **\<City>** elemento.</span><span class="sxs-lookup"><span data-stu-id="58358-133">In this example, a CDATA section wraps the value for the **\<City>** element.</span></span> <span data-ttu-id="58358-134">O carregamento em massa de XML extrai o valor da cadeia de caracteres ("NY") antes de inserir o **\<City>** elemento no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="58358-134">XML Bulk Load extracts the string value ("NY") before it inserts the **\<City>** element into the database.</span></span>  
  
    ```  
    <City><![CDATA[NY]]> </City>  
    ```  
  
     <span data-ttu-id="58358-135">O Carregamento em Massa de XML não preserva as referências de entidade.</span><span class="sxs-lookup"><span data-stu-id="58358-135">XML Bulk Load does not preserve entity references.</span></span>  
  
-   <span data-ttu-id="58358-136">Se o esquema de mapeamento especificar o valor padrão de um atributo e os dados de origem XML não contiverem esse atributo, o Carregamento em Massa de XML usará o valor padrão.</span><span class="sxs-lookup"><span data-stu-id="58358-136">If the mapping schema specifies the default value for an attribute and the XML source data does not contain that attribute, XML Bulk Load uses the default value.</span></span>  
  
     <span data-ttu-id="58358-137">O seguinte esquema XDR de exemplo atribui um valor padrão ao atributo **HireDate** :</span><span class="sxs-lookup"><span data-stu-id="58358-137">The following sample XDR schema assigns a default value to the **HireDate** attribute:</span></span>  
  
    ```  
    <?xml version="1.0" ?>  
    <Schema xmlns="urn:schemas-microsoft-com:xml-data"   
            xmlns:dt="urn:schemas-microsoft-com:xml:datatypes"    
            xmlns:sql="urn:schemas-microsoft-com:xml-sql" >  
       <ElementType name="root" sql:is-constant="1">  
          <element type="Customers" />  
       </ElementType>  
  
       <ElementType name="Customers" sql:relation="Cust3" >  
          <AttributeType name="CustomerID" dt:type="int"  />  
          <AttributeType name="HireDate"  default="2000-01-01" />  
          <AttributeType name="Salary"   />  
  
          <attribute type="CustomerID" sql:field="CustomerID" />  
          <attribute type="HireDate"   sql:field="HireDate"  />  
          <attribute type="Salary"     sql:field="Salary"    />  
       </ElementType>  
    </Schema>  
    ```  
  
     <span data-ttu-id="58358-138">Nesses dados XML, o atributo **HireDate** está faltando no segundo **\<Customers>** elemento.</span><span class="sxs-lookup"><span data-stu-id="58358-138">In this XML data, the **HireDate** attribute is missing from the second **\<Customers>** element.</span></span> <span data-ttu-id="58358-139">Quando o carregamento em massa de XML insere o segundo **\<Customers>** elemento no banco de dados, ele usa o valor padrão especificado no esquema.</span><span class="sxs-lookup"><span data-stu-id="58358-139">When XML Bulk Load inserts the second **\<Customers>** element into the database, it uses the default value that is specified in the schema.</span></span>  
  
    ```  
    <ROOT>  
      <Customers CustomerID="1" HireDate="1999-01-01" Salary="10000" />  
      <Customers CustomerID="2" Salary="10000" />  
    </ROOT>  
    ```  
  
-   <span data-ttu-id="58358-140">Não há suporte à anotação `sql:url-encode`:</span><span class="sxs-lookup"><span data-stu-id="58358-140">The `sql:url-encode` annotation is not supported:</span></span>  
  
     <span data-ttu-id="58358-141">Você não pode especificar uma URL na entrada de dados XML e esperar que o Carregamento em Massa leia os dados desse local.</span><span class="sxs-lookup"><span data-stu-id="58358-141">You cannot specify a URL in the XML data input and expect Bulk Load to read data from that location.</span></span>  
  
     <span data-ttu-id="58358-142">São criadas as tabelas identificadas no esquema de mapeamento (o banco de dados precisa existir).</span><span class="sxs-lookup"><span data-stu-id="58358-142">The tables that are identified in the mapping schema are created (the database must exist).</span></span> <span data-ttu-id="58358-143">Se uma ou mais das tabelas já existir no banco de dados, a propriedade SGDropTables determinará se essas tabelas preexistentes devem ser descartadas e recriadas.</span><span class="sxs-lookup"><span data-stu-id="58358-143">If one or more of the tables already exists in the database, the SGDropTables property determines whether these preexisting tables are to be dropped and re-created.</span></span>  
  
-   <span data-ttu-id="58358-144">Se você especificar a propriedade SchemaGen (por exemplo, SchemaGen = true), as tabelas identificadas no esquema de mapeamento serão criadas.</span><span class="sxs-lookup"><span data-stu-id="58358-144">If you specify the SchemaGen property (for example, SchemaGen = true), the tables that are identified in the mapping schema are created.</span></span> <span data-ttu-id="58358-145">Mas o SchemaGen não cria nenhuma restrição (como as restrições PRIMARY KEY/FOREIGN KEY) nessas tabelas com uma exceção: se os nós XML que constituem a chave primária em uma relação forem definidos como tendo um tipo XML de ID (ou seja, `type="xsd:ID"` para xsd) e a propriedade SGUseID estiver definida como true para SchemaGen, não somente as chaves primárias serão criadas a partir dos nós de tipo de ID, mas as relações de chave primária/chave estrangeira serão criadas a partir do mapeamento de relações de esquema.</span><span class="sxs-lookup"><span data-stu-id="58358-145">But SchemaGen does not create any constraints (such as the PRIMARY KEY/FOREIGN KEY constraints) on these tables with one exception: If the XML nodes that constitute the primary key in a relationship are defined as having an XML type of ID (that is, `type="xsd:ID"` for XSD) AND the SGUseID property is set to True for SchemaGen, then not only are primary keys created from the ID typed nodes, but primary key/foreign key relationships are created from mapping schema relationships.</span></span>  
  
-   <span data-ttu-id="58358-146">SchemaGen não usa facetas e extensões de esquema XSD para gerar o esquema relacional [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="58358-146">SchemaGen does not use XSD schema facets and extensions to generate the relational [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] schema.</span></span>  
  
-   <span data-ttu-id="58358-147">Se você especificar a propriedade SchemaGen (por exemplo, SchemaGen = true) no carregamento em massa, somente as tabelas (e não as exibições do nome compartilhado) especificadas serão atualizadas.</span><span class="sxs-lookup"><span data-stu-id="58358-147">If you specify the SchemaGen property (for example, SchemaGen = true) on Bulk Load, only tables (and not views of shared name) that are specified are updated.</span></span>  
  
-   <span data-ttu-id="58358-148">O SchemaGen fornece apenas a funcionalidade básica para gerar o esquema relacional do XSD anotado.</span><span class="sxs-lookup"><span data-stu-id="58358-148">SchemaGen only provides basic functionality for generating the relational schema from annotated XSD.</span></span> <span data-ttu-id="58358-149">O usuário deve modificar as tabelas geradas manualmente, se necessário.</span><span class="sxs-lookup"><span data-stu-id="58358-149">The user should modify the generated tables manually, if needed.</span></span>  
  
-   <span data-ttu-id="58358-150">Quando houver mais de uma relação entre as tabelas, SchemaGen tentará criar uma única relação que inclui todas as chaves envolvidas entre as duas tabelas.</span><span class="sxs-lookup"><span data-stu-id="58358-150">Where more than relationship exists between tables,SchemaGen tries to create a single relationship that includes all the keys involved between the two tables.</span></span> <span data-ttu-id="58358-151">Essa limitação pode causar um erro [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="58358-151">This limitation might be the cause of a [!INCLUDE[tsql](../../../includes/tsql-md.md)] error.</span></span>  
  
-   <span data-ttu-id="58358-152">Quando você está carregando em massa os dados XML em um banco de dados, é necessário haver pelo menos um atributo ou elemento filho no esquema de mapeamento que esteja mapeado para uma coluna de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="58358-152">When you are bulk loading XML data into a database, there must be at least one attribute or child element in the mapping schema that is mapped to a database column.</span></span>  
  
-   <span data-ttu-id="58358-153">Se você estiver inserindo valores de data usando o XML Bulk Load, eles deverão ser especificados no formato (-)CCYY-MM-DD((+-)TZ).</span><span class="sxs-lookup"><span data-stu-id="58358-153">If you are inserting date values by using XML Bulk Load, the values must be specified in the (-)CCYY-MM-DD((+-)TZ) format.</span></span> <span data-ttu-id="58358-154">Esse é o formato de XSD padrão para a data.</span><span class="sxs-lookup"><span data-stu-id="58358-154">This is the standard XSD format for the date.</span></span>  
  
-   <span data-ttu-id="58358-155">Alguns sinalizadores de propriedade não são compatíveis com outros.</span><span class="sxs-lookup"><span data-stu-id="58358-155">Some property flags are not compatible with other property flags.</span></span> <span data-ttu-id="58358-156">Por exemplo, o carregamento em massa não aceita `Ignoreduplicatekeys=true` junto com `Keepidentity=false`.</span><span class="sxs-lookup"><span data-stu-id="58358-156">For example, bulk load does not support `Ignoreduplicatekeys=true` together with `Keepidentity=false`.</span></span> <span data-ttu-id="58358-157">Quando `Keepidentity=false`, o carregamento em massa espera o servidor gerar os valores de chave.</span><span class="sxs-lookup"><span data-stu-id="58358-157">When `Keepidentity=false`, bulk load expects the server to generate the key values.</span></span> <span data-ttu-id="58358-158">As tabelas devem ter uma restrição `IDENTITY` na chave.</span><span class="sxs-lookup"><span data-stu-id="58358-158">Tables should have an `IDENTITY` constraint on the key.</span></span> <span data-ttu-id="58358-159">O servidor não gerará chaves duplicadas, o que significa que não há necessidade de `Ignoreduplicatekeys` ser definido como `true`.</span><span class="sxs-lookup"><span data-stu-id="58358-159">The server will not generate duplicate keys, which means there is no need for `Ignoreduplicatekeys` to be set to `true`.</span></span> <span data-ttu-id="58358-160">`Ignoreduplicatekeys` deve ser definido como `true` somente ao enviar valores de chave primária dos dados de entrada para uma tabela que tem linhas e se houver um possível conflito dos valores de chave primária.</span><span class="sxs-lookup"><span data-stu-id="58358-160">`Ignoreduplicatekeys` should be set to `true` only when uploading primary key values from the incoming data into a table that has rows and there is a potential for conflict of primary key values.</span></span>  
  
  
