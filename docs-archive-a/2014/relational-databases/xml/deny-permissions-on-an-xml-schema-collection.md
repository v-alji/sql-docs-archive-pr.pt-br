---
title: Recusar permissões em uma coleção de esquemas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- denying permissions [SQL Server], XML server collections
ms.assetid: e2b300b0-e734-4c43-a4da-c78e6e5d4fba
author: rothja
ms.author: jroth
ms.openlocfilehash: 0791a9bd9c7f6b323886a38bed27bea84940770d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569235"
---
# <a name="deny-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="ce15e-102">Recusar permissões em uma coleção de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="ce15e-102">Deny Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="ce15e-103">Permissões podem ser negadas para criar uma nova coleção de esquema XML ou para usar uma coleção existente.</span><span class="sxs-lookup"><span data-stu-id="ce15e-103">Permission can be denied to either create a new XML schema collection or use an existing one.</span></span>  
  
## <a name="denying-permission-to-create-an-xml-schema-collection"></a><span data-ttu-id="ce15e-104">Negando permissão para criar uma coleção de esquema XML</span><span class="sxs-lookup"><span data-stu-id="ce15e-104">Denying Permission to Create an XML Schema Collection</span></span>  
 <span data-ttu-id="ce15e-105">É possível negar permissão para criar uma coleção de esquema XML das seguintes maneiras:</span><span class="sxs-lookup"><span data-stu-id="ce15e-105">You can deny permission to create an XML schema collection in the following ways:</span></span>  
  
-   <span data-ttu-id="ce15e-106">Negar a permissão ALTER no esquema relacional.</span><span class="sxs-lookup"><span data-stu-id="ce15e-106">Deny ALTER permission on the relational schema.</span></span>  
  
-   <span data-ttu-id="ce15e-107">Negar CONTROL no esquema relacional para negar todas as permissões no esquema relacional e em todos os objetos contidos nele.</span><span class="sxs-lookup"><span data-stu-id="ce15e-107">Deny CONTROL on the relational schema to deny all permissions on the relational schema and on all the contained objects.</span></span>  
  
-   <span data-ttu-id="ce15e-108">Negar ALTER ANY SCHEMA no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ce15e-108">Deny ALTER ANY SCHEMA on the database.</span></span> <span data-ttu-id="ce15e-109">Nesse caso, a entidade de segurança não pode criar uma coleção de esquema XML em nenhum outro lugar no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ce15e-109">In this case, the principal cannot create an XML schema collection anywhere in the database.</span></span> <span data-ttu-id="ce15e-110">Observe também que negar a permissão ALTER ou CONTROL no banco de dados nega todas as permissões em todos os objetos do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ce15e-110">Note also that denying ALTER or CONTROL permission on the database denies all permissions on all objects in the database.</span></span>  
  
## <a name="denying-permissions-on-an-xml-schema-collection-object"></a><span data-ttu-id="ce15e-111">Negando permissões em um objeto da coleção de esquema XML</span><span class="sxs-lookup"><span data-stu-id="ce15e-111">Denying Permissions on an XML Schema Collection Object</span></span>  
 <span data-ttu-id="ce15e-112">A lista a seguir apresenta as permissões que podem ser negadas em uma coleção de esquema XML existente e seus resultados:</span><span class="sxs-lookup"><span data-stu-id="ce15e-112">Following are the permission that can be denied on an existing XML schema collection and the results:</span></span>  
  
-   <span data-ttu-id="ce15e-113">Negar a permissão ALTER nega a capacidade de uma entidade de segurança de modificar o conteúdo da coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ce15e-113">Denying the ALTER permission denies the principal the ability to modify the contents of the XML schema collection.</span></span>  
  
-   <span data-ttu-id="ce15e-114">Negar a permissão CONTROL nega a capacidade de uma entidade de segurança de executar qualquer operação na coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ce15e-114">Denying the CONTROL permission denies the principal the ability to perform any operation on the XML schema collection.</span></span>  
  
-   <span data-ttu-id="ce15e-115">Negar a permissão REFERENCES nega a capacidade da entidade de segurança de digitar ou restringir colunas e parâmetros de tipo xml usando a coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ce15e-115">Denying the REFERENCES permission denies the principal the ability to type or constrain xml type columns and parameters using the XML schema collection.</span></span> <span data-ttu-id="ce15e-116">Ela também nega a capacidade da entidade de segurança de fazer referência a esta coleção de esquema XML a partir de outras coleções de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ce15e-116">It also denies the principal the ability to refer to this XML schema collection from other XML schema collections.</span></span>  
  
-   <span data-ttu-id="ce15e-117">Negar a permissão VIEW DEFINITION nega a capacidade da entidade de segurança de exibir o conteúdo de uma coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ce15e-117">Denying the VIEW DEFINITION permission denies the principal the ability to view the contents of an XML schema collection.</span></span>  
  
-   <span data-ttu-id="ce15e-118">Negar a permissão EXECUTE nega a capacidade da entidade de segurança de inserir ou atualizar valores em colunas, variáveis e parâmetros que são de tipo ou restritas pela coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ce15e-118">Denying the EXECUTE permission denies the principal the ability to insert or update the values in columns, variables, and parameters that are typed or constrained by the XML schema collection.</span></span> <span data-ttu-id="ce15e-119">Também nega a capacidade da entidade de segurança de consultar os valores nestas colunas e variáveis de tipo xml.</span><span class="sxs-lookup"><span data-stu-id="ce15e-119">It also denies the principal the ability to query the values in those same xml type columns and variables.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ce15e-120">Exemplos</span><span class="sxs-lookup"><span data-stu-id="ce15e-120">Examples</span></span>  
 <span data-ttu-id="ce15e-121">Os cenários nos exemplos a seguir mostram como as permissões de esquema XML funcionam.</span><span class="sxs-lookup"><span data-stu-id="ce15e-121">The scenarios in the following examples show how XML schema permissions work.</span></span> <span data-ttu-id="ce15e-122">Cada exemplo cria o banco de dados, os esquemas relacionais e os logons de teste necessários.</span><span class="sxs-lookup"><span data-stu-id="ce15e-122">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="ce15e-123">Esses logons recebem as permissões necessárias na coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ce15e-123">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="ce15e-124">Cada exemplo faz a limpeza necessária no final.</span><span class="sxs-lookup"><span data-stu-id="ce15e-124">Each example does the necessary cleanup at the end.</span></span>  
  
### <a name="a-preventing-a-user-from-creating-an-xml-schema-collection"></a><span data-ttu-id="ce15e-125">a.</span><span class="sxs-lookup"><span data-stu-id="ce15e-125">A.</span></span> <span data-ttu-id="ce15e-126">Impedindo que um usuário crie uma coleção de esquema XML</span><span class="sxs-lookup"><span data-stu-id="ce15e-126">Preventing a user from creating an XML schema collection</span></span>  
 <span data-ttu-id="ce15e-127">Uma das maneiras de impedir que um usuário crie uma coleção de esquema XML é negar a permissão ALTER em um esquema relacional.</span><span class="sxs-lookup"><span data-stu-id="ce15e-127">One of the ways to prevent a user from creating an XML schema collection is by denying the ALTER permission on a relational schema.</span></span> <span data-ttu-id="ce15e-128">Isso é mostrado no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="ce15e-128">This is shown in the following example.</span></span>  
  
 <span data-ttu-id="ce15e-129">O exemplo cria um usuário, `TestLogin1`, e um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ce15e-129">The example creates a user, `TestLogin1`, and a database.</span></span> <span data-ttu-id="ce15e-130">Ele também cria um esquema relacional, além do esquema `dbo` , no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ce15e-130">It also creates a relational schema, in addition to the `dbo` schema, in the database.</span></span> <span data-ttu-id="ce15e-131">Inicialmente, a permissão `CREATE XML SCHEMA` permite que o usuário crie uma coleção de esquema em qualquer lugar no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ce15e-131">Initially, the `CREATE XML SCHEMA` permission allows the user to create a schema collection anywhere in the database.</span></span> <span data-ttu-id="ce15e-132">Em seguida, o exemplo nega permissão `ALTER` ao usuário em um dos esquemas relacionais.</span><span class="sxs-lookup"><span data-stu-id="ce15e-132">The example then denies `ALTER` permission to the user on one of the relational schemas.</span></span> <span data-ttu-id="ce15e-133">Isto impede que o usuário crie uma coleção de esquema XML naquele esquema relacional.</span><span class="sxs-lookup"><span data-stu-id="ce15e-133">This prevents the user from creating an XML schema collection in that relational schema.</span></span>  
  
```  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
CREATE USER TestLogin1  
GO  
-- For TestLogin1 to create/import XML schema collection, following  
-- permission needed.  
-- Database-level permissions  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
GO  
GRANT ALTER ANY SCHEMA TO TestLogin1  
GO  
-- Now TestLogin1 can import an XML schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
DROP XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection  
GO  
-- Now deny permission from TestLogin1 to alter myOtherDBSchema.  
setuser  
GO  
DENY ALTER ON SCHEMA::myOtherDBSchema TO TestLogin1  
GO  
-- Now TestLogin1 cannot create xml schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Final cleanup  
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
### <a name="b-denying-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="ce15e-134">B.</span><span class="sxs-lookup"><span data-stu-id="ce15e-134">B.</span></span> <span data-ttu-id="ce15e-135">Negando permissões em uma coleção de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="ce15e-135">Denying permissions on an XML schema collection</span></span>  
 <span data-ttu-id="ce15e-136">O exemplo a seguir mostra como uma permissão específica em uma coleção de esquema XML pode ser negada para um logon.</span><span class="sxs-lookup"><span data-stu-id="ce15e-136">The following example shows how a specific permission on an existing XML schema collection can be denied to a login.</span></span> <span data-ttu-id="ce15e-137">Neste exemplo, a permissão REFERENCES é negada a um logon de teste em uma coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ce15e-137">In this example, a test login is denied REFERENCES permission on an existing XML schema collection.</span></span>  
  
 <span data-ttu-id="ce15e-138">O exemplo cria um usuário, `TestLogin1`, e um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ce15e-138">The example creates a user, `TestLogin1`, and a database.</span></span> <span data-ttu-id="ce15e-139">Ele também cria um esquema relacional, além do esquema `dbo` , no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ce15e-139">It also creates a relational schema, in addition to the `dbo` schema, in the database.</span></span> <span data-ttu-id="ce15e-140">Inicialmente, a permissão `CREATE XML SCHEMA` permite que o usuário crie uma coleção de esquema em qualquer lugar no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ce15e-140">Initially, the `CREATE XML SCHEMA` permission allows the user to create a schema collection anywhere in the database.</span></span>  
  
 <span data-ttu-id="ce15e-141">A permissão `REFERENCES` na coleção de esquema XML permite que o `TestLogin1` use o esquema para criar uma coluna `xml` com tipo em uma tabela.</span><span class="sxs-lookup"><span data-stu-id="ce15e-141">The `REFERENCES` permission on the XML schema collection lets `TestLogin1` use the schema in creating a typed `xml` column in a table.</span></span> <span data-ttu-id="ce15e-142">Se a permissão `REFERENCES` na coleção de esquema XML for negada, ela impedirá que o `TestLogin1` use a coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ce15e-142">If the `REFERENCES` permission on the XML schema collection is denied, it prevents the `TestLogin1` from using the XML schema collection.</span></span>  
  
```  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
CREATE USER TestLogin1  
GO  
-- For TestLogin1 to create/import XML schema collection, the following  
-- permission is required.  
-- Database-level permissions  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
GO  
GRANT ALTER ANY SCHEMA TO TestLogin1  
GO  
-- Now TestLogin1 can import an XML schema collection.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Grant permission to TestLogin1 to create a table and reference the XML schema collection.  
SETUSER  
GO  
GRANT CREATE TABLE TO TestLogin1  
GO  
-- The user also needs REFERENCES permission to use the XML schema collection  
-- to create a typed XML column (REFERENCES permission on the schema   
-- collection is not needed).  
GRANT REFERENCES ON XML SCHEMA COLLECTION::myOtherDBSchema.myTestSchemaCollection   
TO TestLogin1  
GO  
  
--TestLogin1 can use the schema.  
CREATE TABLE T(i int, x xml (myOtherDBSchema.myTestSchemaCollection))  
GO  
-- Drop the table.  
DROP TABLE T  
GO  
-- Now deny REFERENCES permission to TestLogin1 on the schema created previously.  
SETUSER  
GO  
DENY REFERENCES ON XML SCHEMA COLLECTION::myOtherDBSchema.myTestSchemaCollection TO TestLogin1  
  
GO  
-- Now TestLogin1 cannot create xml schema collection  
SETUSER 'TestLogin1'  
GO  
-- Following statement fails. TestLogin1 does not have REFERENCES   
-- permission on the XML schema collection.  
CREATE TABLE T(i int, x xml (myOtherDBSchema.myTestSchemaCollection))  
GO  
  
-- Final cleanup  
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="ce15e-143">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ce15e-143">See Also</span></span>  
 <span data-ttu-id="ce15e-144">[Comparar XML digitado com XML não digitado](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="ce15e-144">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="ce15e-145">[Coleções de esquemas XML &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ce15e-145">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 <span data-ttu-id="ce15e-146">[Requisitos e limitações de uso de coleções de esquema XML no servidor](requirements-and-limitations-for-xml-schema-collections-on-the-server.md) </span><span class="sxs-lookup"><span data-stu-id="ce15e-146">[Requirements and Limitations for XML Schema Collections on the Server](requirements-and-limitations-for-xml-schema-collections-on-the-server.md) </span></span>  
 <span data-ttu-id="ce15e-147">[Permissões de objeto DENY &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ce15e-147">[DENY Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/deny-object-permissions-transact-sql) </span></span>  
 <span data-ttu-id="ce15e-148">[Permissões de objeto GRANT &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="ce15e-148">[GRANT Object Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-object-permissions-transact-sql) </span></span>  
 [<span data-ttu-id="ce15e-149">Dados XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="ce15e-149">XML Data &#40;SQL Server&#41;</span></span>](xml-data-sql-server.md)  
  
  
