---
title: Exibir uma coleção de esquema XML armazenada | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: xml
ms.topic: conceptual
helpviewer_keywords:
- schema collections [SQL Server], viewing
- XML schemas [SQL Server], viewing
- CREATE XML SCHEMA COLLECTION statement
- xml_schema_namespace function
- XML schema collections [SQL Server], viewing
- displaying XML schema collections
- viewing XML schema collections
ms.assetid: e38031af-22df-4cd9-a14e-e316b822f91b
author: rothja
ms.author: jroth
ms.openlocfilehash: 6383fb17183a991d2f83325044663cc9671e9442
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570552"
---
# <a name="view-a-stored-xml-schema-collection"></a><span data-ttu-id="6e118-102">Exibir uma coleção de esquema XML armazenada</span><span class="sxs-lookup"><span data-stu-id="6e118-102">View a Stored XML Schema Collection</span></span>
  <span data-ttu-id="6e118-103">Depois de você importar uma coleção de esquema XML usando [CREATE XML SCHEMA COLLECTION](/sql/t-sql/statements/create-xml-schema-collection-transact-sql), os componentes do esquema são armazenados nos metadados.</span><span class="sxs-lookup"><span data-stu-id="6e118-103">After you import an XML schema collection by using [CREATE XML SCHEMA COLLECTION](/sql/t-sql/statements/create-xml-schema-collection-transact-sql), the schema components are stored in the metadata.</span></span> <span data-ttu-id="6e118-104">É possível usar a função intrínseca [xml_schema_namespace](/sql/t-sql/xml/xml-schema-namespace)para reconstruir a coleção de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="6e118-104">You can use the [xml_schema_namespace](/sql/t-sql/xml/xml-schema-namespace)intrinsic function to reconstruct the XML schema collection.</span></span> <span data-ttu-id="6e118-105">Essa função retorna uma instância de tipo de dados `xml`.</span><span class="sxs-lookup"><span data-stu-id="6e118-105">This function returns an `xml` data type instance.</span></span>  
  
 <span data-ttu-id="6e118-106">Por exemplo, a consulta a seguir recupera uma coleção de esquema XML (`ProductDescriptionSchemaCollection`) do esquema relacional de produção no banco de dados [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="6e118-106">For example, the following query retrieves an XML schema collection (`ProductDescriptionSchemaCollection`) from the production relational schema in the [!INCLUDE[ssSampleDBobject](../../includes/sssampledbobject-md.md)] database.</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection')  
GO  
```  
  
 <span data-ttu-id="6e118-107">Para ver apenas um esquema da coleção de esquema XML, é possível especificar XQuery em relação ao resultado do tipo `xml` que é retornado pelo `xml_schema_namespace`.</span><span class="sxs-lookup"><span data-stu-id="6e118-107">If you want to see only one schema from the XML schema collection, you can specify XQuery against the `xml` type result that is returned by `xml_schema_namespace`.</span></span>  
  
```  
SELECT xml_schema_namespace(N'RelationalSchemaName',N'XmlSchemaCollectionName').query('  
/xs:schema[@targetNamespace="TargetNameSpace"]  
')  
GO  
```  
  
 <span data-ttu-id="6e118-108">Por exemplo, a consulta a seguir recupera informações do esquema XML sobre garantia e manutenção do produto da coleção de esquema XML `ProductDescriptionSchemaCollection` .</span><span class="sxs-lookup"><span data-stu-id="6e118-108">For example, the following query retrieves product warranty and maintenance XML schema information from the `ProductDescriptionSchemaCollection` XML schema collection.</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection').query('  
/xs:schema[@targetNamespace="https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain"]  
')  
GO  
```  
  
 <span data-ttu-id="6e118-109">Também é possível passar o namespace opcional de destino como o terceiro parâmetro para a função `xml_schema_namespace` para recuperar esquema específico da coleção, conforme mostrado na consulta a seguir:</span><span class="sxs-lookup"><span data-stu-id="6e118-109">You can also pass the optional target namespace as the third parameter to the `xml_schema_namespace` function to retrieve specific schema from the collection, as shown in the following query:</span></span>  
  
```  
SELECT xml_schema_namespace(N'Production',N'ProductDescriptionSchemaCollection', N'https://schemas.microsoft.com/sqlserver/2004/07/adventure-works/ProductModelWarrAndMain')  
GO  
```  
  
 <span data-ttu-id="6e118-110">Quando você cria uma coleção de esquema XML usando CREATE XML SCHEMA COLLECTION no banco de dados, a instrução armazena os componentes do esquema nos metadados.</span><span class="sxs-lookup"><span data-stu-id="6e118-110">When you create an XML schema collection by using CREATE XML SCHEMA COLLECTION in the database, the statement stores the schema components in the metadata.</span></span> <span data-ttu-id="6e118-111">Observe que apenas os componentes de esquema que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] entende são armazenados.</span><span class="sxs-lookup"><span data-stu-id="6e118-111">Note that only the schema components that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] understands are stored.</span></span> <span data-ttu-id="6e118-112">Todos os comentários, anotações ou atributos não XSD não são armazenados.</span><span class="sxs-lookup"><span data-stu-id="6e118-112">Any comments, annotations, or non-XSD attributes are not stored.</span></span> <span data-ttu-id="6e118-113">Portanto o esquema reconstruído pelo **xml_schema_namespace** é funcionalmente equivalente ao esquema original, mas não necessariamente terá a mesma aparência.</span><span class="sxs-lookup"><span data-stu-id="6e118-113">Therefore, the schema reconstructed by **xml_schema_namespace** is functionally equivalent to the original schema, but it will not necessarily look the same.</span></span> <span data-ttu-id="6e118-114">Por exemplo, você não verá os mesmos prefixos que existiam no esquema original.</span><span class="sxs-lookup"><span data-stu-id="6e118-114">For example, you will not see the same prefixes you had in the original schema.</span></span> <span data-ttu-id="6e118-115">O esquema retornado pelo **xml_schema_namespace** usa **t** como o prefixo do namespace de destino e **ns1**, **ns2**e assim por diante, para outros namespaces.</span><span class="sxs-lookup"><span data-stu-id="6e118-115">The schema returned by **xml_schema_namespace** uses **t** as the prefix for the target namespace and **ns1**, **ns2**, and so on, for other namespaces.</span></span>  
  
 <span data-ttu-id="6e118-116">Para manter uma cópia idêntica dos esquemas XML, você deve salvar o esquema XML em um arquivo ou em uma tabela do banco de dados em uma coluna de tipo `xml`.</span><span class="sxs-lookup"><span data-stu-id="6e118-116">If you want to retain an identical copy of the XML schemas, you should save your XML schema in a file or in a database table in an `xml` type column.</span></span>  
  
 <span data-ttu-id="6e118-117">A exibição de catálogo [sys.xml_schema_collections](/sql/relational-databases/system-catalog-views/sys-xml-schema-collections-transact-sql) também retorna informações sobre coleções de esquemas XML.</span><span class="sxs-lookup"><span data-stu-id="6e118-117">The [sys.xml_schema_collections](/sql/relational-databases/system-catalog-views/sys-xml-schema-collections-transact-sql) catalog view also returns information about XML schema collections.</span></span> <span data-ttu-id="6e118-118">Essas informações incluem o nome da coleção, a data de criação e o proprietário da coleção.</span><span class="sxs-lookup"><span data-stu-id="6e118-118">This information includes the name of the collection, the creation date, and the owner of the collection.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6e118-119">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6e118-119">See Also</span></span>  
 [<span data-ttu-id="6e118-120">Coleções de esquemas XML &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="6e118-120">XML Schema Collections &#40;SQL Server&#41;</span></span>](xml-schema-collections-sql-server.md)  
  
  
