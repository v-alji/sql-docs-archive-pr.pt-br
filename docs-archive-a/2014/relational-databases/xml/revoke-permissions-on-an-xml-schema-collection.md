---
title: Revogar permissões em uma coleção de esquemas XML | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- revoking permissions [SQL Server]
ms.assetid: 4e542b70-2d56-4a65-8a39-96a1ed477ca6
author: rothja
ms.author: jroth
ms.openlocfilehash: 3ab37c915f14207376e0c4a9582611bf8e65e0d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679730"
---
# <a name="revoke-permissions-on-an-xml-schema-collection"></a><span data-ttu-id="055f7-102">Revogar permissões em uma coleção de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="055f7-102">Revoke Permissions on an XML Schema Collection</span></span>
  <span data-ttu-id="055f7-103">A permissão para criar uma coleção de esquema XML pode ser revogada usando uma das seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="055f7-103">The permission to create an XML schema collection can be revoked by using one of the following:</span></span>  
  
-   <span data-ttu-id="055f7-104">Revogar a permissão ALTER para o esquema relacional.</span><span class="sxs-lookup"><span data-stu-id="055f7-104">Revoke the ALTER permission for the relational schema.</span></span> <span data-ttu-id="055f7-105">Em seguida, a entidade de segurança não pode criar uma coleção de esquema XML no esquema relacional.</span><span class="sxs-lookup"><span data-stu-id="055f7-105">Then, the principal cannot create an XML schema collection in the relational schema.</span></span> <span data-ttu-id="055f7-106">Porém a entidade de segurança ainda pode fazer isso em outros esquemas relacionais no mesmo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="055f7-106">However, the principal can still do so in other relational schemas in the same database.</span></span>  
  
-   <span data-ttu-id="055f7-107">Revogar a permissão ALTER ANY SCHEMA no banco de dados para a entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="055f7-107">Revoke the ALTER ANY SCHEMA permission on the database for the principal.</span></span> <span data-ttu-id="055f7-108">Em seguida, a entidade de segurança não pode criar uma coleção de esquema XML em nenhum outro lugar no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="055f7-108">Then, the principal cannot create an XML schema collection anywhere in the database.</span></span>  
  
-   <span data-ttu-id="055f7-109">Revogar a permissão CREATE XML SCHEMA COLLECTION ou ALTER XML SCHEMA COLLECTION no banco de dados para a entidade de segurança.</span><span class="sxs-lookup"><span data-stu-id="055f7-109">Revoke the CREATE XML SCHEMA COLLECTION or ALTER XML SCHEMA COLLECTION permission on the database for the principal.</span></span> <span data-ttu-id="055f7-110">Isto impede que a entidade de segurança importe uma coleção de esquema XML dentro do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="055f7-110">This prevents the principal from importing an XML schema collection within the database.</span></span> <span data-ttu-id="055f7-111">O mesmo efeito é obtido com a revogação da permissão ALTER ou CONTROL no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="055f7-111">Revoking the ALTER or CONTROL permission on the database has the same effect.</span></span>  
  
## <a name="revoking-permissions-on-an-existing-xml-schema-collection-object"></a><span data-ttu-id="055f7-112">Revogando permissões em um objeto de coleção de esquema XML existente</span><span class="sxs-lookup"><span data-stu-id="055f7-112">Revoking Permissions on an Existing XML Schema Collection Object</span></span>  
 <span data-ttu-id="055f7-113">A lista a seguir apresenta as permissões que podem ser revogadas em uma coleção de esquema XML e seus resultados:</span><span class="sxs-lookup"><span data-stu-id="055f7-113">Following are the permissions that can be revoked on an XML schema collection and the results:</span></span>  
  
-   <span data-ttu-id="055f7-114">A revogação da permissão ALTER revoga a capacidade de uma entidade de segurança de modificar o conteúdo da coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="055f7-114">Revoking the ALTER permission revokes a principal's ability to modify the content of the XML schema collection.</span></span>  
  
-   <span data-ttu-id="055f7-115">A revogação da permissão TAKE OWNERSHIP revoga a capacidade da entidade de segurança de transferir a propriedade da coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="055f7-115">Revoking the TAKE OWNERSHIP permission revokes a principal's ability to transfer ownership of the XML schema collection.</span></span>  
  
-   <span data-ttu-id="055f7-116">A revogação da permissão REFERENCES revoga a capacidade da entidade de segurança de usar a coleção de esquema XML para digitar ou restringir colunas de tipo xml em tabelas, exibições e parâmetros.</span><span class="sxs-lookup"><span data-stu-id="055f7-116">Revoking the REFERENCES permission revokes a principal's ability to use the XML schema collection for typing or constraining xml type columns, in tables and views, and parameters.</span></span> <span data-ttu-id="055f7-117">Ela também revoga a permissão para fazer referência a esta coleção de esquema a partir de outras coleções de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="055f7-117">It also revokes the permission to refer to this schema collection from other XML schema collections.</span></span>  
  
-   <span data-ttu-id="055f7-118">A revogação da permissão VIEW DEFINITION revoga a capacidade da entidade de segurança de exibir o conteúdo de uma coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="055f7-118">Revoking the VIEW DEFINITION permission revokes a principal's ability to view the contents of an XML schema collection.</span></span>  
  
-   <span data-ttu-id="055f7-119">A revogação da permissão EXECUTE revoga a capacidade da entidade de segurança de inserir ou atualizar valores em colunas, variáveis e parâmetros que são de tipo ou restringidas pela coleção XML.</span><span class="sxs-lookup"><span data-stu-id="055f7-119">Revoking the EXECUTE permission revokes a principal's ability to insert or update values in columns, variables, and parameters that are typed or constrained by the XML collection.</span></span> <span data-ttu-id="055f7-120">Ela também revoga a capacidade de consultar essas colunas, variáveis ou parâmetros de tipo **xml** .</span><span class="sxs-lookup"><span data-stu-id="055f7-120">It also revokes the ability to query such **xml** type columns, variables, or parameters.</span></span>  
  
## <a name="examples"></a><span data-ttu-id="055f7-121">Exemplos</span><span class="sxs-lookup"><span data-stu-id="055f7-121">Examples</span></span>  
 <span data-ttu-id="055f7-122">Os cenários nos exemplos seguintes ilustram como as permissões de esquema XML funcionam.</span><span class="sxs-lookup"><span data-stu-id="055f7-122">The scenarios in the following examples illustrate how XML schema permissions work.</span></span> <span data-ttu-id="055f7-123">Cada exemplo cria o banco de dados, os esquemas relacionais e os logons de teste necessários.</span><span class="sxs-lookup"><span data-stu-id="055f7-123">Each example creates the necessary test database, relational schemas, and logins.</span></span> <span data-ttu-id="055f7-124">Esses logons recebem as permissões necessárias na coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="055f7-124">These logins are granted the necessary XML schema collection permissions.</span></span> <span data-ttu-id="055f7-125">Cada exemplo faz a limpeza necessária no final.</span><span class="sxs-lookup"><span data-stu-id="055f7-125">Each example does the necessary cleanup at the end.</span></span>  
  
### <a name="a-revoking-permissions-to-create-an-xml-schema-collection"></a><span data-ttu-id="055f7-126">a.</span><span class="sxs-lookup"><span data-stu-id="055f7-126">A.</span></span> <span data-ttu-id="055f7-127">Revogando permissões para criar uma coleção de esquemas XML</span><span class="sxs-lookup"><span data-stu-id="055f7-127">Revoking permissions to create an XML schema collection</span></span>  
 <span data-ttu-id="055f7-128">Este exemplo cria um logon e um banco de dados de exemplo.</span><span class="sxs-lookup"><span data-stu-id="055f7-128">This example creates a login and a sample database.</span></span> <span data-ttu-id="055f7-129">Ele também adiciona um esquema relacional no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="055f7-129">It also adds a relational schema in the database.</span></span> <span data-ttu-id="055f7-130">Inicialmente, o logon recebe permissão ALTER nos dois esquemas relacionais e outras permissões necessárias para criar coleções de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="055f7-130">Initially, the login is granted ALTER permission on both relational schemas and other necessary permissions to create XML schema collections.</span></span> <span data-ttu-id="055f7-131">Em seguida, o exemplo revoga a permissão ALTER em um dos esquemas relacionais do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="055f7-131">The example then revokes the ALTER permission on one of the relational schemas in the database.</span></span> <span data-ttu-id="055f7-132">Isso impede que o logon crie uma coleção de esquema XML.</span><span class="sxs-lookup"><span data-stu-id="055f7-132">This prevents the login from creating an XML schema collection.</span></span>  
  
```  
setuser  
go  
create login TestLogin1 with password='SQLSvrPwd1'  
go  
create database SampleDBForSchemaPermissions  
go  
use SampleDBForSchemaPermissions  
go  
-- Create another relational schema in the db (in addition to dbo schema)  
CREATE SCHEMA myOtherDBSchema  
go  
CREATE USER TestLogin1  
go  
-- For TestLogin1 to create/import XML schema collection, following  
-- permission needed  
-- CREATE XML SCHEMA is a database level permission  
GRANT CREATE XML SCHEMA COLLECTION TO TestLogin1  
go  
GRANT ALTER ON SCHEMA::myOtherDBSchema TO TestLogin1  
go  
GRANT ALTER ON SCHEMA::dbo TO TestLogin1  
go  
-- Now TestLogin1 can import an XML schema collection in both relational schemas.  
setuser 'TestLogin1'  
go  
CREATE XML SCHEMA COLLECTION dbo.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
-- TestLogin1 can create XML schema collection in myOtherDBSchema relational schema  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
-- Let us drop XML schema collections from both relational schemas  
DROP XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection  
go  
DROP XML SCHEMA COLLECTION dbo.myTestSchemaCollection  
go  
-- now REVOKE permission from TestLogin1 to alter myOtherDBSchema  
setuser  
go  
REVOKE ALTER ON SCHEMA::myOtherDBSchema FROM TestLogin1  
go  
-- now TestLogin1 cannot create xml schema collection in myOtherDBSchema  
setuser 'TestLogin1'  
go  
CREATE XML SCHEMA COLLECTION myOtherDBSchema.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
  
-- TestLogin1 can still create XML schema collections in dbo  
-- It cannot create XML schema collections anywhere in the database  
-- if we REVOKE CREATE XML SCHEMA COLLECTION permission  
SETUSER  
go  
REVOKE CREATE XML SCHEMA COLLECTION FROM TestLogin1  
go  
  
setuser 'TestLogin1'  
go  
-- the following now should fail  
CREATE XML SCHEMA COLLECTION dbo.myTestSchemaCollection AS '<?xml version="1.0" encoding="UTF-8" ?>  
<xsd:schema targetNamespace="http://schemas.adventure-works.com/Additional/ContactInfo"   
            xmlns:xsd="http://www.w3.org/2001/XMLSchema"   
elementFormDefault="qualified">  
<xsd:element name="telephone" type="xsd:string" />  
</xsd:schema>'  
go  
  
-- Final cleanup  
SETUSER  
go  
USE master  
go  
DROP DATABASE SampleDBForSchemaPermissions  
go  
DROP LOGIN TestLogin1  
Go  
```  
  
## <a name="see-also"></a><span data-ttu-id="055f7-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="055f7-133">See Also</span></span>  
 <span data-ttu-id="055f7-134">[Dados XML &#40;SQL Server&#41;](xml-data-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="055f7-134">[XML Data &#40;SQL Server&#41;](xml-data-sql-server.md) </span></span>  
 <span data-ttu-id="055f7-135">[Comparar XML digitado com XML não digitado](compare-typed-xml-to-untyped-xml.md) </span><span class="sxs-lookup"><span data-stu-id="055f7-135">[Compare Typed XML to Untyped XML](compare-typed-xml-to-untyped-xml.md) </span></span>  
 <span data-ttu-id="055f7-136">[Coleções de esquemas XML &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="055f7-136">[XML Schema Collections &#40;SQL Server&#41;](xml-schema-collections-sql-server.md) </span></span>  
 [<span data-ttu-id="055f7-137">Requisitos e limitações para o uso de Coleções de Esquemas XML no servidor</span><span class="sxs-lookup"><span data-stu-id="055f7-137">Requirements and Limitations for XML Schema Collections on the Server</span></span>](requirements-and-limitations-for-xml-schema-collections-on-the-server.md)  
  
  
