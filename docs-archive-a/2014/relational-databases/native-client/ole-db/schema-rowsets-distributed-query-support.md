---
title: Suporte à consulta distribuída no conjunto de linhas do esquema | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- DBPROPSET_SQLSERVERSESSION property
- schema rowsets [OLE DB]
- distributed queries [SQL Server], SQL Server Native Client OLE DB provider
- OLE DB, schema rowsets
- OLE DB rowsets, schema
- rowsets [OLE DB], schema
ms.assetid: 11354bb6-be42-4d8d-854c-42dd3dc38656
author: rothja
ms.author: jroth
ms.openlocfilehash: 48b57bbf40590f8ad5c049268f25fe66d2f94357
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570656"
---
# <a name="distributed-query-support-in-schema-rowsets"></a><span data-ttu-id="774f3-102">Suporte à consulta distribuída no conjunto de linhas do esquema</span><span class="sxs-lookup"><span data-stu-id="774f3-102">Distributed Query Support in Schema Rowsets</span></span>
  <span data-ttu-id="774f3-103">Para dar suporte [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a consultas distribuídas, a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] interface **IDBSchemaRowset** do provedor de OLE DB de cliente nativo retorna metadados em servidores vinculados.</span><span class="sxs-lookup"><span data-stu-id="774f3-103">To support [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] distributed queries, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider **IDBSchemaRowset** interface returns metadata on linked servers.</span></span>  
  
 <span data-ttu-id="774f3-104">Caso a propriedade SSPROP_QUOTEDCATALOGNAMES de DBPROPSET_SQLSERVERSESSION seja VARIANT_TRUE, um identificador citado pode ser especificado para o nome do catálogo (por exemplo "my.catalog").</span><span class="sxs-lookup"><span data-stu-id="774f3-104">If the DBPROPSET_SQLSERVERSESSION property SSPROP_QUOTEDCATALOGNAMES is VARIANT_TRUE, a quoted identifier can be specified for the catalog name (for example "my.catalog").</span></span> <span data-ttu-id="774f3-105">Ao restringir a saída do conjunto de linhas de esquema por catálogo, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo reconhece um nome de duas partes que contém o servidor vinculado e o nome do catálogo.</span><span class="sxs-lookup"><span data-stu-id="774f3-105">When restricting schema rowset output by catalog, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider recognizes a two-part name containing the linked server and catalog name.</span></span> <span data-ttu-id="774f3-106">Para os conjuntos de linhas de esquema na tabela a seguir, especificando um nome de catálogo de duas partes como _linked_server_**.** o _Catálogo_ restringe a saída para o catálogo aplicável do servidor vinculado nomeado.</span><span class="sxs-lookup"><span data-stu-id="774f3-106">For the schema rowsets in the table below, specifying a two-part catalog name as _linked_server_**.**_catalog_ restricts output to the applicable catalog of the named linked server.</span></span>  
  
|<span data-ttu-id="774f3-107">Conjunto de linhas de esquema</span><span class="sxs-lookup"><span data-stu-id="774f3-107">Schema rowset</span></span>|<span data-ttu-id="774f3-108">Restrição de catálogo</span><span class="sxs-lookup"><span data-stu-id="774f3-108">Catalog restriction</span></span>|  
|-------------------|-------------------------|  
|<span data-ttu-id="774f3-109">DBSCHEMA_CATALOGS</span><span class="sxs-lookup"><span data-stu-id="774f3-109">DBSCHEMA_CATALOGS</span></span>|<span data-ttu-id="774f3-110">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="774f3-110">CATALOG_NAME</span></span>|  
|<span data-ttu-id="774f3-111">DBSCHEMA_COLUMNS</span><span class="sxs-lookup"><span data-stu-id="774f3-111">DBSCHEMA_COLUMNS</span></span>|<span data-ttu-id="774f3-112">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="774f3-112">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="774f3-113">DBSCHEMA_PRIMARY_KEYS</span><span class="sxs-lookup"><span data-stu-id="774f3-113">DBSCHEMA_PRIMARY_KEYS</span></span>|<span data-ttu-id="774f3-114">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="774f3-114">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="774f3-115">DBSCHEMA_TABLES</span><span class="sxs-lookup"><span data-stu-id="774f3-115">DBSCHEMA_TABLES</span></span>|<span data-ttu-id="774f3-116">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="774f3-116">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="774f3-117">DBSCHEMA_FOREIGN_KEYS</span><span class="sxs-lookup"><span data-stu-id="774f3-117">DBSCHEMA_FOREIGN_KEYS</span></span>|<span data-ttu-id="774f3-118">PK_TABLE_CATALOG FK_TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="774f3-118">PK_TABLE_CATALOG FK_TABLE_CATALOG</span></span>|  
|<span data-ttu-id="774f3-119">DBSCHEMA_INDEXES</span><span class="sxs-lookup"><span data-stu-id="774f3-119">DBSCHEMA_INDEXES</span></span>|<span data-ttu-id="774f3-120">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="774f3-120">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="774f3-121">DBSCHEMA_COLUMN_PRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="774f3-121">DBSCHEMA_COLUMN_PRIVILEGES</span></span>|<span data-ttu-id="774f3-122">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="774f3-122">TABLE_CATALOG</span></span>|  
|<span data-ttu-id="774f3-123">DBSCHEMA_TABLE_PRIVILEGES</span><span class="sxs-lookup"><span data-stu-id="774f3-123">DBSCHEMA_TABLE_PRIVILEGES</span></span>|<span data-ttu-id="774f3-124">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="774f3-124">TABLE_CATALOG</span></span>|  
  
> [!NOTE]  
>  <span data-ttu-id="774f3-125">Para restringir um conjunto de linhas do esquema a todos os catálogos de um servidor vinculado, use a sintaxe *linked_server* (em que o separador do período faz parte da especificação do nome).</span><span class="sxs-lookup"><span data-stu-id="774f3-125">To restrict a schema rowset to all catalogs from a linked server, use the syntax *linked_server* (where the period separator is part of the name specification).</span></span> <span data-ttu-id="774f3-126">Essa sintaxe é equivalente a especificar NULL para a restrição do nome do catálogo, além de ser usada quando o servidor vinculado indica uma fonte de dados que não oferece suporte a catálogos.</span><span class="sxs-lookup"><span data-stu-id="774f3-126">This syntax is equivalent to specifying NULL for the catalog name restriction and is also used when the linked server indicates a data source that does not support catalogs.</span></span>  
  
 <span data-ttu-id="774f3-127">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo define o conjunto de linhas de esquema LinkedServers, retornando uma lista de OLE DB fontes de dados registradas como servidores vinculados.</span><span class="sxs-lookup"><span data-stu-id="774f3-127">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider defines the schema rowset LINKEDSERVERS, returning a list of OLE DB data sources registered as linked servers.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="774f3-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="774f3-128">See Also</span></span>  
 <span data-ttu-id="774f3-129">[Suporte a conjunto de linhas de esquema &#40;OLE DB&#41;](schema-rowset-support-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="774f3-129">[Schema Rowset Support &#40;OLE DB&#41;](schema-rowset-support-ole-db.md) </span></span>  
 [<span data-ttu-id="774f3-130">Conjunto de linhas LINKEDSERVERS &#40;OLE DB&#41;</span><span class="sxs-lookup"><span data-stu-id="774f3-130">LINKEDSERVERS Rowset &#40;OLE DB&#41;</span></span>](schema-rowsets-linkedservers-rowset.md)  
  
  
