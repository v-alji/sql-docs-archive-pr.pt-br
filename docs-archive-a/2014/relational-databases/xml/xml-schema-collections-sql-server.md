---
title: Coleções de esquema XML (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- XSD schemas [SQL Server]
- xml_schema_namespace function
- XML schema collections [SQL Server], about XML schema collections
- metadata [SQL Server], XML schema collections
- queries [XML in SQL Server], XML schema collections
- schema collections [SQL Server]
- schemas [SQL Server], XML
- XML [SQL Server], schema collections
- XML schema collections [SQL Server]
- schema collections [SQL Server], about XML schema collections
ms.assetid: 659d41aa-ccec-4554-804a-722a96ef25c2
author: rothja
ms.author: jroth
ms.openlocfilehash: 3ee4757f1353278447ee55e97c8d4ba23aa2d649
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575678"
---
# <a name="xml-schema-collections-sql-server"></a><span data-ttu-id="01c3a-102">Coleções de esquema XML (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="01c3a-102">XML Schema Collections (SQL Server)</span></span>
  <span data-ttu-id="01c3a-103">Conforme descrito no tópico [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql), o SQL Server fornece armazenamento nativo de dados XML por meio do `xml` tipo de dados.</span><span class="sxs-lookup"><span data-stu-id="01c3a-103">As described in the topic, [xml &#40;Transact-SQL&#41;](/sql/t-sql/xml/xml-transact-sql), SQL Server provides native storage of XML data through the `xml` data type.</span></span> <span data-ttu-id="01c3a-104">Opcionalmente, você pode associar esquemas XSD a uma variável ou a uma coluna do `xml` tipo por meio de uma coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="01c3a-104">You can optionally associate XSD schemas with a variable or a column of `xml` type through an XML schema collection.</span></span> <span data-ttu-id="01c3a-105">A coleção de esquema XML armazena os esquemas XML importados e, em seguida, é usada para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="01c3a-105">The XML schema collection stores the imported XML schemas and is then used to do the following:</span></span>  
  
-   <span data-ttu-id="01c3a-106">Validar instâncias XML</span><span class="sxs-lookup"><span data-stu-id="01c3a-106">Validate XML instances</span></span>  
  
-   <span data-ttu-id="01c3a-107">Definir o tipo dos dados XML conforme eles são armazenados no banco de dados</span><span class="sxs-lookup"><span data-stu-id="01c3a-107">Type the XML data as it is stored in the database</span></span>  
  
 <span data-ttu-id="01c3a-108">Observe que a coleção de esquema XML é uma entidade de metadados como uma tabela no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="01c3a-108">Note that the XML schema collection is a metadata entity like a table in the database.</span></span> <span data-ttu-id="01c3a-109">É possível criar, modificar e descartá-la.</span><span class="sxs-lookup"><span data-stu-id="01c3a-109">You can create, modify, and drop them.</span></span> <span data-ttu-id="01c3a-110">Esquemas especificados em uma instrução [CREATE XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) são importadas automaticamente no objeto da coleção de esquema XML recém-criado.</span><span class="sxs-lookup"><span data-stu-id="01c3a-110">Schemas specified in a [CREATE XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) statement are automatically imported into the newly created XML schema collection object.</span></span> <span data-ttu-id="01c3a-111">É possível importar esquemas adicionais ou componentes do esquema em um objeto de coleção existente no banco de dados usando a instrução [ALTER XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="01c3a-111">You can import additional schemas or schema components into an existing collection object in the database by using the [ALTER XML SCHEMA COLLECTION (Transact-SQL)](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) statement.</span></span>  
  
 <span data-ttu-id="01c3a-112">Como descrito no tópico, [XML com tipo vs. sem tipo](../xml/compare-typed-xml-to-untyped-xml.md), o XML armazenado em uma coluna ou variável à qual um esquema está associado é denominado XML **com tipo** porque o esquema fornece as informações necessárias do tipo de dados para os dados da instância.</span><span class="sxs-lookup"><span data-stu-id="01c3a-112">As described in the topic, [Typed vs. Untyped XML](../xml/compare-typed-xml-to-untyped-xml.md), the XML stored in a column or variable that a schema is associated with is referred to as **typed** XML, because the schema provides the necessary data type information for the instance data.</span></span> <span data-ttu-id="01c3a-113">O SQL Server usa essas informações de tipo para otimizar o armazenamento de dados.</span><span class="sxs-lookup"><span data-stu-id="01c3a-113">SQL Server uses this type information to optimize data storage.</span></span>  
  
 <span data-ttu-id="01c3a-114">O mecanismo do processamento de consultas também usa o esquema para verificação de tipo e otimizar modificação de dados e consultas.</span><span class="sxs-lookup"><span data-stu-id="01c3a-114">The query-processing engine also uses the schema for type checking and to optimize queries and data modification.</span></span>  
  
 <span data-ttu-id="01c3a-115">Além disso, SQL Server usa a coleção de esquema XML associada, no caso de tipo `xml` , para validar a instância XML.</span><span class="sxs-lookup"><span data-stu-id="01c3a-115">Also, SQL Server uses the associated XML schema collection, in the case of typed `xml`, to validate the XML instance.</span></span> <span data-ttu-id="01c3a-116">Se a instância XML estiver de acordo com o esquema, o banco de dados permitirá que a instância seja armazenada no sistema com suas informações de tipo.</span><span class="sxs-lookup"><span data-stu-id="01c3a-116">If the XML instance complies with the schema, the database allows the instance to be stored in the system with their type information.</span></span> <span data-ttu-id="01c3a-117">Caso contrário, a instância será rejeitada.</span><span class="sxs-lookup"><span data-stu-id="01c3a-117">Otherwise, it rejects the instance.</span></span>  
  
 <span data-ttu-id="01c3a-118">É possível usar a função intrínseca XML_SCHEMA_NAMESPACE para recuperar a coleção de esquema que está armazenada no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="01c3a-118">You can use the intrinsic function XML_SCHEMA_NAMESPACE to retrieve the schema collection that is stored in the database.</span></span> <span data-ttu-id="01c3a-119">Para obter mais informações, veja [Exibir uma coleção de esquemas XML armazenados](../xml/view-a-stored-xml-schema-collection.md).</span><span class="sxs-lookup"><span data-stu-id="01c3a-119">For more information, see [View a Stored XML Schema Collection](../xml/view-a-stored-xml-schema-collection.md).</span></span>  
  
 <span data-ttu-id="01c3a-120">Também é possível usar a coleção de esquema XML para digitar variáveis, parâmetros e colunas XML.</span><span class="sxs-lookup"><span data-stu-id="01c3a-120">You can also use the XML schema collection to type XML variables, parameters, and columns.</span></span>  
  
##  <a name="ddl-for-managing-schema-collections"></a><a name="ddl"></a> <span data-ttu-id="01c3a-121">DDL para gerenciar coleções de esquemas</span><span class="sxs-lookup"><span data-stu-id="01c3a-121">DDL for Managing Schema Collections</span></span>  
 <span data-ttu-id="01c3a-122">Você pode criar coleções de esquemas XML no banco de dados e associá-las a variáveis e colunas do tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="01c3a-122">You can create XML schema collections in the database and associate them with variables and columns of `xml` type.</span></span> <span data-ttu-id="01c3a-123">Para gerenciar coleções de esquema no banco de dados, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fornece as seguintes instruções DDL:</span><span class="sxs-lookup"><span data-stu-id="01c3a-123">To manage schema collections in the database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provides the following DDL statements:</span></span>  
  
-   <span data-ttu-id="01c3a-124">[CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) Importa os componentes de esquema para um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="01c3a-124">[CREATE XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-xml-schema-collection-transact-sql) Imports schema components into a database.</span></span>  
  
-   <span data-ttu-id="01c3a-125">[ALTER XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) Modifica os componentes de esquema em uma coleção de esquema XML existente.</span><span class="sxs-lookup"><span data-stu-id="01c3a-125">[ALTER XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-xml-schema-collection-transact-sql) Modifies the schema components in an existing XML schema collection.</span></span>  
  
-   <span data-ttu-id="01c3a-126">[DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) Exclui uma coleção de esquema XML completa e todos os seus componentes.</span><span class="sxs-lookup"><span data-stu-id="01c3a-126">[DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) Deletes a complete XML schema collection and all its components.</span></span>  
  
 <span data-ttu-id="01c3a-127">Para usar uma coleção de esquema XML e os esquemas contidos nela, você deve primeiro criar a coleção e os esquemas usando a instrução CREATE XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="01c3a-127">To use an XML schema collection and the schemas it contains, you must first create the collection and the schemas by using the CREATE XML SCHEMA COLLECTION statement.</span></span> <span data-ttu-id="01c3a-128">Após a criação da coleção de esquema, é possível criar variáveis e colunas do tipo `xml` e associar a coleção de esquema a elas.</span><span class="sxs-lookup"><span data-stu-id="01c3a-128">After the schema collection is created, you can then create variables and columns of `xml` type and associate the schema collection with them.</span></span> <span data-ttu-id="01c3a-129">Observe que depois que uma coleção de esquema é criada, são armazenados vários componentes de esquema nos metadados.</span><span class="sxs-lookup"><span data-stu-id="01c3a-129">Note that after a schema collection is created, various schema components are stored in the metadata.</span></span> <span data-ttu-id="01c3a-130">Também é possível usar ALTER XML SCHEMA COLLECTION para adicionar mais componentes a esquemas existentes ou adicionar novos esquemas a uma coleção existente.</span><span class="sxs-lookup"><span data-stu-id="01c3a-130">You can also use the ALTER XML SCHEMA COLLECTION to add more components to the existing schemas or add new schemas to an existing collection.</span></span>  
  
 <span data-ttu-id="01c3a-131">Para descartar a coleção de esquema, use a instrução DROP XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="01c3a-131">To drop the schema collection, use the DROP XML SCHEMA COLLECTION statement.</span></span> <span data-ttu-id="01c3a-132">Ela descarta todos os esquemas que estão contidos na coleção e remove o objeto da coleção.</span><span class="sxs-lookup"><span data-stu-id="01c3a-132">This drops all schemas that are contained in the collection and removes the collection object.</span></span> <span data-ttu-id="01c3a-133">Observe que, antes de conseguir remover uma coleção de esquema, as condições descritas em [DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql) deverão ser atendidas.</span><span class="sxs-lookup"><span data-stu-id="01c3a-133">Note that before you can drop a schema collection, the conditions described in [DROP XML SCHEMA COLLECTION &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-xml-schema-collection-transact-sql)must be met.</span></span>  
  
##  <a name="understanding-schema-components"></a><a name="components"></a> <span data-ttu-id="01c3a-134">Compreendendo componentes de esquema</span><span class="sxs-lookup"><span data-stu-id="01c3a-134">Understanding Schema Components</span></span>  
 <span data-ttu-id="01c3a-135">Quando a instrução CREATE XML SCHEMA COLLECTION é usada, vários componentes de esquema são importados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="01c3a-135">When you use the CREATE XML SCHEMA COLLECTION statement, various schema components are imported into the database.</span></span> <span data-ttu-id="01c3a-136">Os componentes de esquema incluem elementos, atributos e definições de tipo de esquema.</span><span class="sxs-lookup"><span data-stu-id="01c3a-136">Schema components include schema elements, attributes, and type definitions.</span></span> <span data-ttu-id="01c3a-137">Quando a instrução DROP XML SCHEMA COLLECTION é usada, a coleção completa é removida.</span><span class="sxs-lookup"><span data-stu-id="01c3a-137">When you use the DROP XML SCHEMA COLLECTION statement, you remove the complete collection.</span></span>  
  
 <span data-ttu-id="01c3a-138">CREATE XML SCHEMA COLLECTION salva os componentes do esquema em várias tabelas do sistema.</span><span class="sxs-lookup"><span data-stu-id="01c3a-138">CREATE XML SCHEMA COLLECTION saves the schema components into various system tables.</span></span>  
  
 <span data-ttu-id="01c3a-139">Por exemplo, considere o seguinte esquema:</span><span class="sxs-lookup"><span data-stu-id="01c3a-139">For example, consider the following schema:</span></span>  
  
```  
<?xml version="1.0"?>  
<xsd:schema xmlns:xsd="http://www.w3.org/2001/XMLSchema"  
            targetNamespace="uri:Cust_Orders2"  
            xmlns="uri:Cust_Orders2" >  
  <xsd:attribute name="SomeAttribute" type="xsd:int" />  
  <xsd:complexType name="SomeType" />  
  <xsd:complexType name="OrderType" >  
    <xsd:sequence>  
      <xsd:element name="OrderDate" type="xsd:date" />  
      <xsd:element name="RequiredDate" type="xsd:date" />  
      <xsd:element name="ShippedDate" type="xsd:date" />  
    </xsd:sequence>  
    <xsd:attribute name="OrderID" type="xsd:ID" />  
    <xsd:attribute name="CustomerID"  />  
    <xsd:attribute name="EmployeeID"  />  
  </xsd:complexType>  
  <xsd:complexType name="CustomerType" >  
     <xsd:sequence>  
        <xsd:element name="Order" type="OrderType"  
                     maxOccurs="unbounded" />  
       </xsd:sequence>  
      <xsd:attribute name="CustomerID" type="xsd:string" />  
      <xsd:attribute name="OrderIDList" type="xsd:IDREFS" />  
  </xsd:complexType>  
  <xsd:element name="Customer" type="CustomerType" />  
</xsd:schema>  
```  
  
 <span data-ttu-id="01c3a-140">O esquema anterior mostra os diferentes tipos de componentes que podem ser armazenados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="01c3a-140">The previous schema shows the different types of components that can be stored in the database.</span></span> <span data-ttu-id="01c3a-141">Esses esquemas incluem `SomeAttribute`, `SomeType`, `OrderType`, `CustomerType`, `Customer`, `Order`, `CustomerID`, `OrderID`, `OrderDate`, `RequiredDate`e `ShippedDate`.</span><span class="sxs-lookup"><span data-stu-id="01c3a-141">These include `SomeAttribute`, `SomeType`, `OrderType`, `CustomerType`, `Customer`, `Order`, `CustomerID`, `OrderID`, `OrderDate`, `RequiredDate`, and `ShippedDate`.</span></span>  
  
### <a name="component-categories"></a><span data-ttu-id="01c3a-142">Categorias de componentes</span><span class="sxs-lookup"><span data-stu-id="01c3a-142">Component Categories</span></span>  
 <span data-ttu-id="01c3a-143">Os componentes de esquema armazenados no banco de dados se enquadram nas seguintes categorias:</span><span class="sxs-lookup"><span data-stu-id="01c3a-143">The Schema components stored in the database fall into the following categories:</span></span>  
  
-   <span data-ttu-id="01c3a-144">ELEMENT</span><span class="sxs-lookup"><span data-stu-id="01c3a-144">ELEMENT</span></span>  
  
-   <span data-ttu-id="01c3a-145">ATTRIBUTE</span><span class="sxs-lookup"><span data-stu-id="01c3a-145">ATTRIBUTE</span></span>  
  
-   <span data-ttu-id="01c3a-146">TYPE (para tipos simples ou complexos)</span><span class="sxs-lookup"><span data-stu-id="01c3a-146">TYPE (for simple or complex types)</span></span>  
  
-   <span data-ttu-id="01c3a-147">ATTRIBUTEGROUP</span><span class="sxs-lookup"><span data-stu-id="01c3a-147">ATTRIBUTEGROUP</span></span>  
  
-   <span data-ttu-id="01c3a-148">MODELGROUP</span><span class="sxs-lookup"><span data-stu-id="01c3a-148">MODELGROUP</span></span>  
  
 <span data-ttu-id="01c3a-149">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="01c3a-149">For example:</span></span>  
  
-   <span data-ttu-id="01c3a-150">**SomeAttribute** é um componente de ATTRIBUTE.</span><span class="sxs-lookup"><span data-stu-id="01c3a-150">**SomeAttribute** is an ATTRIBUTE component.</span></span>  
  
-   <span data-ttu-id="01c3a-151">**SomeType**, **OrderType**e **CustomerType** são componentes de TYPE.</span><span class="sxs-lookup"><span data-stu-id="01c3a-151">**SomeType**, **OrderType**, and **CustomerType** are TYPE components.</span></span>  
  
-   <span data-ttu-id="01c3a-152">**Customer** é um componente de ELEMENT.</span><span class="sxs-lookup"><span data-stu-id="01c3a-152">**Customer** is an ELEMENT component.</span></span>  
  
 <span data-ttu-id="01c3a-153">Quando você importa um esquema no banco de dados, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não armazena o próprio esquema.</span><span class="sxs-lookup"><span data-stu-id="01c3a-153">When you import a schema into the database, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] does not store the schema itself.</span></span> <span data-ttu-id="01c3a-154">Em vez disso, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] armazena os vários componentes individuais.</span><span class="sxs-lookup"><span data-stu-id="01c3a-154">Instead, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stores the various individual components.</span></span> <span data-ttu-id="01c3a-155">Ou seja, a marca \<Schema> não é armazenada, apenas os componentes que estão definidos dentro dela são preservados.</span><span class="sxs-lookup"><span data-stu-id="01c3a-155">That is, the \<Schema> tag is not stored, only the components that are defined within it are preserved.</span></span> <span data-ttu-id="01c3a-156">Todos os elementos do esquema não são preservados.</span><span class="sxs-lookup"><span data-stu-id="01c3a-156">All schema elements are not preserved.</span></span> <span data-ttu-id="01c3a-157">Se a marca \<Schema> contiver atributos que especificam o comportamento padrão dos componentes dela, eles serão movidos para os componentes do esquema dentro dela durante o processo de importação, conforme mostrado na tabela a seguir.</span><span class="sxs-lookup"><span data-stu-id="01c3a-157">If the \<Schema> tag contains attributes that specify default behavior of its components, these attributes are moved to the schema components within it during the import process, as shown in the following table.</span></span>  
  
|<span data-ttu-id="01c3a-158">Nome do atributo</span><span class="sxs-lookup"><span data-stu-id="01c3a-158">Attribute name</span></span>|<span data-ttu-id="01c3a-159">Comportamento</span><span class="sxs-lookup"><span data-stu-id="01c3a-159">Behavior</span></span>|  
|--------------------|--------------|  
|<span data-ttu-id="01c3a-160">**attributeFormDefault**</span><span class="sxs-lookup"><span data-stu-id="01c3a-160">**attributeFormDefault**</span></span>|<span data-ttu-id="01c3a-161">O atributo **form** aplicado a todas as declarações de atributo no esquema em que ele ainda não está presente e o valor é definido como o valor do atributo **attributeFormDefault** .</span><span class="sxs-lookup"><span data-stu-id="01c3a-161">The **form** attribute applied to all attribute declarations in the schema where it is not already present and the value is set to the value of the **attributeFormDefault** attribute.</span></span>|  
|<span data-ttu-id="01c3a-162">**elementFormDefault**</span><span class="sxs-lookup"><span data-stu-id="01c3a-162">**elementFormDefault**</span></span>|<span data-ttu-id="01c3a-163">O atributo **form** aplicado a todas as declarações de elemento no esquema em que ele ainda não está presente e o valor é definido como o valor do atributo **elementFormDefault** .</span><span class="sxs-lookup"><span data-stu-id="01c3a-163">The **form** attribute applied to all element declarations in the schema where it is not already present and the value is set to the value of the **elementFormDefault** attribute.</span></span>|  
|<span data-ttu-id="01c3a-164">**blockDefault**</span><span class="sxs-lookup"><span data-stu-id="01c3a-164">**blockDefault**</span></span>|<span data-ttu-id="01c3a-165">O atributo **block** aplicado a todas as declarações de elemento e às definições de tipo em que ele ainda não está presente e o valor é definido como o valor do atributo **blockDefault** .</span><span class="sxs-lookup"><span data-stu-id="01c3a-165">The **block** attribute applied to all element declarations and type definitions where it is not already present and the value is set to the value of the **blockDefault** attribute.</span></span>|  
|<span data-ttu-id="01c3a-166">**finalDefault**</span><span class="sxs-lookup"><span data-stu-id="01c3a-166">**finalDefault**</span></span>|<span data-ttu-id="01c3a-167">O atributo **final** aplicado a todas as declarações de elemento e às definições de tipo em que ele ainda não está presente e o valor está definido como o valor do atributo **finalDefault** .</span><span class="sxs-lookup"><span data-stu-id="01c3a-167">The **final** attribute applied to all element declarations and type definitions where it is not already present and the value is set to the value of the **finalDefault** attribute.</span></span>|  
|<span data-ttu-id="01c3a-168">**targetNamespace**</span><span class="sxs-lookup"><span data-stu-id="01c3a-168">**targetNamespace**</span></span>|<span data-ttu-id="01c3a-169">Informações sobre os componentes que pertencem ao namespace de destino são armazenadas nos metadados.</span><span class="sxs-lookup"><span data-stu-id="01c3a-169">Information about the components that belong to the target namespace is stored in the metadata.</span></span>|  
  
##  <a name="permissions-on-an-xml-schema-collection"></a><a name="perms"></a> <span data-ttu-id="01c3a-170">Permissões em uma coleção de esquema XML</span><span class="sxs-lookup"><span data-stu-id="01c3a-170">Permissions on an XML Schema Collection</span></span>  
 <span data-ttu-id="01c3a-171">Você deve ter as permissões necessárias para fazer o seguinte:</span><span class="sxs-lookup"><span data-stu-id="01c3a-171">You must have the necessary permissions to do the following:</span></span>  
  
-   <span data-ttu-id="01c3a-172">Criar/carregar a coleção de esquema XML</span><span class="sxs-lookup"><span data-stu-id="01c3a-172">Create/load the XML schema collection</span></span>  
  
-   <span data-ttu-id="01c3a-173">Modificar a coleção de esquema XML</span><span class="sxs-lookup"><span data-stu-id="01c3a-173">Modify the XML schema collection</span></span>  
  
-   <span data-ttu-id="01c3a-174">Descartar a coleção de esquema XML</span><span class="sxs-lookup"><span data-stu-id="01c3a-174">Drop the XML schema collection</span></span>  
  
-   <span data-ttu-id="01c3a-175">Usar a coleção de esquema XML para digitar `xml` colunas de tipo, variáveis e parâmetros, ou usá-la em restrições de tabela ou coluna</span><span class="sxs-lookup"><span data-stu-id="01c3a-175">Use the XML schema collection to type `xml` type columns, variables, and parameters, or use it in table or column constraints</span></span>  
  
 <span data-ttu-id="01c3a-176">O modelo de segurança do SQL permite a permissão CONTROL em todos os objetos.</span><span class="sxs-lookup"><span data-stu-id="01c3a-176">The SQL Server security model allows CONTROL permission on every object.</span></span> <span data-ttu-id="01c3a-177">O usuário autorizado dessa permissão obtém todas as outras permissões no objeto.</span><span class="sxs-lookup"><span data-stu-id="01c3a-177">The grantee of this permission obtains all other permissions on the object.</span></span> <span data-ttu-id="01c3a-178">O proprietário do objeto também tem todas as permissões no objeto.</span><span class="sxs-lookup"><span data-stu-id="01c3a-178">The owner of the object also has all the permissions on the object.</span></span>  
  
 <span data-ttu-id="01c3a-179">O proprietário e o usuário autorizado da permissão CONTROL em um objeto podem conceder qualquer permissão no objeto.</span><span class="sxs-lookup"><span data-stu-id="01c3a-179">The owner and the grantee of the CONTROL permission on an object can grant any permission on the object.</span></span> <span data-ttu-id="01c3a-180">Um usuário que não é um proprietário e não tem a permissão CONTROL ainda pode conceder permissão em um objeto quando WITH GRANT OPTION estiver especificada.</span><span class="sxs-lookup"><span data-stu-id="01c3a-180">A user who is not the owner and does not have CONTROL permission can still grant permission on an object when WITH GRANT OPTION is specified.</span></span> <span data-ttu-id="01c3a-181">Por exemplo, assuma que o Usuário A tem a permissão REFERENCES na coleção de esquema XML S, através da WITH GRANT OPTION, mas nenhuma outra permissão em S. O Usuário A pode conceder a permissão REFERENCES ao Usuário B na coleção de esquema S.</span><span class="sxs-lookup"><span data-stu-id="01c3a-181">For example, assume User A has REFERENCES permission on XML schema collection S, through WITH GRANT OPTION, but no other permissions on S. User A could grant User B REFERENCES permission on schema collection S.</span></span>  
  
 <span data-ttu-id="01c3a-182">O modelo de segurança também permite permissões para criar e usar coleções de esquema XML ou transferir a propriedade de um usuário para outro.</span><span class="sxs-lookup"><span data-stu-id="01c3a-182">The security model also allows permissions to create and use XML schema collections or transfer ownership from one user to another.</span></span> <span data-ttu-id="01c3a-183">Os tópicos a seguir descrevem as permissões de coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="01c3a-183">The following topics describe the XML schema collection permissions.</span></span>  
  
-   [<span data-ttu-id="01c3a-184">Conceder permissões em uma Coleção de Esquemas XML</span><span class="sxs-lookup"><span data-stu-id="01c3a-184">Grant Permissions on an XML Schema Collection</span></span>](../xml/grant-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="01c3a-185">Este tópico discute como conceder permissões para criar uma coleção de esquema XML e como conceder permissões em um objeto de coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="01c3a-185">This topic discussess how to grant permissions to create an XML schema collection and how to grant permissions on an XML schema collection object.</span></span>  
  
-   [<span data-ttu-id="01c3a-186">Revogar permissões em uma Coleção de Esquemas XML</span><span class="sxs-lookup"><span data-stu-id="01c3a-186">Revoke Permissions on an XML Schema Collection</span></span>](../xml/revoke-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="01c3a-187">Este tópico discute como a revogação de permissões pode ser usada para evitar a criação de uma coleção de esquema XML e como revogar permissões em um objeto de coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="01c3a-187">This topic discusses how revoking permissions can be used to prevent the creation of an XML schema collection and how to revoke permissions on an XML schema collection object.</span></span>  
  
-   [<span data-ttu-id="01c3a-188">Recusar permissões em uma Coleção de Esquemas XML</span><span class="sxs-lookup"><span data-stu-id="01c3a-188">Deny Permissions on an XML Schema Collection</span></span>](../xml/deny-permissions-on-an-xml-schema-collection.md)  
  
     <span data-ttu-id="01c3a-189">Este tópico discute como negar permissões para criar uma coleção de esquema XML e como negar permissões em um objeto de coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="01c3a-189">This topic discusses how to deny permissions to create an XML schema collection and deny permission on an XML schema collection object.</span></span>  
  
##  <a name="getting-information-about-xml-schemas-and-schema-collections"></a><a name="info"></a> <span data-ttu-id="01c3a-190">Adquirindo Informações sobre esquemas XML e coleções de esquemas</span><span class="sxs-lookup"><span data-stu-id="01c3a-190">Getting Information about XML Schemas and Schema Collections</span></span>  
 <span data-ttu-id="01c3a-191">Coleções de esquema XML são enumeradas na exibição do catálogo sys.xml_schema_collections.</span><span class="sxs-lookup"><span data-stu-id="01c3a-191">XML schema collections are enumerated in the catalog view, sys.xml_schema_collections.</span></span> <span data-ttu-id="01c3a-192">A coleção de esquema XML "sys" está definida pelo sistema.</span><span class="sxs-lookup"><span data-stu-id="01c3a-192">The XML schema collection "sys" is defined by the system.</span></span> <span data-ttu-id="01c3a-193">Ela contém os namespaces predefinidos que podem ser usados em todas as coleções de esquema XML definidas pelo usuário sem precisar carregá-las explicitamente.</span><span class="sxs-lookup"><span data-stu-id="01c3a-193">It contains the predefined namespaces that can be used in all user-defined XML schema collections without having to load them explicitly.</span></span> <span data-ttu-id="01c3a-194">Essa lista contém os namespaces para xml, xs, xsi, fn e xdt.</span><span class="sxs-lookup"><span data-stu-id="01c3a-194">This list contains the namespaces for xml, xs, xsi, fn, and xdt.</span></span> <span data-ttu-id="01c3a-195">Duas outras exibições do catálogo são sys.xml_schema_namespaces, que enumera todos os namespaces dentro de cada coleção de esquema XML, e sys.xml_components, que enumera todos os componentes do esquema XML dentro de cada esquema XML.</span><span class="sxs-lookup"><span data-stu-id="01c3a-195">Two other catalog views are sys.xml_schema_namespaces, which enumerates all namespaces within each XML schema collection, and sys.xml_components, which enumerates all XML schema components within each XML schema.</span></span>  
  
 <span data-ttu-id="01c3a-196">A função interna **XML_SCHEMA_NAMESPACE**, *SchemaName, XmlSchemaCollectionName, namespace-URI*, produz uma `xml` instância de tipo de dados..</span><span class="sxs-lookup"><span data-stu-id="01c3a-196">The built-in function **XML_SCHEMA_NAMESPACE**, *schemaName, XmlSchemacollectionName, namespace-uri*, yields an `xml` data type instance..</span></span> <span data-ttu-id="01c3a-197">Essa instância contém fragmentos de esquema XML estão contidos em uma coleção de esquema XML, exceto os esquemas XML predefinidos.</span><span class="sxs-lookup"><span data-stu-id="01c3a-197">This instance contains XML schema fragments for schemas that are contained in an XML schema collection, except the predefined XML schemas.</span></span>  
  
 <span data-ttu-id="01c3a-198">É possível enumerar o conteúdo de uma coleção de esquema XML das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="01c3a-198">You can enumerate the contents of an XML schema collection in the following ways:</span></span>  
  
-   <span data-ttu-id="01c3a-199">Escreva consultas Transact-SQL nas exibições do catálogo apropriadas para coleções de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="01c3a-199">Write Transact-SQL queries on the appropriate catalog views for XML schema collections.</span></span>  
  
-   <span data-ttu-id="01c3a-200">Use a função interna **XML_SCHEMA_NAMESPACE()** .</span><span class="sxs-lookup"><span data-stu-id="01c3a-200">Use the built-in function **XML_SCHEMA_NAMESPACE()**.</span></span> <span data-ttu-id="01c3a-201">Você pode aplicar `xml` métodos de tipo de dados na saída dessa função.</span><span class="sxs-lookup"><span data-stu-id="01c3a-201">You can apply `xml` data type methods on the output of this function.</span></span> <span data-ttu-id="01c3a-202">No entanto não é possível modificar os esquemas XML subjacentes.</span><span class="sxs-lookup"><span data-stu-id="01c3a-202">However, you cannot modify the underlying XML schemas.</span></span>  
  
 <span data-ttu-id="01c3a-203">Esses são ilustrados nos exemplos a seguir.</span><span class="sxs-lookup"><span data-stu-id="01c3a-203">These are illustrated in the following examples.</span></span>  
  
### <a name="example-enumerate-the-xml-namespaces-in-an-xml-schema-collection"></a><span data-ttu-id="01c3a-204">Exemplo: Enumerar os namespaces XML em uma coleção de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="01c3a-204">Example: Enumerate the XML Namespaces in an XML Schema Collection</span></span>  
 <span data-ttu-id="01c3a-205">Use a consulta a seguir para a coleção de esquema XML "myCollection":</span><span class="sxs-lookup"><span data-stu-id="01c3a-205">Use the following query for the XML schema collection "myCollection":</span></span>  
  
```  
SELECT XSN.name  
FROM    sys.xml_schema_collections XSC JOIN sys.xml_schema_namespaces XSN  
    ON (XSC.xml_collection_id = XSN.xml_collection_id)  
WHERE    XSC.name = 'myCollection'     
```  
  
### <a name="example-enumerate-the-contents-of-an-xml-schema-collection"></a><span data-ttu-id="01c3a-206">Exemplo: Enumerar o conteúdo de uma coleção de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="01c3a-206">Example: Enumerate the Contents of an XML Schema Collection</span></span>  
 <span data-ttu-id="01c3a-207">A instrução a seguir enumera o conteúdo da coleção de esquema XML "myCollection" dentro do esquema relacional dbo.</span><span class="sxs-lookup"><span data-stu-id="01c3a-207">The following statement enumerates the contents of the XML schema collection "myCollection" within the relational schema, dbo.</span></span>  
  
```  
SELECT XML_SCHEMA_NAMESPACE (N'dbo', N'myCollection')  
```  
  
 <span data-ttu-id="01c3a-208">Esquemas XML individuais dentro da coleção podem ser obtidos como `xml` instâncias de tipo de dados, especificando o namespace de destino como o terceiro argumento para **XML_SCHEMA_NAMESPACE ()**.</span><span class="sxs-lookup"><span data-stu-id="01c3a-208">Individual XML schemas within the collection can be obtained as `xml` data type instances by specifying the target namespace as the third argument to **XML_SCHEMA_NAMESPACE()**.</span></span> <span data-ttu-id="01c3a-209">Isso é mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="01c3a-209">This is shown in the following example.</span></span>  
  
### <a name="example-output-a-specified-schema-from-an-xml-schema-collection"></a><span data-ttu-id="01c3a-210">Exemplo: Gerar um esquema especificado com base em uma coleção de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="01c3a-210">Example: Output a Specified Schema from an XML Schema Collection</span></span>  
 <span data-ttu-id="01c3a-211">A instrução a seguir produz o esquema XML com o namespace de destino "<https://www.microsoft.com/books>" da coleção de esquemas XML "myCollection" dentro do esquema relacional dbo.</span><span class="sxs-lookup"><span data-stu-id="01c3a-211">The following statement outputs the XML schema with the target namespace "<https://www.microsoft.com/books>" from the XML schema collection "myCollection" within the relational schema, dbo.</span></span>  
  
```  
SELECT XML_SCHEMA_NAMESPACE (N'dbo', N'myCollection',   
N'https://www.microsoft.com/books')  
```  
  
### <a name="querying-xml-schemas"></a><span data-ttu-id="01c3a-212">Consultando esquemas XML</span><span class="sxs-lookup"><span data-stu-id="01c3a-212">Querying XML Schemas</span></span>  
 <span data-ttu-id="01c3a-213">É possível consultar esquemas XML carregados em coleções de esquema XML das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="01c3a-213">You can query XML schemas that you have loaded into XML schema collections in the following ways:</span></span>  
  
-   <span data-ttu-id="01c3a-214">Escreva consultas Transact-SQL em exibições do catálogo para namespaces de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="01c3a-214">Write Transact-SQL queries on catalog views for XML schema namespaces.</span></span>  
  
-   <span data-ttu-id="01c3a-215">Crie uma tabela que contenha uma coluna de tipo de dados `xml` para armazenar seus esquemas XML e também para carregá-las no sistema de tipo XML.</span><span class="sxs-lookup"><span data-stu-id="01c3a-215">Create a table that contains an `xml` data type column to store your XML schemas and also load them into the XML type system.</span></span> <span data-ttu-id="01c3a-216">É possível consultar a coluna XML usando os métodos de tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="01c3a-216">You can query the XML column by using the `xml` data type methods.</span></span> <span data-ttu-id="01c3a-217">Além disso, é possível construir um índice XML nessa coluna.</span><span class="sxs-lookup"><span data-stu-id="01c3a-217">Also, you can build an XML index on this column.</span></span> <span data-ttu-id="01c3a-218">No entanto, com essa abordagem, o aplicativo deve manter consistência entre os esquemas XML armazenados na coluna XML e no sistema de tipo XML.</span><span class="sxs-lookup"><span data-stu-id="01c3a-218">However, with this approach, the application must maintain consistency between the XML schemas stored in the XML column and the XML type system.</span></span> <span data-ttu-id="01c3a-219">Por exemplo, se você descartar o namespace do esquema XML do sistema de tipo XML, também deverá descartá-lo da tabela para preservar a consistência.</span><span class="sxs-lookup"><span data-stu-id="01c3a-219">For example, if you drop the XML schema namespace from the XML type system, you also have to drop it from the table in order to preserve consistency.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="01c3a-220">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="01c3a-220">See Also</span></span>  
 <span data-ttu-id="01c3a-221">[Exibir uma coleção de esquemas XML armazenados](../xml/view-a-stored-xml-schema-collection.md) </span><span class="sxs-lookup"><span data-stu-id="01c3a-221">[View a Stored XML Schema Collection](../xml/view-a-stored-xml-schema-collection.md) </span></span>  
 <span data-ttu-id="01c3a-222">[Pré-processar um esquema para mesclar esquemas incluídos](../xml/preprocess-a-schema-to-merge-included-schemas.md) </span><span class="sxs-lookup"><span data-stu-id="01c3a-222">[Preprocess a Schema to Merge Included Schemas](../xml/preprocess-a-schema-to-merge-included-schemas.md) </span></span>  
 [<span data-ttu-id="01c3a-223">Requisitos e limitações para o uso de Coleções de Esquemas XML no servidor</span><span class="sxs-lookup"><span data-stu-id="01c3a-223">Requirements and Limitations for XML Schema Collections on the Server</span></span>](../xml/requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
