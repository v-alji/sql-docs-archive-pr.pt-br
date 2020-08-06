---
title: Introdução aos Updategrams (SQLXML 4,0) | Microsoft Docs
ms.custom: ''
ms.date: 04/27/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: reference
helpviewer_keywords:
- explicit schema mapping [SQLXML]
- updategrams [SQLXML], mapping schema specifying
- namespaces [SQLXML]
- updategrams [SQLXML], about updategrams
- attribute-centric mapping
- invalid characters [SQLXML]
- element-centric mapping [SQLXML]
- mapping schema [SQLXML], updategrams
- namespaces [SQLXML], updategrams
- executing updategrams [SQLXML]
- implicit schema mapping
ms.assetid: cfe24e82-a645-4f93-ab16-39c21f90cce6
author: rothja
ms.author: jroth
ms.openlocfilehash: eb2f29d7f5d86d28254dacb9c55cceb9b4c72d8d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87680839"
---
# <a name="introduction-to-updategrams-sqlxml-40"></a><span data-ttu-id="23a34-102">Introdução aos diagramas de atualização (SQLXML 4.0)</span><span class="sxs-lookup"><span data-stu-id="23a34-102">Introduction to Updategrams (SQLXML 4.0)</span></span>
  <span data-ttu-id="23a34-103">Você pode modificar (inserir, atualizar ou excluir) um banco de dados [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] do em um documento XML existente usando um updategram ou a [!INCLUDE[tsql](../../../includes/tsql-md.md)] função OPENXML.</span><span class="sxs-lookup"><span data-stu-id="23a34-103">You can modify (insert, update, or delete) a database in [!INCLUDE[msCoName](../../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] from an existing XML document by using an updategram or the OPENXML [!INCLUDE[tsql](../../../includes/tsql-md.md)] function.</span></span>  
  
 <span data-ttu-id="23a34-104">A função OPENXML modifica um banco de dados fragmentando o documento XML existente e fornecendo um conjunto de linhas que pode ser passado para uma instrução INSERT, UPDATE ou DELETE.</span><span class="sxs-lookup"><span data-stu-id="23a34-104">The OPENXML function modifies a database by shredding the existing XML document and providing a rowset that can be passed to an INSERT, UPDATE, or DELETE statement.</span></span> <span data-ttu-id="23a34-105">Com OPENXML, as operações são executadas diretamente nas tabelas de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="23a34-105">With OPENXML, operations are performed directly against the database tables.</span></span> <span data-ttu-id="23a34-106">Portanto, OPENXML é especialmente apropriada nos casos em que provedores de conjuntos de linhas, como uma tabela, possam aparecer como uma origem.</span><span class="sxs-lookup"><span data-stu-id="23a34-106">Therefore, OPENXML is most appropriate wherever rowset providers, such as a table, can appear as a source.</span></span>  
  
 <span data-ttu-id="23a34-107">Da mesma forma que a OPENXML, um diagrama de atualização permite inserir, atualizar ou excluir dados no banco de dados. Entretanto, ele trabalha nas exibições em XML fornecidas pelo esquema XSD (ou um XDR) anotado; por exemplo, as atualizações são aplicadas à exibição em XML fornecida pelo esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="23a34-107">Like OPENXML, an updategram allows you to insert, update, or delete data in the database; however, an updategram works against the XML views provided by the annotated XSD (or an XDR) schema; for example, the updates are applied to the XML view provided by the mapping schema.</span></span> <span data-ttu-id="23a34-108">O esquema de mapeamento, por sua vez, tem as informações necessárias para mapear elementos e atributos XML para as tabelas e colunas de bancos de dados correspondentes.</span><span class="sxs-lookup"><span data-stu-id="23a34-108">The mapping schema, in turn, has the necessary information to map XML elements and attributes to the corresponding database tables and columns.</span></span> <span data-ttu-id="23a34-109">O diagrama de atualização usa estas informações de mapeamento para atualizar as tabelas e colunas de bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="23a34-109">The updategram uses this mapping information to update the database tables and columns.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="23a34-110">Esta documentação parte do pressuposto de que você esteja familiarizado com suporte a modelos e ao esquema de mapeamento no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="23a34-110">This documentation assumes that you are familiar with templates and mapping schema support in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="23a34-111">Para obter mais informações, consulte [introdução aos esquemas XSD anotados &#40;SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="23a34-111">For more information, see [Introduction to Annotated XSD Schemas &#40;SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/introduction-to-annotated-xsd-schemas-sqlxml-4-0.md).</span></span> <span data-ttu-id="23a34-112">Para aplicativos herdados que usam XDR, consulte [esquemas XDR anotados &#40;preteridos no SQLXML 4,0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="23a34-112">For legacy applications that use XDR, see [Annotated XDR Schemas &#40;Deprecated in SQLXML 4.0&#41;](../../sqlxml/annotated-xsd-schemas/annotated-xdr-schemas-deprecated-in-sqlxml-4-0.md).</span></span>  
  
## <a name="required-namespaces-in-the-updategram"></a><span data-ttu-id="23a34-113">Namespaces necessários no diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="23a34-113">Required Namespaces in the Updategram</span></span>  
 <span data-ttu-id="23a34-114">As palavras-chave em um updategram, como, **\<sync>** **\<before>** e **\<after>** , existem no `urn:schemas-microsoft-com:xml-updategram` namespace.</span><span class="sxs-lookup"><span data-stu-id="23a34-114">The keywords in an updategram, such as **\<sync>**, **\<before>**, and **\<after>**, exist in the `urn:schemas-microsoft-com:xml-updategram` namespace.</span></span> <span data-ttu-id="23a34-115">O prefixo de namespace utilizado é arbitrário.</span><span class="sxs-lookup"><span data-stu-id="23a34-115">The namespace prefix that you use is arbitrary.</span></span> <span data-ttu-id="23a34-116">Nesta documentação, o prefixo `updg` indica o namespace `updategram`.</span><span class="sxs-lookup"><span data-stu-id="23a34-116">In this documentation, the `updg` prefix denotes the `updategram` namespace.</span></span>  
  
## <a name="reviewing-syntax"></a><span data-ttu-id="23a34-117">Revisando a sintaxe</span><span class="sxs-lookup"><span data-stu-id="23a34-117">Reviewing Syntax</span></span>  
 <span data-ttu-id="23a34-118">Um updategram é um modelo com **\<sync>** , **\<before>** e **\<after>** blocos que formam a sintaxe do updategram.</span><span class="sxs-lookup"><span data-stu-id="23a34-118">An updategram is a template with **\<sync>**, **\<before>**, and **\<after>** blocks that form the syntax of the updategram.</span></span> <span data-ttu-id="23a34-119">O seguinte código mostra esta sintaxe em sua forma mais simples:</span><span class="sxs-lookup"><span data-stu-id="23a34-119">The following code shows this syntax in its simplest form:</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
  <updg:sync [mapping-schema= "AnnotatedSchemaFile.xml"] >  
    <updg:before>  
        ...  
    </updg:before>  
    <updg:after>  
        ...  
    </updg:after>  
  </updg:sync>  
</ROOT>  
```  
  
 <span data-ttu-id="23a34-120">As seguintes definições descrevem a função de cada um destes blocos:</span><span class="sxs-lookup"><span data-stu-id="23a34-120">The following definitions describe the role of each of these blocks:</span></span>  
  
 **\<before>**  
 <span data-ttu-id="23a34-121">Identifica o estado existente (também chamado de "o estado antes") da instância de registro.</span><span class="sxs-lookup"><span data-stu-id="23a34-121">Identifies the existing state (also called "the before state") of the record instance.</span></span>  
  
 **\<after>**  
 <span data-ttu-id="23a34-122">Identifica o estado novo para o qual dados devem ser alterados.</span><span class="sxs-lookup"><span data-stu-id="23a34-122">Identifies the new state to which data is to be changed.</span></span>  
  
 **\<sync>**  
 <span data-ttu-id="23a34-123">Contém os **\<before>** **\<after>** blocos e.</span><span class="sxs-lookup"><span data-stu-id="23a34-123">Contains the **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="23a34-124">Um **\<sync>** bloco pode conter mais de um conjunto de **\<before>** **\<after>** blocos e.</span><span class="sxs-lookup"><span data-stu-id="23a34-124">A **\<sync>** block can contain more than one set of **\<before>** and **\<after>** blocks.</span></span> <span data-ttu-id="23a34-125">Se houver mais de um conjunto de **\<before>** blocos e **\<after>** , esses blocos (mesmo se estiverem vazios) deverão ser especificados como pares.</span><span class="sxs-lookup"><span data-stu-id="23a34-125">If there is more than one set of **\<before>** and **\<after>** blocks, these blocks (even if they are empty) must be specified as pairs.</span></span> <span data-ttu-id="23a34-126">Além disso, um updategram pode ter mais de um **\<sync>** bloco.</span><span class="sxs-lookup"><span data-stu-id="23a34-126">Furthermore, an updategram can have more than one **\<sync>** block.</span></span> <span data-ttu-id="23a34-127">Cada **\<sync>** bloco é uma unidade de transação (o que significa que tudo no **\<sync>** bloco é feito ou nada é feito).</span><span class="sxs-lookup"><span data-stu-id="23a34-127">Each **\<sync>** block is one unit of transaction (which means that either everything in the **\<sync>** block is done or nothing is done).</span></span> <span data-ttu-id="23a34-128">Se você especificar vários **\<sync>** blocos em um updategram, a falha de um **\<sync>** bloco não afetará os outros **\<sync>** blocos.</span><span class="sxs-lookup"><span data-stu-id="23a34-128">If you specify multiple **\<sync>** blocks in an updategram, the failure of one **\<sync>** block does not affect the other **\<sync>** blocks.</span></span>  
  
 <span data-ttu-id="23a34-129">Se um updategram exclui, insere ou atualiza uma instância de registro depende do conteúdo dos **\<before>** **\<after>** blocos e:</span><span class="sxs-lookup"><span data-stu-id="23a34-129">Whether an updategram deletes, inserts, or updates a record instance depends on the contents of the **\<before>** and **\<after>** blocks:</span></span>  
  
-   <span data-ttu-id="23a34-130">Se uma instância de registro aparecer apenas no **\<before>** bloco sem nenhuma instância correspondente no **\<after>** bloco, o updategram executará uma operação de exclusão.</span><span class="sxs-lookup"><span data-stu-id="23a34-130">If a record instance appears only in the **\<before>** block with no corresponding instance in the **\<after>** block, the updategram performs a delete operation.</span></span>  
  
-   <span data-ttu-id="23a34-131">Se uma instância de registro aparecer apenas no **\<after>** bloco sem nenhuma instância correspondente no **\<before>** bloco, será uma operação de inserção.</span><span class="sxs-lookup"><span data-stu-id="23a34-131">If a record instance appears only in the **\<after>** block with no corresponding instance in the **\<before>** block, it is an insert operation.</span></span>  
  
-   <span data-ttu-id="23a34-132">Se uma instância de registro aparecer no **\<before>** bloco e tiver uma instância correspondente no **\<after>** bloco, será uma operação de atualização.</span><span class="sxs-lookup"><span data-stu-id="23a34-132">If a record instance appears in the **\<before>** block and has a corresponding instance in the **\<after>** block, it is an update operation.</span></span> <span data-ttu-id="23a34-133">Nesse caso, o updategram atualiza a instância do registro para os valores especificados no **\<after>** bloco.</span><span class="sxs-lookup"><span data-stu-id="23a34-133">In this case, the updategram updates the record instance to the values that are specified in the **\<after>** block.</span></span>  
  
## <a name="specifying-a-mapping-schema-in-the-updategram"></a><span data-ttu-id="23a34-134">Especificando um esquema de mapeamento no diagrama de atualização</span><span class="sxs-lookup"><span data-stu-id="23a34-134">Specifying a Mapping Schema in the Updategram</span></span>  
 <span data-ttu-id="23a34-135">Em um diagrama de atualização, a abstração XML que é fornecida por um esquema de mapeamento (é dado suporte a esquemas XSD e também XDR) pode ser implícita ou explícita (ou seja, um diagrama de atualização pode funcionar com ou sem um esquema de mapeamento especificado).</span><span class="sxs-lookup"><span data-stu-id="23a34-135">In an updategram, the XML abstraction that is provided by a mapping schema (both XSD and XDR schemas are supported) can be implicit or explicit (that is, an updategram can work with or without a specified mapping schema).</span></span> <span data-ttu-id="23a34-136">Se você não especificar um esquema de mapeamento, o updategram assumirá um mapeamento implícito (o mapeamento padrão), em que cada elemento no **\<before>** bloco ou **\<after>** bloco é mapeado para uma tabela e o elemento ou atributo filho de cada elemento é mapeado para uma coluna no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="23a34-136">If you do not specify a mapping schema, the updategram assumes an implicit mapping (the default mapping), where each element in the **\<before>** block or **\<after>** block maps to a table and each element's child element or attribute maps to a column in the database.</span></span> <span data-ttu-id="23a34-137">Se você especificar explicitamente um esquema de mapeamento, os elementos e atributos no diagrama de atualização deverão corresponder aos elementos e atributos no esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="23a34-137">If you explicitly specify a mapping schema, the elements and attributes in the updategram must match the elements and attributes in the mapping schema.</span></span>  
  
### <a name="implicit-default-mapping"></a><span data-ttu-id="23a34-138">Mapeamento implícito (padrão)</span><span class="sxs-lookup"><span data-stu-id="23a34-138">Implicit (default) Mapping</span></span>  
 <span data-ttu-id="23a34-139">Na maioria dos casos, um diagrama de atualização que executa atualizações simples pode não precisar de um esquema de mapeamento.</span><span class="sxs-lookup"><span data-stu-id="23a34-139">In most cases, an updategram that performs simple updates might not require a mapping schema.</span></span> <span data-ttu-id="23a34-140">Neste caso, o diagrama de atualização se baseia no esquema de mapeamento padrão.</span><span class="sxs-lookup"><span data-stu-id="23a34-140">In this case, the updategram relies on the default mapping schema.</span></span>  
  
 <span data-ttu-id="23a34-141">O seguinte diagrama de atualização demonstra o mapeamento implícito.</span><span class="sxs-lookup"><span data-stu-id="23a34-141">The following updategram demonstrates implicit mapping.</span></span> <span data-ttu-id="23a34-142">Neste exemplo, o diagrama de atualização insere um novo cliente na tabela Sales.Customer.</span><span class="sxs-lookup"><span data-stu-id="23a34-142">In this example, the updategram inserts a new customer in the Sales.Customer table.</span></span> <span data-ttu-id="23a34-143">Como esse updategram usa o mapeamento implícito, o \<Sales.Customer> elemento é mapeado para a tabela Sales. Customer e os atributos CustomerID e vendedorid são mapeados para as colunas correspondentes na tabela Sales. Customer.</span><span class="sxs-lookup"><span data-stu-id="23a34-143">Because this updategram uses implicit mapping, the \<Sales.Customer> element maps to the Sales.Customer table, and the CustomerID and SalesPersonID attributes map to the corresponding columns in the Sales.Customer table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
<updg:before>  
</updg:before>  
<updg:after>  
    <Sales.Customer CustomerID="1" SalesPersonID="277" />  
    </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="explicit-mapping"></a><span data-ttu-id="23a34-144">Mapeamento explícito</span><span class="sxs-lookup"><span data-stu-id="23a34-144">Explicit Mapping</span></span>  
 <span data-ttu-id="23a34-145">Se você especificar um esquema de mapeamento (XSD ou XDR), o diagrama de atualização usará o esquema para determinar as tabelas e colunas do banco de dados que deverão ser atualizados.</span><span class="sxs-lookup"><span data-stu-id="23a34-145">If you specify a mapping schema (either XSD or XDR), the updategram uses the schema to determine the database tables and columns that are to be updated.</span></span>  
  
 <span data-ttu-id="23a34-146">Se o diagrama de atualização realizar uma atualização complexa (por exemplo, inserindo registros em várias tabelas com base no relacionamento pai-filho especificado no esquema de mapeamento), você deverá fornecer explicitamente o esquema de mapeamento usando o atributo `mapping-schema` sobre o qual o diagrama de atualização será executado.</span><span class="sxs-lookup"><span data-stu-id="23a34-146">If the updategram performs a complex update (for example, inserting records in multiple tables on the basis of the parent-child relationship that is specified in the mapping schema), you must explicitly provide the mapping schema by using the `mapping-schema` attribute against which the updategram executes.</span></span>  
  
 <span data-ttu-id="23a34-147">Como um diagrama de atualização é um modelo, o caminho especificado para o esquema de mapeamento no diagrama de atualização é relativo ao local do arquivo do modelo (relativo ao local onde o diagrama de atualização está armazenado).</span><span class="sxs-lookup"><span data-stu-id="23a34-147">Because an updategram is a template, the path specified for the mapping schema in the updategram is relative to the location of the template file (relative to where the updategram is stored).</span></span> <span data-ttu-id="23a34-148">Para obter mais informações, consulte [especificando um esquema de mapeamento anotado em um Updategram &#40;SQLXML 4,0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span><span class="sxs-lookup"><span data-stu-id="23a34-148">For more information, see [Specifying an Annotated Mapping Schema in an Updategram &#40;SQLXML 4.0&#41;](specifying-an-annotated-mapping-schema-in-an-updategram-sqlxml-4-0.md).</span></span>  
  
## <a name="element-centric-and-attribute-centric-mapping-in-updategrams"></a><span data-ttu-id="23a34-149">Mapeamento centrado em elemento e mapeamento centrado em atributo em diagramas de atualização</span><span class="sxs-lookup"><span data-stu-id="23a34-149">Element-centric and Attribute-centric Mapping in Updategrams</span></span>  
 <span data-ttu-id="23a34-150">Com o mapeamento padrão (quando o esquema de mapeamento não for especificado no diagrama de atualização), os elementos do diagrama de atualização são mapeados para tabelas e os elementos-filho (no caso do mapeamento centrado em elementos) e os atributos (no caso do mapeamento centrado em atributos) são mapeados para colunas.</span><span class="sxs-lookup"><span data-stu-id="23a34-150">With default mapping (when the mapping schema is not specified in the updategram), the updategram elements map to tables and the  child elements (in the case of element-centric mapping) and the attributes (in the case of attribute-centric mapping) map to columns.</span></span>  
  
### <a name="element-centric-mapping"></a><span data-ttu-id="23a34-151">Mapeamento centrado em elemento</span><span class="sxs-lookup"><span data-stu-id="23a34-151">Element-centric Mapping</span></span>  
 <span data-ttu-id="23a34-152">Em um diagrama de atualização centrado em elemento, um elemento contém elementos filhos que denotam as propriedades do elemento.</span><span class="sxs-lookup"><span data-stu-id="23a34-152">In an element-centric updategram, an element contains child elements that denote the properties of the element.</span></span> <span data-ttu-id="23a34-153">Como um exemplo, consulte o seguinte diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="23a34-153">As an example, refer to the following updategram.</span></span> <span data-ttu-id="23a34-154">O **\<Person.Contact>** elemento contém os **\<FirstName>** **\<LastName>** elementos filho e.</span><span class="sxs-lookup"><span data-stu-id="23a34-154">The **\<Person.Contact>** element contains the **\<FirstName>** and **\<LastName>** child elements.</span></span> <span data-ttu-id="23a34-155">Esses elementos filho são propriedades do **\<Person.Contact>** elemento.</span><span class="sxs-lookup"><span data-stu-id="23a34-155">These child elements are properties of the **\<Person.Contact>** element.</span></span>  
  
 <span data-ttu-id="23a34-156">Como esse updategram não especifica um esquema de mapeamento, o updategram usa o mapeamento implícito, em que o **\<Person.Contact>** elemento é mapeado para a tabela Person. Contact e seus elementos filho são mapeados para as colunas FirstName e LastName.</span><span class="sxs-lookup"><span data-stu-id="23a34-156">Because this updategram does not specify a mapping schema, the updategram uses implicit mapping, where the **\<Person.Contact>** element maps to the Person.Contact table and its child elements map to the FirstName and LastName columns.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:after>  
    <Person.Contact>  
       <FirstName>Catherine</FirstName>  
       <LastName>Abel</LastName>  
    </Person.Contact>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="attribute-centric-mapping"></a><span data-ttu-id="23a34-157">mapeamento centrado em atributo</span><span class="sxs-lookup"><span data-stu-id="23a34-157">Attribute-centric Mapping</span></span>  
 <span data-ttu-id="23a34-158">Em um mapeamento centrado em atributo, os elementos têm atributos.</span><span class="sxs-lookup"><span data-stu-id="23a34-158">In an attribute-centric mapping, the elements have attributes.</span></span> <span data-ttu-id="23a34-159">O seguinte diagrama de atualização usa mapeamento centrado em atributo.</span><span class="sxs-lookup"><span data-stu-id="23a34-159">The following updategram uses attribute-centric mapping.</span></span> <span data-ttu-id="23a34-160">Neste exemplo, o **\<Person.Contact>** elemento consiste nos atributos **FirstName** e **LastName** .</span><span class="sxs-lookup"><span data-stu-id="23a34-160">In this example, the **\<Person.Contact>** element consists of the **FirstName** and **LastName** attributes.</span></span> <span data-ttu-id="23a34-161">Esses atributos são as propriedades do **\<Person.Contact>** elemento.</span><span class="sxs-lookup"><span data-stu-id="23a34-161">These attributes are the properties of the **\<Person.Contact>** element.</span></span> <span data-ttu-id="23a34-162">Como no exemplo anterior, este updategram não especifica nenhum esquema de mapeamento, portanto, ele se baseia no mapeamento implícito para mapear o **\<Person.Contact>** elemento para a tabela Person. Contact e os atributos do elemento para as respectivas colunas na tabela.</span><span class="sxs-lookup"><span data-stu-id="23a34-162">As in the previous example, this updategram specifies no mapping schema, so it relies on implicit mapping to map the **\<Person.Contact>** element to the Person.Contact table and the element's attributes to the respective columns in the table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
    <Person.Contact FirstName="Catherine" LastName="Abel" />  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
### <a name="using-both-element-centric-and-attribute-centric-mapping"></a><span data-ttu-id="23a34-163">Usando o mapeamento centrado em elemento e centrado em atributo</span><span class="sxs-lookup"><span data-stu-id="23a34-163">Using Both Element-centric and Attribute-centric Mapping</span></span>  
 <span data-ttu-id="23a34-164">Você pode especificar uma mistura de mapeamento centrado em elemento e mapeamento centrado em atributo, conforme mostrado no seguinte diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="23a34-164">You can specify a mix of element-centric and attribute-centric mapping, as shown in the following updategram.</span></span> <span data-ttu-id="23a34-165">Observe que o **\<Person.Contact>** elemento contém um atributo e um elemento filho.</span><span class="sxs-lookup"><span data-stu-id="23a34-165">Notice that the **\<Person.Contact>** element contains both an attribute and a child element.</span></span> <span data-ttu-id="23a34-166">Além disso, este diagrama de atualização se baseia em mapeamento implícito.</span><span class="sxs-lookup"><span data-stu-id="23a34-166">Also, this updategram relies on implicit mapping.</span></span> <span data-ttu-id="23a34-167">Assim, o atributo **FirstName** e o **\<LastName>** elemento filho são mapeados para as colunas correspondentes na tabela Person. Contact.</span><span class="sxs-lookup"><span data-stu-id="23a34-167">Thus, the **FirstName** attribute and the **\<LastName>** child element map to corresponding columns in the Person.Contact table.</span></span>  
  
```  
<ROOT xmlns:updg="urn:schemas-microsoft-com:xml-updategram">  
<updg:sync >  
  <updg:before>  
  </updg:before>  
  <updg:after>  
    <Person.Contact FirstName="Catherine" >  
       <LastName>Abel</LastName>  
    </Person.Contact>  
  </updg:after>  
</updg:sync>  
</ROOT>  
```  
  
## <a name="working-with-characters-valid-in-sql-server-but-not-valid-in-xml"></a><span data-ttu-id="23a34-168">Trabalhando com caracteres válidos no SQL Server, mas não válidos em XML</span><span class="sxs-lookup"><span data-stu-id="23a34-168">Working with Characters Valid in SQL Server but Not Valid in XML</span></span>  
 <span data-ttu-id="23a34-169">No [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], os nomes de tabela podem incluir um espaço.</span><span class="sxs-lookup"><span data-stu-id="23a34-169">In [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], table names can include a space.</span></span> <span data-ttu-id="23a34-170">Porém, este tipo de nome de tabela não é válido em XML.</span><span class="sxs-lookup"><span data-stu-id="23a34-170">However, this type of table name is not valid in XML.</span></span>  
  
 <span data-ttu-id="23a34-171">Para codificar caracteres que são [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identificadores válidos, mas não são identificadores XML válidos, use ' __xHHHH \_ \_ ' como o valor de codificação, em que HHHH significa o código UCS-2 hexadecimal de quatro dígitos para o caractere na ordem de bits mais significativa.</span><span class="sxs-lookup"><span data-stu-id="23a34-171">To encode characters that are valid [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] identifiers but are not valid XML identifiers, use '__xHHHH\_\_' as the encoding value, where HHHH stands for the four-digit hexadecimal UCS-2 code for the character in the most significant bit-first order.</span></span> <span data-ttu-id="23a34-172">Usando esse esquema de codificação, um caractere de espaço é substituído por x0020 (o código hexadecimal de quatro dígitos para um caractere de espaço); Portanto, o nome da tabela [Order Details] in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] se torna _x005B_Order_x0020_Details_x005D \_ em XML.</span><span class="sxs-lookup"><span data-stu-id="23a34-172">Using this encoding scheme, a space character gets replaced with x0020 (the four-digit hexadecimal code for a space character); thus, the table name [Order Details] in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] becomes _x005B_Order_x0020_Details_x005D\_ in XML.</span></span>  
  
 <span data-ttu-id="23a34-173">Da mesma forma, talvez seja necessário especificar nomes de elementos de três partes, como \<[database].[owner].[table]> .</span><span class="sxs-lookup"><span data-stu-id="23a34-173">Similarly, you might need to specify three-part element names, such as \<[database].[owner].[table]>.</span></span> <span data-ttu-id="23a34-174">Como os caracteres de colchetes ([e]) não são válidos em XML, você deve especificar isso como \<_x005B_database_x005D\_._x005B_owner_x005D\_._x005B_table_x005D\_> , em que _x005B \_ é a codificação para o colchete esquerdo ([) e _x005D \_ é a codificação para o colchete direito (]).</span><span class="sxs-lookup"><span data-stu-id="23a34-174">Because the bracket characters ([ and ]) are not valid in XML, you must specify this as \<_x005B_database_x005D\_._x005B_owner_x005D\_._x005B_table_x005D\_>, where _x005B\_ is the encoding for the left bracket ([) and _x005D\_ is the encoding for the right bracket (]).</span></span>  
  
## <a name="executing-updategrams"></a><span data-ttu-id="23a34-175">Executando diagramas de atualização</span><span class="sxs-lookup"><span data-stu-id="23a34-175">Executing Updategrams</span></span>  
 <span data-ttu-id="23a34-176">Como um diagrama de atualização é um modelo, todos os mecanismos de processamento de um modelo se aplicam ao diagrama de atualização.</span><span class="sxs-lookup"><span data-stu-id="23a34-176">Because an updategram is a template, all the processing mechanisms of a template apply to the updategram.</span></span> <span data-ttu-id="23a34-177">Para SQLXML 4.0, você pode executar um diagrama de atualização em qualquer um dos seguintes modos:</span><span class="sxs-lookup"><span data-stu-id="23a34-177">For SQLXML 4.0, you can execute an updategram in either of the following ways:</span></span>  
  
-   <span data-ttu-id="23a34-178">Enviando-o em um comando ADO.</span><span class="sxs-lookup"><span data-stu-id="23a34-178">By submitting it in an ADO command.</span></span>  
  
-   <span data-ttu-id="23a34-179">Enviando-o como um comando OLE DB.</span><span class="sxs-lookup"><span data-stu-id="23a34-179">By submitting it as an OLE DB command.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="23a34-180">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="23a34-180">See Also</span></span>  
 [<span data-ttu-id="23a34-181">Considerações de segurança do updategram &#40;SQLXML 4,0&#41;</span><span class="sxs-lookup"><span data-stu-id="23a34-181">Updategram Security Considerations &#40;SQLXML 4.0&#41;</span></span>](../security/updategram-security-considerations-sqlxml-4-0.md)  
  
  
