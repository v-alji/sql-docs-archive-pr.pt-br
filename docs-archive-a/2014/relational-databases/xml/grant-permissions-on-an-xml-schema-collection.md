---
title: Conceder permissões em uma coleção de esquemas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- granting permissions [SQL Server], XML schema collections
- ALTER permission
ms.assetid: ffbb829c-3b8f-4e5d-97d9-ab4059aab0db
author: rothja
ms.author: jroth
ms.openlocfilehash: 2dc6384acb2f079245c80923e683ebe2c03d2562
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679197"
---
# <a name="grant-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="ea011-102">Conceder permissões em uma coleção de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="ea011-102">Grant Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="ea011-103">É possível conceder permissões para criar uma coleção de esquema XML e também permissões em um objeto da coleção de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="ea011-103">You can grant permissions to create an XML schema collection and also grant permissions on an XML schema collection object.</span></span>  
  
## <a name="granting-permission-to-create-an-xml-schema-collection"></a><span data-ttu-id="ea011-104">Concedendo permissão para criar uma coleção de esquema XML</span><span class="sxs-lookup"><span data-stu-id="ea011-104">Granting Permission to Create an XML Schema Collection</span></span>  
 <span data-ttu-id="ea011-105">Para criar uma coleção de esquema XML, são necessárias as seguintes permissões:</span><span class="sxs-lookup"><span data-stu-id="ea011-105">To create an XML schema collection, the following permissions are required:</span></span>  
  
-   <span data-ttu-id="ea011-106">A entidade de segurança requer permissão CREATE XML SCHEMA COLLECTION no nível de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ea011-106">The principal requires CREATE XML SCHEMA COLLECTION permission at the database-level.</span></span>  
  
-   <span data-ttu-id="ea011-107">Como as coleções de esquema XML estão no escopo do esquema relacional, a entidade de segurança deve ter permissão ALTER no esquema relacional.</span><span class="sxs-lookup"><span data-stu-id="ea011-107">Because the XML schema collections are relational schema-scoped, the principal must also have ALTER permission on the relational schema.</span></span>  
  
 <span data-ttu-id="ea011-108">As seguintes permissões permitem que uma entidade de segurança crie uma coleção de esquema XML em um esquema relacional em um banco de dados em um servidor:</span><span class="sxs-lookup"><span data-stu-id="ea011-108">The following permissions let a principal create an XML schema collection in a relational schema in a database on a server:</span></span>  
  
-   <span data-ttu-id="ea011-109">Permissão CONTROL no servidor</span><span class="sxs-lookup"><span data-stu-id="ea011-109">CONTROL permission on the server</span></span>  
  
-   <span data-ttu-id="ea011-110">Permissão ALTER ANY DATABASE no servidor</span><span class="sxs-lookup"><span data-stu-id="ea011-110">ALTER ANY DATABASE permission on the server</span></span>  
  
-   <span data-ttu-id="ea011-111">Permissão ALTER no banco de dados</span><span class="sxs-lookup"><span data-stu-id="ea011-111">ALTER permission on the database</span></span>  
  
-   <span data-ttu-id="ea011-112">Permissão CONTROL no banco de dados</span><span class="sxs-lookup"><span data-stu-id="ea011-112">CONTROL permission in the database</span></span>  
  
-   <span data-ttu-id="ea011-113">Permissões ALTER ANY SCHEMA e CREATE XML SCHEMA COLLECTION no banco de dados</span><span class="sxs-lookup"><span data-stu-id="ea011-113">ALTER ANY SCHEMA permission and CREATE XML SCHEMA COLLECTION permission in the database</span></span>  
  
-   <span data-ttu-id="ea011-114">Permissões ALTER ou CONTROL no esquema relacional e CREATE XML SCHEMA COLLECTION no banco de dados</span><span class="sxs-lookup"><span data-stu-id="ea011-114">ALTER or CONTROL permission on the relational schema and CREATE XML SCHEMA COLLECTION permission in the database</span></span>  
  
 <span data-ttu-id="ea011-115">Esse último método de permissões é usado no exemplo seguinte.</span><span class="sxs-lookup"><span data-stu-id="ea011-115">This last method of permissions is used in the following example.</span></span>  
  
 <span data-ttu-id="ea011-116">O proprietário do esquema relacional se torna o proprietário da coleção de esquema XML criada naquele esquema.</span><span class="sxs-lookup"><span data-stu-id="ea011-116">The owner of the relational schema becomes the owner of the XML schema collection created in that schema.</span></span> <span data-ttu-id="ea011-117">Esse proprietário tem controle total sobre a coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ea011-117">This owner then has full control over the XML schema collection.</span></span> <span data-ttu-id="ea011-118">Portanto esse proprietário pode modificar a coleção de esquema XML, digitar uma coluna xml ou descartar a coleção e esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ea011-118">Therefore, this owner can modify the XML schema collection, type an xml column, or drop the XML schema collection.</span></span>  
  
## <a name="granting-permissions-on-an-xml-schema-collection-object"></a><span data-ttu-id="ea011-119">Concedendo permissões em um objeto da coleção de esquema XML</span><span class="sxs-lookup"><span data-stu-id="ea011-119">Granting Permissions on an XML Schema Collection Object</span></span>  
 <span data-ttu-id="ea011-120">As seguintes permissões são permitidas na coleção de esquema XML:</span><span class="sxs-lookup"><span data-stu-id="ea011-120">The following permissions are allowed on the XML schema collection:</span></span>  
  
-   <span data-ttu-id="ea011-121">A permissão ALTER é necessária ao modificar o conteúdo de uma coleção de esquema XML existente usando uma instrução ALTER XML SCHEMA COLLECTION.</span><span class="sxs-lookup"><span data-stu-id="ea011-121">The ALTER permission is required when modifying contents of an existing XML schema collection by using the ALTER XML SCHEMA COLLECTION statement.</span></span>  
  
-   <span data-ttu-id="ea011-122">A permissão CONTROL permite que um usuário execute qualquer operação na coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ea011-122">The CONTROL permission lets a user perform any operation on the XML schema collection.</span></span>  
  
-   <span data-ttu-id="ea011-123">A permissão TAKE OWNERSHIP é necessária para transferir a propriedade da coleção de esquemas XML de uma entidade de segurança para outra.</span><span class="sxs-lookup"><span data-stu-id="ea011-123">The TAKE OWNERSHIP permission is required to transfer ownership of the XML schema collection from one principal to another.</span></span>  
  
-   <span data-ttu-id="ea011-124">A permissão REFERENCES autoriza a entidade de segurança a usar a coleção de esquemas XML para digitar ou restringir colunas de tipo `xml` em tabelas, exibições e parâmetros.</span><span class="sxs-lookup"><span data-stu-id="ea011-124">The REFERENCES permission authorizes the principal to use the XML schema collection to type or constrain `xml` type columns, in tables and views and parameters.</span></span> <span data-ttu-id="ea011-125">A permissão REFERENCES também é necessária quando uma coleção de esquemas XML faz referência à outra.</span><span class="sxs-lookup"><span data-stu-id="ea011-125">The REFERENCES permission is also required when one XML schema collection refers to another.</span></span>  
  
-   <span data-ttu-id="ea011-126">A permissão VIEW DEFINITION permite que a entidade de segurança consulte o conteúdo de uma coleção de esquema XML por meio de XML_SCHEMA_NAMESPACE ou de exibições de catálogo, desde que a entidade de segurança tenha uma das permissões ALTER, REFERENCES ou CONTROL na coleção.</span><span class="sxs-lookup"><span data-stu-id="ea011-126">The VIEW DEFINITION permission allows the principal to query the contents of an XML schema collection either through XML_SCHEMA_NAMESPACE or through the catalog views, provided this principal also has one of the ALTER, REFERENCES, or CONTROL permissions on the collection.</span></span>  
  
-   <span data-ttu-id="ea011-127">A permissão EXECUTE é necessária para validar valores inseridos ou atualizados pela entidade de segurança na coleção de esquemas XML que está digitando ou restringindo as variáveis, os parâmetros e as colunas de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="ea011-127">The EXECUTE permission is required to validate values inserted or updated by the principal against the XML schema collection that is typing or constraining the `xml` type columns, variables, and parameters.</span></span> <span data-ttu-id="ea011-128">Essa permissão também é necessária para consultar o XML armazenado nessas colunas e variáveis.</span><span class="sxs-lookup"><span data-stu-id="ea011-128">You also need this permission when you are querying the XML stored in these columns and variables.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="ea011-129">Exemplos</span><span class="sxs-lookup"><span data-stu-id="ea011-129">Examples</span></span>  
 <span data-ttu-id="ea011-130">Os cenários nos exemplos seguintes ilustram como as permissões de esquema XML funcionam.</span><span class="sxs-lookup"><span data-stu-id="ea011-130">The scenarios in the following examples illustrate how XML schema permissions work.</span></span> <span data-ttu-id="ea011-131">Cada exemplo cria o banco de dados, os esquemas relacionais e os logons de teste necessários.</span><span class="sxs-lookup"><span data-stu-id="ea011-131">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="ea011-132">Esses logons recebem as permissões necessárias na coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ea011-132">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="ea011-133">Cada exemplo faz a limpeza necessária no final.</span><span class="sxs-lookup"><span data-stu-id="ea011-133">Each example does the necessary clean up at the end.</span></span>  
  
### <a name="a-granting-permissions-to-create-an-xml-schema-collection"></a><span data-ttu-id="ea011-134">a.</span><span class="sxs-lookup"><span data-stu-id="ea011-134">A.</span></span> <span data-ttu-id="ea011-135">Concedendo permissões para criar uma coleção de esquema XML</span><span class="sxs-lookup"><span data-stu-id="ea011-135">Granting permissions to create an XML schema collection</span></span>  
 <span data-ttu-id="ea011-136">O exemplo a seguir mostra como conceder permissões para que uma entidade de segurança possa criar uma coleção de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="ea011-136">The following example shows how to grant permissions so that a principal can create an XML schema collection.</span></span> <span data-ttu-id="ea011-137">O exemplo cria um banco de dados de exemplo e um usuário de teste, `TestLogin1`.</span><span class="sxs-lookup"><span data-stu-id="ea011-137">The example creates a sample database and a test user, `TestLogin1`.</span></span> <span data-ttu-id="ea011-138">`TestLogin1` recebe a permissão `ALTER` no esquema relacional e a permissão `CREATE XML SCHEMA COLLECTION` no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ea011-138">`TestLogin1` is then given `ALTER` permission on the relational schema and given `CREATE XML SCHEMA COLLECTION` permission on the database.</span></span> <span data-ttu-id="ea011-139">Com essas permissões, `TestLogin1` pode criar com êxito uma coleção de esquemas XML de exemplo.</span><span class="sxs-lookup"><span data-stu-id="ea011-139">With these permissions, `TestLogin1` succeeds in creating a sample XML schema collection.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Execute CREATE XML SCHEMA COLLECTION.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="root" type="xsd:byte"/>  
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
  
### <a name="b-granting-permission-to-use-an-existing-xml-schema-collection"></a><span data-ttu-id="ea011-140">B.</span><span class="sxs-lookup"><span data-stu-id="ea011-140">B.</span></span> <span data-ttu-id="ea011-141">Concedendo permissão para usar uma coleção de esquema XML existente</span><span class="sxs-lookup"><span data-stu-id="ea011-141">Granting permission to use an existing XML schema collection</span></span>  
 <span data-ttu-id="ea011-142">O exemplo seguinte mostra ainda mais o modelo de permissão para a coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ea011-142">The following example further shows the permission model for the XML schema collection.</span></span> <span data-ttu-id="ea011-143">Ele mostra como permissões diferentes são necessárias para criar e usar a coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="ea011-143">The example shows how different permissions are required to create and use the XML schema collection.</span></span>  
  
 <span data-ttu-id="ea011-144">O exemplo cria um banco de dados de teste e um logon, `TestLogin1`.</span><span class="sxs-lookup"><span data-stu-id="ea011-144">The example creates a test database and a login, `TestLogin1`.</span></span> <span data-ttu-id="ea011-145">`TestLogin1` cria uma coleção de esquemas XML no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ea011-145">`TestLogin1` creates an XML schema collection in the database.</span></span> <span data-ttu-id="ea011-146">Em seguida, o logon cria uma tabela e usa a coleção de esquemas XML para criar uma coluna do tipo xml.</span><span class="sxs-lookup"><span data-stu-id="ea011-146">The login then creates a table and uses the XML schema collection to create a typed xml column.</span></span> <span data-ttu-id="ea011-147">Em seguida, o usuário insere dados e os consulta.</span><span class="sxs-lookup"><span data-stu-id="ea011-147">The user then inserts data and queries it.</span></span> <span data-ttu-id="ea011-148">Todas essas etapas requerem as permissões de esquema necessárias conforme mostrado no código.</span><span class="sxs-lookup"><span data-stu-id="ea011-148">All these steps require the necessary schema permissions, as shown in the code.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- Grant permission to the user.  
SETUSER  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Now user can execute the previous CREATE XML SCHEMA COLLECTION statement.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
  
-- Create a table by using the collection to type an XML column.   
--TestLogin1 must have permission to create a table.  
SETUSER  
GO  
GRANT CREATE TABLE TO TestLogin1  
GO  
-- The user also must have REFERENCES permission to use the XML schema collection  
-- to create a typed XML column (REFERENCES permission on schema   
-- collection is not needed).  
GRANT REFERENCES ON XML SCHEMA COLLECTION::myTestSchemaCollection   
TO TestLogin1  
GO  
-- Now user can create a table and use the XML schema collection to create   
-- a typed XML column.  
SETUSER 'TestLogin1'  
GO  
CREATE TABLE MyTestTable (xmlCol xml (dbo.myTestSchemaCollection))  
GO  
-- To insert data in the table, the user needs EXECUTE permission on the XML schema collection.  
-- GRANT EXECUTE permission to TestLogin2 on the xml schema collection.  
SETUSER  
GO  
GRANT EXECUTE ON XML SCHEMA COLLECTION::myTestSchemaCollection   
TO TestLogin1  
GO  
-- TestLogin1 does not own the dbo schema. This user must have INSERT permission.  
GRANT INSERT TO TestLogin1  
GO  
-- Now the user can insert data into the table.  
SETUSER 'TestLogin1'  
GO  
INSERT INTO MyTestTable VALUES('  
<telephone xmlns="http://schemas.adventure-works.com/Additional/ContactInfo">111-1111</telephone>  
')  
GO  
-- To query the table, TestLogin1 must have permissions: SELECT on the table and EXECUTE on the XML schema collection.  
SETUSER  
GO  
GRANT SELECT TO TestLogin1  
GO  
-- TestLogin1 already has EXECUTE permission on the schema (granted before inserting a record in the table).  
SELECT xmlCol.query('declare default element namespace "http://schemas.adventure-works.com/Additional/ContactInfo" /telephone[1]')  
FROM MyTestTable  
GO  
-- To show that the user must have EXECUTE permission to query, revoke the  
-- previously granted permission and return the query.  
SETUSER  
GO  
REVOKE EXECUTE ON XML SCHEMA COLLECTION::myTestSchemaCollection to TestLogin1  
Go  
-- Now TestLogin1 cannot execute the query.  
SETUSER 'TestLogin1'  
GO  
SELECT xmlCol.query('declare default element namespace "http://schemas.adventure-works.com/Additional/ContactInfo" /telephone[1]')  
FROM MyTestTable  
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
  
### <a name="c-granting-alter-permission-on-an-xml-schema-collection"></a><span data-ttu-id="ea011-149">C.</span><span class="sxs-lookup"><span data-stu-id="ea011-149">C.</span></span> <span data-ttu-id="ea011-150">Concedendo permissão ALTER em uma coleção de esquema XML</span><span class="sxs-lookup"><span data-stu-id="ea011-150">Granting ALTER permission on an XML schema collection</span></span>  
 <span data-ttu-id="ea011-151">Um usuário precisa ter a permissão ALTER para modificar uma coleção de esquema XML existente no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="ea011-151">A user must have ALTER permission to modify an existing XML schema collection in the database.</span></span> <span data-ttu-id="ea011-152">O exemplo a seguir mostra como conceder a permissão `ALTER` .</span><span class="sxs-lookup"><span data-stu-id="ea011-152">The following example shows how to grant `ALTER` permission.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
CREATE LOGIN TestLogin1 WITH password='SQLSvrPwd1'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
CREATE USER TestLogin1  
GO  
-- Grant permission to the user.  
SETUSER  
GO  
-- User must have ALTER permission on the relational schema in the database.  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- User also must have permission to create XML schema collections in the database.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
-- Now user can execute the previous CREATE XML SCHEMA COLLECTION statement.  
SETUSER 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
  <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"    
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
  </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
-- Grant ALTER permission to TestLogin1.  
setuser  
GO  
GRANT ALTER ON XML SCHEMA COLLECTION::myTestSchemaCollection TO TestLogin1  
GO  
-- TestLogin1 should be able to add components to the collection.  
SETUSER 'TestLogin1'  
GO  
ALTER XML SCHEMA COLLECTION myTestSchemaCollection ADD '  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
            xmlns="http://schemas.adventure-works.com/Additional/ContactInfo"   
elementFormDefault="qualified">  
 <xsd:element name="pager" type="xsd:string"/>  
</xsd:schema>  
'  
Go  
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
  
### <a name="d-granting-take-ownership-permission-on-an-xml-schema-collection"></a><span data-ttu-id="ea011-153">D.</span><span class="sxs-lookup"><span data-stu-id="ea011-153">D.</span></span> <span data-ttu-id="ea011-154">Concedendo a permissão TAKE OWNERSHIP em uma coleção de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="ea011-154">Granting TAKE OWNERSHIP permission on an XML schema collection</span></span>  
 <span data-ttu-id="ea011-155">O exemplo a seguir mostra como transferir a propriedade do esquema XML de um usuário para outro.</span><span class="sxs-lookup"><span data-stu-id="ea011-155">The following example shows how to transfer XML schema ownership from one user to another.</span></span> <span data-ttu-id="ea011-156">Para tornar o exemplo mais interessante, os usuários neste trabalho de exemplo trabalham em diferentes esquemas relacionais padrão.</span><span class="sxs-lookup"><span data-stu-id="ea011-156">To make the example more interesting, the users in this example work in different default relational schemas.</span></span>  
  
 <span data-ttu-id="ea011-157">Este exemplo faz o seguinte:</span><span class="sxs-lookup"><span data-stu-id="ea011-157">This example does the following:</span></span>  
  
-   <span data-ttu-id="ea011-158">Cria um banco de dados com dois esquemas relacionais ( `dbo` e `myOtherDBSchema`).</span><span class="sxs-lookup"><span data-stu-id="ea011-158">Creates a database with two relational schemas, `dbo` and `myOtherDBSchema`).</span></span>  
  
-   <span data-ttu-id="ea011-159">Cria dois usuários, `TestLogin1` e `TestLogin2`.</span><span class="sxs-lookup"><span data-stu-id="ea011-159">Creates two users, `TestLogin1` and `TestLogin2`.</span></span> <span data-ttu-id="ea011-160">`TestLogin2` se torna o proprietário do esquema relacional `myOtherDBSchema` .</span><span class="sxs-lookup"><span data-stu-id="ea011-160">`TestLogin2` is made the owner of the `myOtherDBSchema` relational schema.</span></span>  
  
-   <span data-ttu-id="ea011-161">`TestLogin1` cria uma coleção de esquemas XML no esquema relacional `dbo` .</span><span class="sxs-lookup"><span data-stu-id="ea011-161">`TestLogin1` creates an XML schema collection in the `dbo` relational schema.</span></span>  
  
-   <span data-ttu-id="ea011-162">`TestLogin1` concede a permissão `TAKE OWNERSHIP` na coleção de esquemas XML para `TestLogin2`.</span><span class="sxs-lookup"><span data-stu-id="ea011-162">`TestLogin1` then gives `TAKE OWNERSHIP` permission on the XML schema collection to `TestLogin2`.</span></span>  
  
-   <span data-ttu-id="ea011-163">`TestLogin2` se torna o proprietário da coleção de esquemas XML no `myOtherDBSchema`, sem alterar o esquema relacional da coleção de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="ea011-163">`TestLogin2` becomes the owner of the XML schema collection in `myOtherDBSchema`, without changing the relational schema of the XML schema collection.</span></span>  
  
```  
CREATE LOGIN TestLogin1 with password='SQLSvrPwd1'  
GO  
CREATE LOGIN TestLogin2 with password='SQLSvrPwd2'  
GO  
CREATE DATABASE SampleDBForSchemaPermissions  
GO  
USE SampleDBForSchemaPermissions  
GO  
-- Create another relational schema in the database.  
CREATE SCHEMA myOtherDBSchema  
GO  
-- Create users in the database. Note TestLogin2's default schema is  
-- myOtherDBSchema.  
CREATE USER TestLogin1  
GO  
CREATE USER TestLogin2 WITH DEFAULT_SCHEMA=myOtherDBSchema  
GO  
-- TestLogin2 will own myOtherDBSchema relational schema.  
ALTER AUTHORIZATION ON SCHEMA::myOtherDBSchema TO TestLogin2  
GO  
  
-- For TestLogin1 to create XML schema collection, the following  
-- permission is required.  
GRANT CREATE XML SCHEMA COLLECTION   
TO TestLogin1  
GO  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
GO  
-- Now TestLogin1 can create an XML schema collection.  
setuser 'TestLogin1'  
GO  
CREATE XML SCHEMA COLLECTION myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
  
<xsd:element name="AdditionalContactInfo" >  
 <xsd:complexType mixed="true" >  
    <xsd:sequence>  
      <xsd:any processContents="strict"   
               namespace="http://schemas.adventure-works.com/Contact/Record   
                          http://schemas.adventure-works.com/AdditionalContactTypes"  
               minOccurs="0" maxOccurs="unbounded" />  
    </xsd:sequence>  
 </xsd:complexType>  
</xsd:element>  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
GO  
  
-- Grant TAKE OWNERSHIP to TestLogin2.  
SETUSER  
GO  
GRANT TAKE OWNERSHIP ON XML SCHEMA COLLECTION::dbo.myTestSchemaCollection   
TO TestLogin2  
GO  
-- Verify the owner. Note the UserName and Principal_id is null.   
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
       sys.schemas.name as RelSchemaName,*   
FROM   sys.xml_schema_collections   
      JOIN sys.schemas   
      ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
-- TestLogin2 can take ownership now.  
setuser 'TestLogin2'  
GO  
ALTER AUTHORIZATION ON XML SCHEMA COLLECTION::dbo.myTestSchemaCollection   
TO TestLogin2  
GO  
-- Note that although TestLogin2 is the owner,the XML schema collection   
-- is still in dbo.  
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
      sys.schemas.name as RelSchemaName,*   
FROM sys.xml_schema_collections JOIN sys.schemas   
     ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
  
-- TestLogin2 moves the collection from dbo to myOtherDBSchema relational schema.  
-- TestLogin2 already has all necessary permissions.  
-- 1) TestLogin2 owns the destination relational schema so he can alter it.  
-- 2) TestLogin2 owns the XML schema collection (therefore, has CONTROL permission).  
ALTER SCHEMA myOtherDBSchema  
TRANSFER XML SCHEMA COLLECTION::dbo.myTestSchemaCollection  
GO  
  
SELECT user_name(sys.xml_schema_collections.principal_id) as UserName,   
       sys.schemas.name as RelSchemaName,*   
FROM   sys.xml_schema_collections JOIN sys.schemas   
       ON sys.schemas.schema_id=sys.xml_schema_collections.schema_id  
GO  
-- Final cleanup   
SETUSER  
GO  
USE master  
GO  
DROP DATABASE SampleDBForSchemaPermissions  
GO  
DROP LOGIN TestLogin1  
DROP LOGIN TestLogin2  
go   
```  
  
### <a name="e-granting-view-definition-permission-on-an-xml-schema-collection"></a><span data-ttu-id="ea011-164">E.</span><span class="sxs-lookup"><span data-stu-id="ea011-164">E.</span></span> <span data-ttu-id="ea011-165">Concedendo permissão VIEW DEFINITION em uma coleção de esquema XML</span><span class="sxs-lookup"><span data-stu-id="ea011-165">Granting VIEW DEFINITION permission on an XML schema collection</span></span>  
 <span data-ttu-id="ea011-166">Este exemplo mostra como conceder permissões VIEW DEFINITION para uma coleção de esquema XML:</span><span class="sxs-lookup"><span data-stu-id="ea011-166">The following example shows how to grant VIEW DEFINITION permissions for an XML schema collection.</span></span>  
  
```  
SETUSER  
GO  
USE master  
GO  
IF EXISTS( SELECT * FROM sysdatabases WHERE name='permissionsDB' )  
   DROP DATABASE permissionsDB  
GO  
IF EXISTS( SELECT * FROM sys.sql_logins WHERE name='schemaUser' )  
   DROP LOGIN schemaUser  
GO  
CREATE DATABASE permissionsDB  
GO  
CREATE LOGIN schemaUser WITH PASSWORD='Pass#123',DEFAULT_DATABASE=permissionsDB  
GO  
GRANT CONNECT SQL TO schemaUser  
GO  
USE permissionsDB  
GO  
CREATE USER schemaUser WITH DEFAULT_SCHEMA=dbo  
GO  
CREATE XML SCHEMA COLLECTION MySC AS '  
<schema xmlns="http://www.w3.org/2001/XMLSchema" targetNamespace="http://ns"  
xmlns:ns="http://ns">  
  
   <simpleType name="ListOfIntegers">  
      <list itemType="integer"/>  
   </simpleType>  
  
   <element name="root" type="ns:ListOfIntegers"/>  
  
   <element name="gRoot" type="gMonth"/>  
  
</schema>  
'  
GO  
-- schemaUser cannot see the contents of the collection.  
SETUSER 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
  
-- Grant schemaUser VIEW DEFINITION and REFERENCES permissions  
-- on the XML schema collection.  
SETUSER  
GO  
GRANT VIEW DEFINITION ON XML SCHEMA COLLECTION::dbo.MySC TO schemaUser  
GO  
GRANT REFERENCES ON XML SCHEMA COLLECTION::dbo.MySC TO schemaUser  
GO  
-- Now schemaUser can see the content of the collection.  
SETUSER 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
-- Revoke schemaUser VIEW DEFINITION permissions  
-- on the XML schema collection.  
SETUSER  
GO  
REVOKE VIEW DEFINITION ON XML SCHEMA COLLECTION::dbo.MySC FROM schemaUser  
GO  
-- Now schemaUser cannot see the contents of   
-- the collection.  
setuser 'schemaUser'  
GO  
SELECT XML_SCHEMA_NAMESPACE(N'dbo',N'MySC')  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="ea011-167">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="ea011-167">See Also</span></span>  
 <span data-ttu-id="ea011-168">[Dados XML &#40;SQL Server&#41;](xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ea011-168">[XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) </span></span>  
 <span data-ttu-id="ea011-169">[Comparar XML digitado com XML não digitado](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="ea011-169">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="ea011-170">[Coleções de esquemas XML &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="ea011-170">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 [<span data-ttu-id="ea011-171">Requisitos e limitações para o uso de Coleções de Esquemas XML no servidor</span><span class="sxs-lookup"><span data-stu-id="ea011-171">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
