---
title: Inserindo dados usando Updategrams XML (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- xsi:nil attribute
- unique values
- <after> block
- id attribute
- data insertions [SQLXML]
- nil attribute
- <before> block
- updg:guid attribute
- multiple record insertions
- returnid attribute
- updategrams [SQLXML], inserting data
- updg:at-identity attribute
- invalid characters [SQLXML]
- updg:returnid attribute
- updg:id attribute
- namespaces [SQLXML], updategrams
- IDENTITY-type column
- guid attribute
- record insertion [SQLXML]
- null values [SQLXML]
- at-identity attribute
- xml data type [SQL Server], SQLXML
ms.assetid: 4dc48762-bc12-43fb-b356-ea1b9c1e287e
author: rothja
ms.author: jroth
ms.openlocfilehash: a80f2cb157e59f30ebcbff5c14abba1003de9e40
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680840"
---
# <a name="inserting-data-using-xml-updategrams-sqlxml-40"></a><span data-ttu-id="e23a2-102">Inserindo dados usando diagramas de atualização XML (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="e23a2-102">Inserting Data Using XML Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="e23a2-103">Um updategram indica uma operação de inserção quando uma instância de registro é exibida no **\<after>** bloco, mas não no **\<before>** bloco correspondente.</span><span class="sxs-lookup"><span data-stu-id="e23a2-103">An updategram indicates an insert operation when a record instance appears in the **\<after>** block but not in the corresponding **\<before>** block.</span></span> <span data-ttu-id="e23a2-104">Nesse caso, o updategram insere o registro no bloco no **\<after>** banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e23a2-104">In this case, the updategram inserts the record in the **\<after>** block into the database.</span></span>  
  
 <span data-ttu-id="e23a2-105">Este é o formato do diagrama de atualização em uma operação de inserção:</span><span class="sxs-lookup"><span data-stu-id="e23a2-105">This is the updategram format for an insert operation:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema="SampleSchema.xml"]  >  
   [<updg:before>  
   </updg:before>]  
    <updg:after [updg:returnid="x y ...] >  
       <ElementName [updg:id="value"]   
                   [updg:at-identity="x"]   
                   [updg:guid="y"]  
                   attribute="value"   
                   attribute="value"  
                   ...  
       />  
      [<ElementName .../>... ]  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
## <a name="before-block"></a><span data-ttu-id="e23a2-106">\<before>Impeça</span><span class="sxs-lookup"><span data-stu-id="e23a2-106">\<before> Block</span></span>  
 <span data-ttu-id="e23a2-107">O **\<before>** bloco pode ser omitido para uma operação de inserção.</span><span class="sxs-lookup"><span data-stu-id="e23a2-107">The **\<before>** block can be omitted for an insert operation.</span></span> <span data-ttu-id="e23a2-108">Se o `mapping-schema` atributo opcional não for especificado, o **\<ElementName>** que é especificado no updategram é mapeado para uma tabela de banco de dados e os elementos filho ou atributos são mapeados para colunas na tabela.</span><span class="sxs-lookup"><span data-stu-id="e23a2-108">If the optional `mapping-schema` attribute is not specified, the **\<ElementName>** that is specified in the updategram maps to a database table and the child elements or attributes map to columns in the table.</span></span>  
  
## <a name="after-block"></a><span data-ttu-id="e23a2-109">\<after>Impeça</span><span class="sxs-lookup"><span data-stu-id="e23a2-109">\<after> Block</span></span>  
 <span data-ttu-id="e23a2-110">Você pode especificar um ou mais registros no **\<after>** bloco.</span><span class="sxs-lookup"><span data-stu-id="e23a2-110">You can specify one or more records in the **\<after>** block.</span></span>  
  
 <span data-ttu-id="e23a2-111">Se o **\<after>** bloco não fornecer um valor para uma determinada coluna, o updategram usará o valor padrão especificado no esquema anotado (se um esquema tiver sido especificado).</span><span class="sxs-lookup"><span data-stu-id="e23a2-111">If the **\<after>** block does not supply a value for a particular column, the updategram uses the default value that is specified in the annotated schema (if a schema has been specified).</span></span> <span data-ttu-id="e23a2-112">Se o esquema não especificar um valor padrão para a coluna, o updategram não especificará nenhum valor explícito para essa coluna e, em vez disso, atribuirá o [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] valor padrão (se especificado) a essa coluna.</span><span class="sxs-lookup"><span data-stu-id="e23a2-112">If the schema does not specify a default value for the column, the updategram does not specify any explicit value to this column and, instead, assigns the [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default value (if specified) to this column.</span></span> <span data-ttu-id="e23a2-113">Se não houver nenhum valor padrão [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] e a coluna aceitar um valor NULL, o diagrama de atualização definirá o valor da coluna como NULL.</span><span class="sxs-lookup"><span data-stu-id="e23a2-113">If there is no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] default value and the column accepts a NULL value, the updategram sets the column value to NULL.</span></span> <span data-ttu-id="e23a2-114">Caso a coluna não tenha um valor padrão nem aceite valores NULL, o comando apresentará uma falha e o diagrama de atualização retornará um erro.</span><span class="sxs-lookup"><span data-stu-id="e23a2-114">If the column neither has a default value nor accepts a NULL value, the command fails and the updategram returns an error.</span></span> <span data-ttu-id="e23a2-115">O atributo opcional `updg:returnid` é usado para retornar o valor de identidade gerado pelo sistema quando um registro é adicionado a uma tabela com uma coluna do tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="e23a2-115">The optional `updg:returnid` attribute is used to return the identity value that is generated by the system when a record is added in a table with an IDENTITY-type column.</span></span>  
  
## <a name="updgid-attribute"></a><span data-ttu-id="e23a2-116">Atributo updg:id</span><span class="sxs-lookup"><span data-stu-id="e23a2-116">updg:id Attribute</span></span>  
 <span data-ttu-id="e23a2-117">Se o diagrama de atualização só estiver inserindo registros, ele não exigirá o atributo `updg:id`.</span><span class="sxs-lookup"><span data-stu-id="e23a2-117">If the updategram is inserting only records, the updategram does not require the `updg:id` attribute.</span></span> <span data-ttu-id="e23a2-118">Para obter mais informações sobre o `updg:id` , consulte [atualizando dados usando updategrams XML &#40;SQLXML 4,0&#41;](updating-data-using-xml-updategrams-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e23a2-118">For more information about `updg:id`, see [Updating Data Using XML Updategrams &#40;SQLXML 4.0&#41;](updating-data-using-xml-updategrams-sqlxml-4-0.md).</span></span>  
  
## <a name="updgat-identity-attribute"></a><span data-ttu-id="e23a2-119">Atributo updg:at-identity</span><span class="sxs-lookup"><span data-stu-id="e23a2-119">updg:at-identity Attribute</span></span>  
 <span data-ttu-id="e23a2-120">Quando um diagrama de atualização insere um registro em uma tabela que possui uma coluna do tipo IDENTITY, o diagrama pode capturar o valor atribuído do sistema usando o atributo opcional `updg:at-identity`.</span><span class="sxs-lookup"><span data-stu-id="e23a2-120">When an updategram inserts a record in a table that has an IDENTITY-type column, the updategram can capture the system assigned value by using the optional `updg:at-identity` attribute.</span></span> <span data-ttu-id="e23a2-121">Esse valor pode ser usado em todas as operações subsequentes.</span><span class="sxs-lookup"><span data-stu-id="e23a2-121">The updategram can then use this value in subsequent operations.</span></span> <span data-ttu-id="e23a2-122">Após a execução do diagrama de atualização, você pode retornar o valor de identidade gerado pela especificação do atributo `updg:returnid`.</span><span class="sxs-lookup"><span data-stu-id="e23a2-122">Upon execution of the updategram, you can return the identity value that is generated by specifying the `updg:returnid` attribute.</span></span>  
  
## <a name="updgguid-attribute"></a><span data-ttu-id="e23a2-123">Atributo updg:guid</span><span class="sxs-lookup"><span data-stu-id="e23a2-123">updg:guid Attribute</span></span>  
 <span data-ttu-id="e23a2-124">O atributo `updg:guid` é um atributo opcional que gera um identificador globalmente exclusivo.</span><span class="sxs-lookup"><span data-stu-id="e23a2-124">The `updg:guid` attribute is an optional attribute that generates a globally unique identifier.</span></span> <span data-ttu-id="e23a2-125">Esse valor permanece no escopo para todo o **\<sync>** bloco no qual é especificado.</span><span class="sxs-lookup"><span data-stu-id="e23a2-125">This value remains in scope for the entire **\<sync>** block in which it is specified.</span></span> <span data-ttu-id="e23a2-126">Você pode usar esse valor em qualquer lugar no **\<sync>** bloco.</span><span class="sxs-lookup"><span data-stu-id="e23a2-126">You can use this value anywhere in the **\<sync>** block.</span></span> <span data-ttu-id="e23a2-127">O atributo chama a `NEWGUID()` [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] função para gerar o identificador exclusivo.</span><span class="sxs-lookup"><span data-stu-id="e23a2-127">The attribute calls the `NEWGUID()`[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] function to generate the unique identifier.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="e23a2-128">Exemplos</span><span class="sxs-lookup"><span data-stu-id="e23a2-128">Examples</span></span>  
 <span data-ttu-id="e23a2-129">Para criar exemplos de trabalho usando os exemplos a seguir, você deve atender aos requisitos especificados em [requisitos para executar exemplos do SQLXML](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span><span class="sxs-lookup"><span data-stu-id="e23a2-129">To create working samples using the following examples, you must meet the requirements specified in [Requirements for Running SQLXML Examples](../../sqlxml/requirements-for-running-sqlxml-examples.md).</span></span>  
  
 <span data-ttu-id="e23a2-130">Antes de usar os exemplos de diagrama de atualização, observe o seguinte:</span><span class="sxs-lookup"><span data-stu-id="e23a2-130">Before using the updategram examples, note the following:</span></span>  
  
-   <span data-ttu-id="e23a2-131">A maioria dos exemplos usa mapeamento padrão (ou seja, nenhum esquema de mapeamento é especificado no diagrama de atualização).</span><span class="sxs-lookup"><span data-stu-id="e23a2-131">Most of the examples use default mapping (that is, no mapping schema is specified in the updategram).</span></span> <span data-ttu-id="e23a2-132">Para obter mais exemplos de Updategrams que usam esquemas de mapeamento, consulte [especificando um esquema de mapeamento anotado em um Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e23a2-132">For more examples of updategrams that use mapping schemas, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
-   <span data-ttu-id="e23a2-133">A maioria dos exemplos usa o banco de dados de exemplo [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e23a2-133">Most of the examples use the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="e23a2-134">Todas as atualizações são aplicadas às tabelas deste banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e23a2-134">All the updates are applied to the tables in this database.</span></span>  
  
### <a name="a-inserting-a-record-by-using-an-updategram"></a><span data-ttu-id="e23a2-135">a.</span><span class="sxs-lookup"><span data-stu-id="e23a2-135">A.</span></span> <span data-ttu-id="e23a2-136">Inserindo um registro usando um diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="e23a2-136">Inserting a record by using an updategram</span></span>  
 <span data-ttu-id="e23a2-137">Este diagrama de atualização centrado em atributo insere um registro na tabela HumanResources.Employee do banco de dados [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e23a2-137">This attribute-centric updategram inserts a record in the HumanResources.Employee table in the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] database.</span></span>  
  
 <span data-ttu-id="e23a2-138">Neste exemplo, o diagrama de atualização não especifica um esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="e23a2-138">In this example, the updategram does not specify a mapping schema.</span></span> <span data-ttu-id="e23a2-139">Dessa forma, o diagrama usa o mapeamento padrão, no qual o nome do elemento é mapeado para um nome de tabela e os atributos ou elementos filho para as colunas contidas nessa tabela.</span><span class="sxs-lookup"><span data-stu-id="e23a2-139">Therefore, the updategram uses default mapping, in which the element name maps to a table name and the attributes or child elements map to columns in that table.</span></span>  
  
 <span data-ttu-id="e23a2-140">O esquema [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] para a tabela HumanResources.Department impõe uma restrição 'não nulo' em todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="e23a2-140">The [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] schema for the HumanResources.Department table imposes a 'not null' restriction on all columns.</span></span> <span data-ttu-id="e23a2-141">Portanto, o diagrama de atualização deve incluir valores especificados para todas as colunas.</span><span class="sxs-lookup"><span data-stu-id="e23a2-141">Therefore, the updategram must include values specified for all columns.</span></span> <span data-ttu-id="e23a2-142">DepartmentID é uma coluna do tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="e23a2-142">The DepartmentID is an IDENTITY-type column.</span></span> <span data-ttu-id="e23a2-143">Por isso, nenhum valor é especificado para ela.</span><span class="sxs-lookup"><span data-stu-id="e23a2-143">Therefore, no values are specified for it.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department   
            Name="New Product Research"   
            GroupName="Research and Development"   
            ModifiedDate="2010-08-31"/>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e23a2-144">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="e23a2-144">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e23a2-145">Copie o diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e23a2-145">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e23a2-146">Salve o arquivo como MyUpdategram.xml.</span><span class="sxs-lookup"><span data-stu-id="e23a2-146">Save the file as MyUpdategram.xml.</span></span>  
  
2.  <span data-ttu-id="e23a2-147">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e23a2-147">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e23a2-148">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e23a2-148">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e23a2-149">Em um mapeamento centrado em elemento, o diagrama de atualização tem esta aparência:</span><span class="sxs-lookup"><span data-stu-id="e23a2-149">In an element-centric mapping, the updategram looks like this:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department>  
            <Name> New Product Research </Name>  
            <GroupName> Research and Development </GroupName>  
            <ModifiedDate>2010-08-31</ModifiedDate>  
       </HumanResources.Department>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e23a2-150">Em um diagrama de atualização de modo misto (centrado em elemento e centrado em atributo), um elemento pode ter tanto atributos como subelementos, conforme mostrado neste diagrama:</span><span class="sxs-lookup"><span data-stu-id="e23a2-150">In a mixed-mode (element-centric and attribute-centric) updategram, an element can have both attributes and subelements, as shown in this updategram:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
       <HumanResources.Department   
            Name=" New Product Research "   
            <GroupName>Research and Development</GroupName>  
            <ModifiedDate>2010-08-31</ModifiedDate>  
       </HumanResources.Department>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
### <a name="b-inserting-multiple-records-by-using-an-updategram"></a><span data-ttu-id="e23a2-151">B.</span><span class="sxs-lookup"><span data-stu-id="e23a2-151">B.</span></span> <span data-ttu-id="e23a2-152">Inserindo vários registros usando um diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="e23a2-152">Inserting multiple records by using an updategram</span></span>  
 <span data-ttu-id="e23a2-153">Este diagrama de atualização adiciona dois novos registros de troca à tabela HumanResources.Shift.</span><span class="sxs-lookup"><span data-stu-id="e23a2-153">This updategram adds two new shift records to the HumanResources.Shift table.</span></span> <span data-ttu-id="e23a2-154">O updategram não especifica o bloco opcional **\<before>** .</span><span class="sxs-lookup"><span data-stu-id="e23a2-154">The updategram does not specify the optional **\<before>** block.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync>  
    <updg:after >  
       <HumanResources.Shift Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e23a2-155">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="e23a2-155">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e23a2-156">Copie o diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e23a2-156">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e23a2-157">Salve o arquivo como Updategram-AddShifts.xml.</span><span class="sxs-lookup"><span data-stu-id="e23a2-157">Save the file as Updategram-AddShifts.xml.</span></span>  
  
2.  <span data-ttu-id="e23a2-158">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e23a2-158">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e23a2-159">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e23a2-159">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e23a2-160">Outra versão deste exemplo é um updategram que usa dois blocos separados **\<after>** em vez de um bloco para inserir os dois funcionários.</span><span class="sxs-lookup"><span data-stu-id="e23a2-160">Another version of this example is an updategram that uses two separate **\<after>** blocks instead of one block to insert the two employees.</span></span> <span data-ttu-id="e23a2-161">Isso é válido e pode ser codificado da seguinte maneira:</span><span class="sxs-lookup"><span data-stu-id="e23a2-161">This is valid and can be encoded as follows:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync>  
    <updg:after >  
       <HumanResources.Shift Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
    <updg:before>  
    </updg:before>  
    <updg:after >  
       <HumanResources.Shift Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
### <a name="c-working-with-valid-sql-server-characters-that-are-not-valid-in-xml"></a><span data-ttu-id="e23a2-162">C.</span><span class="sxs-lookup"><span data-stu-id="e23a2-162">C.</span></span> <span data-ttu-id="e23a2-163">Trabalhando com caracteres SQL Server válidos que não são válidos no XML</span><span class="sxs-lookup"><span data-stu-id="e23a2-163">Working with valid SQL Server characters that are not valid in XML</span></span>  
 <span data-ttu-id="e23a2-164">No [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], os nomes de tabela podem incluir um espaço, como a tabela Order Details no banco de dados Northwind.</span><span class="sxs-lookup"><span data-stu-id="e23a2-164">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], table names can include a space, such as the Order Details table in the Northwind database.</span></span> <span data-ttu-id="e23a2-165">No entanto, isso não é válido em caracteres XML que são [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identificadores válidos, mas não identificadores XML válidos podem ser codificados usando ' __xHHHH \_ \_ ' como o valor de codificação, em que HHHH significa o código UCS-2 hexadecimal de quatro dígitos para o caractere na ordem mais significativa do bit-primeiro.</span><span class="sxs-lookup"><span data-stu-id="e23a2-165">However, this is not valid in XML characters that are valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identifiers but not valid XML identifiers can be encoded using '__xHHHH\_\_' as the encoding value, where HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="e23a2-166">Este exemplo usa o banco de dados Northwind.</span><span class="sxs-lookup"><span data-stu-id="e23a2-166">This example uses the Northwind database.</span></span> <span data-ttu-id="e23a2-167">Você pode instalar o banco de dados Northwind usando um script SQL disponível para download neste [site da Microsoft](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span><span class="sxs-lookup"><span data-stu-id="e23a2-167">You can install the Northwind database by using an SQL script available for download from this [Microsoft Web site](https://github.com/Microsoft/sql-server-samples/tree/master/samples/databases/northwind-pubs).</span></span>  
  
 <span data-ttu-id="e23a2-168">Além disso, o nome de elemento deve ser incluído dentro de colchetes ([]).</span><span class="sxs-lookup"><span data-stu-id="e23a2-168">Also, the element name must be enclosed within brackets ([ ]).</span></span> <span data-ttu-id="e23a2-169">Como os caracteres [e] não são válidos em XML, você deve codificá-los como _x005B \_ e _x005D \_ , respectivamente.</span><span class="sxs-lookup"><span data-stu-id="e23a2-169">Because the characters [and] are not valid in XML, you must encode them as _x005B\_ and _x005D\_, respectively.</span></span> <span data-ttu-id="e23a2-170">(Se você usar um esquema de mapeamento, poderá fornecer nomes de elemento que não contêm caracteres inválidos, como espaços em branco.</span><span class="sxs-lookup"><span data-stu-id="e23a2-170">(If you use a mapping schema, you can provide element names that do not contain characters that are not valid, such as white spaces.</span></span> <span data-ttu-id="e23a2-171">O esquema de mapeamento faz o mapeamento necessário; portanto, você não precisa codificar esses caracteres).</span><span class="sxs-lookup"><span data-stu-id="e23a2-171">The mapping schema does the necessary mapping; therefore, you do not need to encode for these characters).</span></span>  
  
 <span data-ttu-id="e23a2-172">Este diagrama de atualização adiciona um registro à tabela Order Details no banco de dados Northwind:</span><span class="sxs-lookup"><span data-stu-id="e23a2-172">This updategram adds a record to the Order Details table in the Northwind database:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after>  
      <_x005B_Order_x0020_Details_x005D_ OrderID="1"  
            ProductID="11"  
            UnitPrice="$1.0"  
            Quantity="1"  
            Discount="0.0" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e23a2-173">A coluna UnitPrice da tabela Order Details é do tipo `money`.</span><span class="sxs-lookup"><span data-stu-id="e23a2-173">The UnitPrice column in the Order Details table is of the `money` type.</span></span> <span data-ttu-id="e23a2-174">Para aplicar a conversão de tipo apropriada (de um tipo `string` em um tipo `money`), o caractere de cifrão ($) deve ser adicionado como parte do valor.</span><span class="sxs-lookup"><span data-stu-id="e23a2-174">To apply the appropriate type conversion (from a `string` type to a `money` type), the dollar sign character ($) must be added as part of the value.</span></span> <span data-ttu-id="e23a2-175">Se o diagrama de atualização não especificar um esquema de mapeamento, o primeiro caractere do valor `string` será avaliado.</span><span class="sxs-lookup"><span data-stu-id="e23a2-175">If the updategram does not specify a mapping schema, the first character of the `string` value is evaluated.</span></span> <span data-ttu-id="e23a2-176">Se o primeiro caractere for um cifrão ($), a conversão apropriada será aplicada.</span><span class="sxs-lookup"><span data-stu-id="e23a2-176">If the first character is a dollar sign ($), the appropriate conversion is applied.</span></span>  
  
 <span data-ttu-id="e23a2-177">Se o diagrama de atualização for especificado em um esquema de mapeamento em que a coluna seja marcada como `dt:type="fixed.14.4"` ou `sql:datatype="money"`, o cifrão ($) não será necessário e a conversão será feita pelo mapeamento.</span><span class="sxs-lookup"><span data-stu-id="e23a2-177">If the updategram is specified against a mapping schema where the column is appropriately marked as either `dt:type="fixed.14.4"` or `sql:datatype="money"`, the dollar sign ($) is not required and the conversion is handled by the mapping.</span></span> <span data-ttu-id="e23a2-178">Esse é o modo recomendado para garantir uma conversão de tipos bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="e23a2-178">This is the recommended way to ensure that the appropriate type conversion occurs.</span></span>  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e23a2-179">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="e23a2-179">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e23a2-180">Copie o diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e23a2-180">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e23a2-181">Salve o arquivo como UpdategramSpacesInTableName.xml.</span><span class="sxs-lookup"><span data-stu-id="e23a2-181">Save the file as UpdategramSpacesInTableName.xml.</span></span>  
  
2.  <span data-ttu-id="e23a2-182">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e23a2-182">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e23a2-183">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e23a2-183">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="d-using-the-at-identity-attribute-to-retrieve-the-value-that-has-been-inserted-in-the-identity-type-column"></a><span data-ttu-id="e23a2-184">D.</span><span class="sxs-lookup"><span data-stu-id="e23a2-184">D.</span></span> <span data-ttu-id="e23a2-185">Usando o atributo at-identity para recuperar o valor inserido na coluna do tipo IDENTITY</span><span class="sxs-lookup"><span data-stu-id="e23a2-185">Using the at-identity attribute to retrieve the value that has been inserted in the IDENTITY-type column</span></span>  
 <span data-ttu-id="e23a2-186">O diagrama de atualização a seguir insere dois registros: um na tabela Sales.SalesOrderHeader e outro na tabela Sales.SalesOrderDetail.</span><span class="sxs-lookup"><span data-stu-id="e23a2-186">The following updategram inserts two records: one in the Sales.SalesOrderHeader table and another in the Sales.SalesOrderDetail table.</span></span>  
  
 <span data-ttu-id="e23a2-187">Primeiro, o diagrama adiciona um registro à tabela Sales.SalesOrderHeader.</span><span class="sxs-lookup"><span data-stu-id="e23a2-187">First, the updategram adds a record to the Sales.SalesOrderHeader table.</span></span> <span data-ttu-id="e23a2-188">Nessa tabela, a coluna SalesOrderID é uma coluna do tipo IDENTITY.</span><span class="sxs-lookup"><span data-stu-id="e23a2-188">In this table, the SalesOrderID column is an IDENTITY-type column.</span></span> <span data-ttu-id="e23a2-189">Portanto, quando você adiciona esse registro à tabela, o diagrama de atualização usa o atributo `at-identity` para capturar o valor SalesOrderID atribuído como "x" (um valor de espaço reservado).</span><span class="sxs-lookup"><span data-stu-id="e23a2-189">Therefore, when you add this record to the table, the updategram uses the `at-identity` attribute to capture the assigned SalesOrderID value as "x" (a placeholder value).</span></span> <span data-ttu-id="e23a2-190">O updategam então especifica essa `at-identity` variável como o valor do atributo SalesOrderID no \<Sales.SalesOrderDetail> elemento.</span><span class="sxs-lookup"><span data-stu-id="e23a2-190">The updategam then specifies this `at-identity` variable as the value of SalesOrderID attribute in the \<Sales.SalesOrderDetail> element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
 <updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
   <Sales.SalesOrderHeader updg:at-identity="x"   
             RevisionNumber="1"  
             OrderDate="2001-07-01 00:00:00.000"  
             DueDate="2001-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             CustomerID="676"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="00001111-2222-3333-4444-556677889900"  
             ModifiedDate="2001-07-08 00:00:00.000" />  
      <Sales.SalesOrderDetail SalesOrderID="x"  
                LineNumber="1"  
                OrderQty="1"  
                ProductID="776"  
                SpecialOfferID="1"  
                UnitPrice="2429.9928"  
                UnitPriceDiscount="0.00"  
                rowguid="aaaaaaaa-bbbb-cccc-dddd-eeeeeeeeeeee"  
                ModifiedDate="2001-07-01 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e23a2-191">Se você quiser retornar o valor de identidade gerado pelo atributo `updg:at-identity`, poderá usar o atributo `updg:returnid`.</span><span class="sxs-lookup"><span data-stu-id="e23a2-191">If you want to return the identity value that is generated by the `updg:at-identity` attribute, you can use the `updg:returnid` attribute.</span></span> <span data-ttu-id="e23a2-192">A seguir, é mostrado um diagrama de atualização revisado que retorna esse valor de identidade.</span><span class="sxs-lookup"><span data-stu-id="e23a2-192">The following is a revised updategram that returns this identity value.</span></span> <span data-ttu-id="e23a2-193">(Esse diagrama adiciona dois registros de pedido e dois registros de detalhe de pedido, só para tornar o exemplo um pouco mais complexo.)</span><span class="sxs-lookup"><span data-stu-id="e23a2-193">(This updategram adds two order records and two order detail records, just to make the example a little more complex.)</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
 <updg:sync>  
  <updg:before>  
  </updg:before>  
  <updg:after updg:returnid="x y" >  
       <HumanResources.Shift updg:at-identity="x" Name="Day-Evening"  
                        StartTime="1900-01-01 11:00:00.000"  
                        EndTime="1900-01-01 19:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
       <HumanResources.Shift updg:at-identity="y" Name="Evening-Night"  
                        StartTime="1900-01-01 19:00:00.000"  
                        EndTime="1900-01-01 03:00:00.000"  
                        ModifiedDate="2004-01-01 00:00:00.000" />  
  </updg:after>  
 </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e23a2-194">Quando o diagrama é executado, ele retorna resultados semelhantes aos mostrados a seguir, incluindo o valor de identidade (o valor gerado da coluna ShiftID usado para a identidade da tabela) gerado:</span><span class="sxs-lookup"><span data-stu-id="e23a2-194">When the updategram is executed, it returns results similar to the following, which includes the identity value (the generated value of the ShiftID column used for table identity) that was generated:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">   
  <returnid>   
    <x>4</x>   
    <y>5</y>   
  </returnid>   
</ROOT>  
```  
  
##### <a name="to-test-a-sample-xpath-query-against-the-schema"></a><span data-ttu-id="e23a2-195">Para testar uma consulta XPath de exemplo com relação ao esquema</span><span class="sxs-lookup"><span data-stu-id="e23a2-195">To test a sample XPath query against the schema</span></span>  
  
1.  <span data-ttu-id="e23a2-196">Copie o diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e23a2-196">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e23a2-197">Salve o arquivo como Updategram-returnId.xml.</span><span class="sxs-lookup"><span data-stu-id="e23a2-197">Save the file as Updategram-returnId.xml.</span></span>  
  
2.  <span data-ttu-id="e23a2-198">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e23a2-198">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e23a2-199">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e23a2-199">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="e-using-the-updgguid-attribute-to-generate-a-unique-value"></a><span data-ttu-id="e23a2-200">E.</span><span class="sxs-lookup"><span data-stu-id="e23a2-200">E.</span></span> <span data-ttu-id="e23a2-201">Usando o atributo updg:guid para gerar um valor exclusivo</span><span class="sxs-lookup"><span data-stu-id="e23a2-201">Using the updg:guid attribute to generate a unique value</span></span>  
 <span data-ttu-id="e23a2-202">Nesse exemplo, o diagrama de atualização insere um registro nas tabelas Cust e CustOrder.</span><span class="sxs-lookup"><span data-stu-id="e23a2-202">In this example, the updategram inserts a record in the Cust and CustOrder tables.</span></span> <span data-ttu-id="e23a2-203">Além disso, o diagrama gera um valor exclusivo para o atributo CustomerID usando o atributo `updg:guid`.</span><span class="sxs-lookup"><span data-stu-id="e23a2-203">Also, the updategram generates a unique value for the CustomerID attribute by using the `updg:guid` attribute.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync >  
    <updg:before>  
    </updg:before>  
    <updg:after updg:returnid="x" >  
      <Cust updg:guid="x" >  
         <CustID>x</CustID>  
         <LastName>Fuller</LastName>  
      </Cust>  
      <CustOrder>  
         <CustID>x</CustID>  
         <OrderID>1</OrderID>  
      </CustOrder>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e23a2-204">O diagrama especifica o atributo `returnid`.</span><span class="sxs-lookup"><span data-stu-id="e23a2-204">The updategram specifies the `returnid` attribute.</span></span> <span data-ttu-id="e23a2-205">Como resultado, o GUID gerado é retornado:</span><span class="sxs-lookup"><span data-stu-id="e23a2-205">As a result, the GUID that is generated is returned:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <returnid>  
    <x>7111BD1A-7F0B-4CEE-B411-260DADFEFA2A</x>   
  </returnid>  
</ROOT>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="e23a2-206">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="e23a2-206">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e23a2-207">Copie o diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e23a2-207">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e23a2-208">Salve o arquivo como Updategram-GenerateGuid.xml.</span><span class="sxs-lookup"><span data-stu-id="e23a2-208">Save the file as Updategram-GenerateGuid.xml.</span></span>  
  
2.  <span data-ttu-id="e23a2-209">Crie estas tabelas:</span><span class="sxs-lookup"><span data-stu-id="e23a2-209">Create these tables:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Cust (CustID uniqueidentifier, LastName varchar(20))  
    CREATE TABLE CustOrder (CustID uniqueidentifier, OrderID int)  
    ```  
  
3.  <span data-ttu-id="e23a2-210">Crie e use o script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o modelo.</span><span class="sxs-lookup"><span data-stu-id="e23a2-210">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the template.</span></span>  
  
     <span data-ttu-id="e23a2-211">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e23a2-211">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="f-specifying-a-schema-in-an-updategram"></a><span data-ttu-id="e23a2-212">F.</span><span class="sxs-lookup"><span data-stu-id="e23a2-212">F.</span></span> <span data-ttu-id="e23a2-213">Especificando um esquema em um diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="e23a2-213">Specifying a schema in an updategram</span></span>  
 <span data-ttu-id="e23a2-214">O diagrama deste exemplo insere um registro na seguinte tabela:</span><span class="sxs-lookup"><span data-stu-id="e23a2-214">The updategram in this example inserts a record into the following table:</span></span>  
  
```  
CustOrder(OrderID, EmployeeID, OrderType)  
```  
  
 <span data-ttu-id="e23a2-215">Um esquema XSD é especificado nesse diagrama (ou seja, não há nenhum mapeamento padrão dos elementos e atributos).</span><span class="sxs-lookup"><span data-stu-id="e23a2-215">An XSD schema is specified in this updategram (that is, there is no default mapping of updategram elements and attributes).</span></span> <span data-ttu-id="e23a2-216">O esquema fornece o mapeamento necessário dos elementos e atributos para as tabelas e colunas do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="e23a2-216">The schema provides the necessary mapping of the elements and attributes to the database tables and columns.</span></span>  
  
 <span data-ttu-id="e23a2-217">O esquema a seguir (CustOrderSchema.xml) descreve um **\<CustOrder>** elemento que consiste nos atributos **OrderID** e **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="e23a2-217">The following schema (CustOrderSchema.xml) describes a **\<CustOrder>** element that consists of the **OrderID** and **EmployeeID** attributes.</span></span> <span data-ttu-id="e23a2-218">Para tornar o esquema mais interessante, um valor padrão é atribuído ao atributo **EmployeeID** .</span><span class="sxs-lookup"><span data-stu-id="e23a2-218">To make the schema more interesting, a default value is assigned to the **EmployeeID** attribute.</span></span> <span data-ttu-id="e23a2-219">Um diagrama usa o valor padrão de um atributo apenas em operações de inserção e, nesse caso, só se o diagrama não especificar tal atributo.</span><span class="sxs-lookup"><span data-stu-id="e23a2-219">An updategram uses an attribute's default value only for insert operations, and then only if the updategram does not specify that attribute.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
  <xsd:element name="CustOrder" >  
   <xsd:complexType>  
        <xsd:attribute name="OrderID"     type="xsd:integer" />   
        <xsd:attribute name="EmployeeID"  type="xsd:integer" />  
        <xsd:attribute name="OrderType  " type="xsd:integer" default="1"/>  
    </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="e23a2-220">Esse diagrama insere um registro na tabela CustOrder.</span><span class="sxs-lookup"><span data-stu-id="e23a2-220">This updategram inserts a record into the CustOrder table.</span></span> <span data-ttu-id="e23a2-221">O diagrama especifica apenas os valores de atributo OrderID e EmployeeID.</span><span class="sxs-lookup"><span data-stu-id="e23a2-221">The updategram specifies only the OrderID and EmployeeID attribute values.</span></span> <span data-ttu-id="e23a2-222">Ele não especifica o valor de atributo OrderType.</span><span class="sxs-lookup"><span data-stu-id="e23a2-222">It does not specify the OrderType attribute value.</span></span> <span data-ttu-id="e23a2-223">Dessa forma, o diagrama usa o valor padrão do atributo EmployeeID especificado no esquema anterior.</span><span class="sxs-lookup"><span data-stu-id="e23a2-223">Therefore, the updategram uses the default value of the EmployeeID attribute that is specified in the preceding schema.</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"  
             xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync mapping-schema='CustOrderSchema.xml'>  
<updg:after>  
       <CustOrder OrderID="98000" EmployeeID="1" />  
</updg:after>  
</updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e23a2-224">Para obter mais exemplos de Updategrams que especificam um esquema de mapeamento, consulte [especificando um esquema de mapeamento anotado em um Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="e23a2-224">For more examples of updategrams that specify a mapping schema, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="e23a2-225">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="e23a2-225">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e23a2-226">Crie esta tabela no banco de dados **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="e23a2-226">Create this table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE CustOrder(  
                     OrderID int,   
                     EmployeeID int,   
                     OrderType int)  
    ```  
  
2.  <span data-ttu-id="e23a2-227">Copie o esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e23a2-227">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="e23a2-228">Salve o arquivo como CustOrderSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="e23a2-228">Save the file as CustOrderSchema.xml.</span></span>  
  
3.  <span data-ttu-id="e23a2-229">Copie o diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e23a2-229">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e23a2-230">Salve o arquivo como CustOrderUpdategram.xml na mesma pasta usada na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="e23a2-230">Save the file as CustOrderUpdategram.xml in the same folder used in the previous step.</span></span>  
  
4.  <span data-ttu-id="e23a2-231">Crie e use o Script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="e23a2-231">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="e23a2-232">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e23a2-232">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
 <span data-ttu-id="e23a2-233">Este é o esquema XDR equivalente:</span><span class="sxs-lookup"><span data-stu-id="e23a2-233">This is the equivalent XDR schema:</span></span>  
  
```  
<Schema xmlns="urn:schemas-microsoft-com:xml-data"  
        xmlns:sql="urn:schemas-microsoft-com:xml-sql">  
 <ElementType name="CustOrder" >  
    <AttributeType name="OrderID" />  
    <AttributeType name="EmployeeID" />  
    <AttributeType name="OrderType" default="1" />  
    <attribute type="OrderID"  />  
    <attribute type="EmployeeID" />  
    <attribute type="OrderType" />  
  </ElementType>  
</Schema>  
```  
  
### <a name="g-using-the-xsinil-attribute-to-insert-null-values-in-a-column"></a><span data-ttu-id="e23a2-234">G.</span><span class="sxs-lookup"><span data-stu-id="e23a2-234">G.</span></span> <span data-ttu-id="e23a2-235">Usando o atributo xsi:nil para inserir valores nulos em uma coluna</span><span class="sxs-lookup"><span data-stu-id="e23a2-235">Using the xsi:nil attribute to insert null values in a column</span></span>  
 <span data-ttu-id="e23a2-236">Caso queira inserir um valor nulo na coluna correspondente da tabela, você pode especificar o atributo `xsi:nil` em um elemento de um diagrama.</span><span class="sxs-lookup"><span data-stu-id="e23a2-236">If you want to insert a null value in the corresponding column in the table, you can specify the `xsi:nil` attribute on an element in an updategram.</span></span> <span data-ttu-id="e23a2-237">No esquema XSD correspondente, o atributo XSD `nillable` também deve ser especificado.</span><span class="sxs-lookup"><span data-stu-id="e23a2-237">In the corresponding XSD schema, the XSD `nillable` attribute also must be specified.</span></span>  
  
 <span data-ttu-id="e23a2-238">Por exemplo, considere este esquema XSD:</span><span class="sxs-lookup"><span data-stu-id="e23a2-238">For example, consider this XSD schema:</span></span>  
  
```  
<?xml version="1.0"?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns:sql="urn:schemas-microsoft-com:mapping-schema">  
<xsd:element name="Student" sql:relation="Students">  
  <xsd:complexType>  
    <xsd:all>  
      <xsd:element name="fname" sql:field="first_name"   
                                type="xsd:string"   
                                 nillable="true"/>  
    </xsd:all>  
    <xsd:attribute name="SID"   
                        sql:field="StudentID"  
                        type="xsd:ID"/>      
    <xsd:attribute name="lname"       
                        sql:field="last_name"  
                        type="xsd:string"/>  
    <xsd:attribute name="minitial"    
                        sql:field="middle_initial"   
                        type="xsd:string"/>  
    <xsd:attribute name="years"       
                         sql:field="no_of_years"  
                         type="xsd:integer"/>  
  </xsd:complexType>  
 </xsd:element>  
</xsd:schema>  
```  
  
 <span data-ttu-id="e23a2-239">O esquema XSD especifica **anulável = "true"** para o **\<fname>** elemento.</span><span class="sxs-lookup"><span data-stu-id="e23a2-239">The XSD schema specifies **nillable="true"** for the **\<fname>** element.</span></span> <span data-ttu-id="e23a2-240">O seguinte diagrama usa esse esquema:</span><span class="sxs-lookup"><span data-stu-id="e23a2-240">The following updategram uses this schema:</span></span>  
  
```  
<ROOT xmlns:sql="urn:schemas-microsoft-com:xml-sql"  
      xmlns:updg="urn:schemas-microsoft-com:xml-updategram"  
      xmlns:xsi="http://www.w3.org/2001/XMLSchema-instance">  
  
<updg:sync mapping-schema='StudentSchema.xml'>  
  <updg:before/>  
  <updg:after>  
    <Student SID="S00004" lname="Elmaci" minitial="" years="2">  
      <fname xsi:nil="true">  
    </fname>  
    </Student>  
  </updg:after>  
</updg:sync>  
  
</ROOT>  
```  
  
 <span data-ttu-id="e23a2-241">O updategram especifica o `xsi:nil` **\<fname>** elemento no **\<after>** bloco.</span><span class="sxs-lookup"><span data-stu-id="e23a2-241">The updategram specifies `xsi:nil` for the **\<fname>** element in the **\<after>** block.</span></span> <span data-ttu-id="e23a2-242">Portanto, quando esse diagrama é executado, um valor NULL é inserido na coluna first_name da tabela.</span><span class="sxs-lookup"><span data-stu-id="e23a2-242">Therefore, when this updategram is executed, a value of NULL is inserted for the first_name column in the table.</span></span>  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="e23a2-243">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="e23a2-243">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e23a2-244">Crie a tabela a seguir no banco de dados **tempdb** :</span><span class="sxs-lookup"><span data-stu-id="e23a2-244">Create the following table in the **tempdb** database:</span></span>  
  
    ```  
    USE tempdb  
    CREATE TABLE Students (  
       StudentID char(6)NOT NULL ,  
       first_name varchar(50),  
       last_name varchar(50),  
       middle_initial char(1),  
       no_of_years int NULL)  
    GO  
    ```  
  
2.  <span data-ttu-id="e23a2-245">Copie o esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e23a2-245">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="e23a2-246">Salve o arquivo como StudentSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="e23a2-246">Save the file as StudentSchema.xml.</span></span>  
  
3.  <span data-ttu-id="e23a2-247">Copie o diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e23a2-247">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e23a2-248">Salve o arquivo como StudentUpdategram.xml na mesma pasta usada na etapa anterior para salvar StudentSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="e23a2-248">Save the file as StudentUpdategram.xml in the same folder used in previous step to save StudentSchema.xml.</span></span>  
  
4.  <span data-ttu-id="e23a2-249">Crie e use o Script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="e23a2-249">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="e23a2-250">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e23a2-250">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="h-specifying-namespaces-in-an-updategram"></a><span data-ttu-id="e23a2-251">H.</span><span class="sxs-lookup"><span data-stu-id="e23a2-251">H.</span></span> <span data-ttu-id="e23a2-252">Especificando namespaces em um diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="e23a2-252">Specifying namespaces in an updategram</span></span>  
 <span data-ttu-id="e23a2-253">Em um diagrama de atualização, você pode ter elementos que pertencem a um namespace declarado no mesmo elemento do diagrama.</span><span class="sxs-lookup"><span data-stu-id="e23a2-253">In an updategram you can have elements that belong to a namespace declared in the same element in the updategram.</span></span> <span data-ttu-id="e23a2-254">Nesse caso, o esquema correspondente deve declarar também o mesmo namespace e o elemento deve pertencer àquele namespace de destino.</span><span class="sxs-lookup"><span data-stu-id="e23a2-254">In this case, the corresponding schema must also declare the same namespace and the element must belong to that target namespace.</span></span>  
  
 <span data-ttu-id="e23a2-255">Por exemplo, no updategram a seguir (UpdateGram-ElementHavingNamespace.xml), o **\<Order>** elemento pertence a um namespace declarado no elemento.</span><span class="sxs-lookup"><span data-stu-id="e23a2-255">For example, in the following updategram (UpdateGram-ElementHavingNamespace.xml), the **\<Order>** element belongs to a namespace declared in the element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync mapping-schema='XSD-ElementHavingNameSpace.xml'>  
    <updg:after>  
       <x:Order  xmlns:x="http://server/xyz/schemas/"  
             updg:at-identity="SalesOrderID"   
             RevisionNumber="1"  
             OrderDate="2001-07-01 00:00:00.000"  
             DueDate="2001-07-13 00:00:00.000"  
             OnlineOrderFlag="0"  
             CustomerID="676"  
             ContactID="378"  
             BillToAddressID="985"  
             ShipToAddressID="985"  
             ShipMethodID="5"  
             SubTotal="24643.9362"  
             TaxAmt="1971.5149"  
             Freight="616.0984"  
             rowguid="00009999-8888-7777-6666-554433221100"  
             ModifiedDate="2001-07-08 00:00:00.000" />  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e23a2-256">Nesse caso, o esquema deve declarar também o namespace como mostrado neste esquema:</span><span class="sxs-lookup"><span data-stu-id="e23a2-256">In this case, the schema must also declare the namespace as shown in this schema:</span></span>  
  
 <span data-ttu-id="e23a2-257">O esquema a seguir (XSD-ElementHavingNamespace.xml) mostra como o elemento e os atributos correspondentes devem ser declarados.</span><span class="sxs-lookup"><span data-stu-id="e23a2-257">The following schema (XSD-ElementHavingNamespace.xml) shows how the corresponding element and attributes must be declared.</span></span>  
  
```  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
     xmlns:dt="urn:schemas-microsoft-com:datatypes"   
     xmlns:sql="urn:schemas-microsoft-com:mapping-schema"    
     xmlns:x="http://server/xyz/schemas/"   
     targetNamespace="http://server/xyz/schemas/" >  
  <xsd:element name="Order" sql:relation="Sales.SalesOrderHeader" type="x:Order_type"/>  
  <xsd:complexType name="Order_type">  
    <xsd:attribute name="SalesOrderID"  type="xsd:ID"/>  
    <xsd:attribute name="RevisionNumber" type="xsd:unsignedByte"/>  
    <xsd:attribute name="OrderDate" type="xsd:dateTime"/>  
    <xsd:attribute name="DueDate" type="xsd:dateTime"/>  
    <xsd:attribute name="ShipDate" type="xsd:dateTime"/>  
    <xsd:attribute name="Status" type="xsd:unsignedByte"/>  
    <xsd:attribute name="OnlineOrderFlag" type="xsd:boolean"/>  
    <xsd:attribute name="SalesOrderNumber" type="xsd:string"/>  
    <xsd:attribute name="PurchaseOrderNumber" type="xsd:string"/>  
    <xsd:attribute name="AccountNumber" type="xsd:string"/>  
    <xsd:attribute name="CustomerID" type="xsd:int"/>  
    <xsd:attribute name="ContactID" type="xsd:int"/>  
    <xsd:attribute name="SalesPersonID" type="xsd:int"/>  
    <xsd:attribute name="TerritoryID" type="xsd:int"/>  
    <xsd:attribute name="BillToAddressID" type="xsd:int"/>  
    <xsd:attribute name="ShipToAddressID" type="xsd:int"/>  
    <xsd:attribute name="ShipMethodID" type="xsd:int"/>  
    <xsd:attribute name="CreditCardID" type="xsd:int"/>  
    <xsd:attribute name="CreditCardApprovalCode" type="xsd:string"/>  
    <xsd:attribute name="CurrencyRateID" type="xsd:int"/>  
    <xsd:attribute name="SubTotal" type="xsd:decimal"/>  
    <xsd:attribute name="TaxAmt" type="xsd:decimal"/>  
    <xsd:attribute name="Freight" type="xsd:decimal"/>  
    <xsd:attribute name="TotalDue" type="xsd:decimal"/>  
    <xsd:attribute name="Comment" type="xsd:string"/>  
    <xsd:attribute name="rowguid" type="xsd:string"/>  
    <xsd:attribute name="ModifiedDate" type="xsd:dateTime"/>  
  </xsd:complexType>  
</xsd:schema>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="e23a2-258">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="e23a2-258">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e23a2-259">Copie o esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e23a2-259">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="e23a2-260">Salve o arquivo como XSD-ElementHavingNamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="e23a2-260">Save the file as XSD-ElementHavingNamespace.xml.</span></span>  
  
2.  <span data-ttu-id="e23a2-261">Copie o diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e23a2-261">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e23a2-262">Salve o arquivo como Updategram-ElementHavingNamespace.xml na mesma pasta usada para salvar XSD-ElementHavingnamespace.xml.</span><span class="sxs-lookup"><span data-stu-id="e23a2-262">Save the file as Updategram-ElementHavingNamespace.xml in the same folder used to save XSD-ElementHavingnamespace.xml.</span></span>  
  
3.  <span data-ttu-id="e23a2-263">Crie e use o Script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="e23a2-263">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="e23a2-264">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e23a2-264">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
### <a name="i-inserting-data-into-an-xml-data-type-column"></a><span data-ttu-id="e23a2-265">I.</span><span class="sxs-lookup"><span data-stu-id="e23a2-265">I.</span></span> <span data-ttu-id="e23a2-266">Inserindo dados em uma coluna de tipo de dados XML</span><span class="sxs-lookup"><span data-stu-id="e23a2-266">Inserting data into an XML data type column</span></span>  
 <span data-ttu-id="e23a2-267">O tipo de dados `xml` foi introduzido no [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e23a2-267">The `xml` data type was introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)].</span></span> <span data-ttu-id="e23a2-268">Você pode usar diagramas de atualização para inserir e atualizar dados armazenados em colunas de tipo de dados `xml` com as seguintes provisões:</span><span class="sxs-lookup"><span data-stu-id="e23a2-268">You can use updategrams to insert and update data stored in `xml` data type columns with the following provisions:</span></span>  
  
-   <span data-ttu-id="e23a2-269">A coluna `xml` não pode ser usada para identificar uma linha existente.</span><span class="sxs-lookup"><span data-stu-id="e23a2-269">The `xml` column cannot be used for identifying an existing row.</span></span> <span data-ttu-id="e23a2-270">Portanto, ela não pode ser incluída na seção `updg:before` de um diagrama.</span><span class="sxs-lookup"><span data-stu-id="e23a2-270">Therefore, it cannot be included in the `updg:before` section of an updategram.</span></span>  
  
-   <span data-ttu-id="e23a2-271">Os namespaces incluídos no escopo do fragmento XML inserido na coluna `xml` serão preservados e suas declarações de namespace serão adicionadas ao elemento superior do fragmento inserido.</span><span class="sxs-lookup"><span data-stu-id="e23a2-271">Namespaces that are in scope of the XML fragment inserted into the `xml` column will be preserved and their namespace declarations are added to the top element of the inserted fragment.</span></span>  
  
 <span data-ttu-id="e23a2-272">Por exemplo, no updategram a seguir (SampleUpdateGram.xml), o **\<Desc>** elemento atualiza a coluna ProductDescription na tabela ProductModel de produção>no [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] banco de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="e23a2-272">For example, in the following updategram (SampleUpdateGram.xml), the **\<Desc>** element updates the ProductDescription column in the Production>productModel table in the [!INCLUDE[ssSampleDBobject](../../../includes/sssampledbobject-md.md)] sample database.</span></span> <span data-ttu-id="e23a2-273">O resultado desse updategram é que o conteúdo XML da coluna ProductDescription é atualizado com o conteúdo XML do **\<Desc>** elemento.</span><span class="sxs-lookup"><span data-stu-id="e23a2-273">The result of this updategram is that the XML contents of the ProductDescription column are update with the XML contents of the **\<Desc>** element.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
    <updg:sync mapping-schema="SampleSchema.xml" >  
       <updg:before>  
<ProductModel ProductModelID="19">  
   <Name>Mountain-100</Name>  
</ProductModel>  
    </updg:before>  
    <updg:after>  
 <ProductModel>  
    <Name>Mountain-100</Name>  
    <Desc><?xml-stylesheet href="ProductDescription.xsl" type="text/xsl"?>  
        <p1:ProductDescription xmlns:p1="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription"   
              xmlns:wm="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"   
              xmlns:wf="http://www.adventure-works.com/schemas/OtherFeatures"   
              xmlns:html="http://www.w3.org/1999/xhtml"   
              xmlns="">  
  <p1:Summary>  
     <html:p>Insert Example</html:p>  
  </p1:Summary>  
  <p1:Manufacturer>  
    <p1:Name>AdventureWorks</p1:Name>  
    <p1:Copyright>2002</p1:Copyright>  
    <p1:ProductURL>HTTP://www.Adventure-works.com</p1:ProductURL>  
  </p1:Manufacturer>  
  <p1:Features>These are the product highlights.   
    <wm:Warranty>  
       <wm:WarrantyPeriod>3 years</wm:WarrantyPeriod>  
       <wm:Description>parts and labor</wm:Description>  
    </wm:Warranty>  
    <wm:Maintenance>  
       <wm:NoOfYears>10 years</wm:NoOfYears>  
       <wm:Description>maintenance contract available through your dealer or any AdventureWorks retail store.</wm:Description>  
    </wm:Maintenance>  
    <wf:wheel>High performance wheels.</wf:wheel>  
    <wf:saddle>  
      <html:i>Anatomic design</html:i> and made from durable leather for a full-day of riding in comfort.</wf:saddle>  
    <wf:pedal>  
       <html:b>Top-of-the-line</html:b> clipless pedals with adjustable tension.</wf:pedal>  
    <wf:BikeFrame>Each frame is hand-crafted in our Bothell facility to the optimum diameter and wall-thickness required of a premium mountain frame. The heat-treated welded aluminum frame has a larger diameter tube that absorbs the bumps.</wf:BikeFrame>  
    <wf:crankset> Triple crankset; alumunim crank arm; flawless shifting. </wf:crankset>  
   </p1:Features>  
   <p1:Picture>  
      <p1:Angle>front</p1:Angle>  
      <p1:Size>small</p1:Size>  
      <p1:ProductPhotoID>118</p1:ProductPhotoID>  
   </p1:Picture>  
   <p1:Specifications> These are the product specifications.  
     <Material>Almuminum Alloy</Material>  
     <Color>Available in most colors</Color>  
     <ProductLine>Mountain bike</ProductLine>  
     <Style>Unisex</Style>  
     <RiderExperience>Advanced to Professional riders</RiderExperience>  
   </p1:Specifications>  
  </p1:ProductDescription>  
 </Desc>  
      </ProductModel>  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="e23a2-274">O diagrama faz referência ao seguinte esquema XSD anotado (SampleSchema.xml):</span><span class="sxs-lookup"><span data-stu-id="e23a2-274">The updategram refers to the following annotated XSD schema (SampleSchema.xml).</span></span>  
  
```  
<?xml version="1.0" encoding="utf-8" ?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
           xmlns:sql="urn:schemas-microsoft-com:mapping-schema"  
           xmlns="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelDescription">   
  <xsd:element name="ProductModel"  sql:relation="Production.ProductModel" >  
     <xsd:complexType>  
       <xsd:sequence>  
          <xsd:element name="Name" type="xsd:string"></xsd:element>  
          <xsd:element name="Desc" sql:field="CatalogDescription" sql:datatype="xml">  
           <xsd:complexType>  
            <xsd:sequence>  
              <xsd:element name="ProductDescription">  
                 <xsd:complexType>  
                   <xsd:sequence>  
                     <xsd:element name="Summary" type="xsd:anyType">  
                     </xsd:element>  
                   </xsd:sequence>  
                 </xsd:complexType>  
              </xsd:element>  
            </xsd:sequence>  
           </xsd:complexType>  
          </xsd:element>   
       </xsd:sequence>  
       <xsd:attribute name="ProductModelID" sql:field="ProductModelID"/>  
     </xsd:complexType>  
  </xsd:element>  
</xsd:schema>  
```  
  
##### <a name="to-test-the-updategram"></a><span data-ttu-id="e23a2-275">Para testar o diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="e23a2-275">To test the updategram</span></span>  
  
1.  <span data-ttu-id="e23a2-276">Copie o esquema acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e23a2-276">Copy the schema above and paste it into a text file.</span></span> <span data-ttu-id="e23a2-277">Salve o arquivo como XSD-SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="e23a2-277">Save the file as XSD-SampleSchema.xml.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="e23a2-278">Pelo fato de os diagramas suportarem o mapeamento padrão, não há como identificar o começo e o fim do tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="e23a2-278">Because updategrams support default mapping, there is no way to identify the beginning and ending of the `xml` data type.</span></span> <span data-ttu-id="e23a2-279">Na prática, isso significa que será necessário um esquema de mapeamento durante a inserção ou atualização de tabelas com colunas de tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="e23a2-279">This effectively means that a mapping schema is required when inserting or updating tables with `xml` data type columns.</span></span> <span data-ttu-id="e23a2-280">Quando um esquema não é fornecido, SQLXML retorna um erro informando que uma das colunas da tabela está faltando.</span><span class="sxs-lookup"><span data-stu-id="e23a2-280">When a schema is not provided, SQLXML returns an error indicating that one of the columns is missing from the table.</span></span>  
  
2.  <span data-ttu-id="e23a2-281">Copie o diagrama de atualização acima e cole-o em um arquivo de texto.</span><span class="sxs-lookup"><span data-stu-id="e23a2-281">Copy the updategram above and paste it into a text file.</span></span> <span data-ttu-id="e23a2-282">Salve o arquivo como SampleUpdategram.xml na mesma pasta usada para salvar SampleSchema.xml.</span><span class="sxs-lookup"><span data-stu-id="e23a2-282">Save the file as SampleUpdategram.xml in the same folder used to save SampleSchema.xml.</span></span>  
  
3.  <span data-ttu-id="e23a2-283">Crie e use o Script de teste SQLXML 4.0 (Sqlxml4test.vbs) para executar o diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="e23a2-283">Create and use the SQLXML 4.0 Test Script (Sqlxml4test.vbs) to execute the updategram.</span></span>  
  
     <span data-ttu-id="e23a2-284">Para obter mais informações, consulte [usando o ADO para executar consultas do SQLXML 4,0](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span><span class="sxs-lookup"><span data-stu-id="e23a2-284">For more information, see [Using ADO to Execute SQLXML 4.0 Queries](../../sqlxml/using-ado-to-execute-sqlxml-4-0-queries.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e23a2-285">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e23a2-285">See Also</span></span>  
 [<span data-ttu-id="e23a2-286">Considerações de segurança do updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="e23a2-286">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
