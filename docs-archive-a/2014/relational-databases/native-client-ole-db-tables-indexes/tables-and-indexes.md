---
title: Tabelas e índices | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- OLE DB, indexes
- OLE DB, tables
- ITableDefinition interface
- tables [OLE DB]
- IIndexDefinition interface
- SQL Server Native Client OLE DB provider, tables
- SQL Server Native Client OLE DB provider, indexes
- indexes [OLE DB]
ms.assetid: 4217c6d8-8cd2-43dc-b36f-3cfd8a58fabc
author: rothja
ms.author: jroth
ms.openlocfilehash: abc7c314e433eb9f107bd191738d951706f1b50d
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575084"
---
# <a name="tables-and-indexes"></a><span data-ttu-id="6a6a1-102">Tabelas e índices</span><span class="sxs-lookup"><span data-stu-id="6a6a1-102">Tables and Indexes</span></span>
  <span data-ttu-id="6a6a1-103">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo expõe as interfaces **IIndexDefinition** e **ITableDefinition** , permitindo que os consumidores criem, alterem e removam [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tabelas e índices.</span><span class="sxs-lookup"><span data-stu-id="6a6a1-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider exposes the **IIndexDefinition** and **ITableDefinition** interfaces, allowing consumers to create, alter, and drop [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] tables and indexes.</span></span> <span data-ttu-id="6a6a1-104">As definições válidas de tabela e de índice dependem da versão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a6a1-104">Valid table and index definitions depend on the version of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6a6a1-105">A capacidade de criar ou descartar tabelas e índices depende dos direitos de acesso do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do usuário do aplicativo de consumidor.</span><span class="sxs-lookup"><span data-stu-id="6a6a1-105">The ability to create or drop tables and indexes depends on the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] access rights of the consumer-application user.</span></span> <span data-ttu-id="6a6a1-106">Descartar uma tabela pode ser uma operação ainda mais restrita pela presença de restrições de integridade referencial declarativas ou outros fatores.</span><span class="sxs-lookup"><span data-stu-id="6a6a1-106">Dropping a table can be further constrained by the presence of declarative referential integrity constraints or other factors.</span></span>  
  
 <span data-ttu-id="6a6a1-107">A maioria dos aplicativos que visam [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usar o SQL-DMO em vez dessas [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] interfaces do provedor de OLE DB do cliente nativo.</span><span class="sxs-lookup"><span data-stu-id="6a6a1-107">Most applications targeting [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] use SQL-DMO instead of these [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client OLE DB provider interfaces.</span></span> <span data-ttu-id="6a6a1-108">SQL-DMO é uma coleção de objetos de automação OLE que dão suporte a todas as funções administrativas do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6a6a1-108">SQL-DMO is a collection of OLE Automation objects that support all the administrative functions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="6a6a1-109">Os aplicativos destinados a vários provedores OLE DB usam essas interfaces OLE DB genéricas suportadas pelos vários provedores OLE DB.</span><span class="sxs-lookup"><span data-stu-id="6a6a1-109">Applications targeting multiple OLE DB providers use these generic OLE DB interfaces that are supported by the various OLE DB providers.</span></span>  
  
 <span data-ttu-id="6a6a1-110">No conjunto de propriedades específico de provedor DBPROPSET_SQLSERVERCOLUMN, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] define a propriedade a seguir.</span><span class="sxs-lookup"><span data-stu-id="6a6a1-110">In the provider-specific property set DBPROPSET_SQLSERVERCOLUMN, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] defines the following property.</span></span>  
  
|<span data-ttu-id="6a6a1-111">ID da propriedade</span><span class="sxs-lookup"><span data-stu-id="6a6a1-111">Property ID</span></span>|<span data-ttu-id="6a6a1-112">Descrição</span><span class="sxs-lookup"><span data-stu-id="6a6a1-112">Description</span></span>|  
|-----------------|-----------------|  
|<span data-ttu-id="6a6a1-113">SSPROP_COL_COLLATIONNAME</span><span class="sxs-lookup"><span data-stu-id="6a6a1-113">SSPROP_COL_COLLATIONNAME</span></span>|<span data-ttu-id="6a6a1-114">Tipo: VT_BSTR</span><span class="sxs-lookup"><span data-stu-id="6a6a1-114">Type: VT_BSTR</span></span><br /><br /> <span data-ttu-id="6a6a1-115">Leitura/gravação: gravação</span><span class="sxs-lookup"><span data-stu-id="6a6a1-115">R/W: Write</span></span><br /><br /> <span data-ttu-id="6a6a1-116">Padrão: Null</span><span class="sxs-lookup"><span data-stu-id="6a6a1-116">Default: Null</span></span><br /><br /> <span data-ttu-id="6a6a1-117">Descrição: essa propriedade só é usada em **ITableDefinition**.</span><span class="sxs-lookup"><span data-stu-id="6a6a1-117">Description: This property is used only in **ITableDefinition**.</span></span> <span data-ttu-id="6a6a1-118">A cadeia de caracteres especificada nesta propriedade é usada ao criar uma instrução [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql)</span><span class="sxs-lookup"><span data-stu-id="6a6a1-118">The string specified in this property is used when creating a [CREATE TABLE](/sql/t-sql/statements/create-table-transact-sql)</span></span><br /><br /> <span data-ttu-id="6a6a1-119">.</span><span class="sxs-lookup"><span data-stu-id="6a6a1-119">statement.</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="6a6a1-120">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="6a6a1-120">In This Section</span></span>  
  
-   [<span data-ttu-id="6a6a1-121">Criando tabelas do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a6a1-121">Creating SQL Server Tables</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/creating-sql-server-tables.md)  
  
-   [<span data-ttu-id="6a6a1-122">Adicionando uma coluna a uma tabela do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a6a1-122">Adding a Column to a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/adding-a-column-to-a-sql-server-table.md)  
  
-   [<span data-ttu-id="6a6a1-123">Removendo uma coluna de uma tabela do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a6a1-123">Removing a Column from a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/removing-a-column-from-a-sql-server-table.md)  
  
-   [<span data-ttu-id="6a6a1-124">Descartando uma tabela do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a6a1-124">Dropping a SQL Server Table</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/dropping-a-sql-server-table.md)  
  
-   [<span data-ttu-id="6a6a1-125">Criando índices do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a6a1-125">Creating SQL Server Indexes</span></span>](../../relational-databases/indexes/indexes.md)  
  
-   [<span data-ttu-id="6a6a1-126">Descartando um índice do SQL Server</span><span class="sxs-lookup"><span data-stu-id="6a6a1-126">Dropping a SQL Server Index</span></span>](../../relational-databases/native-client-ole-db-tables-indexes/dropping-a-sql-server-index.md)  
  
## <a name="see-also"></a><span data-ttu-id="6a6a1-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6a6a1-127">See Also</span></span>  
 <span data-ttu-id="6a6a1-128">[SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md) </span><span class="sxs-lookup"><span data-stu-id="6a6a1-128">[SQL Server Native Client &#40;OLE DB&#41;](../../relational-databases/native-client/ole-db/sql-server-native-client-ole-db.md) </span></span>  
 <span data-ttu-id="6a6a1-129">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6a6a1-129">[DROP TABLE &#40;Transact-SQL&#41;](/sql/t-sql/statements/drop-table-transact-sql) </span></span>  
 <span data-ttu-id="6a6a1-130">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="6a6a1-130">[CREATE INDEX &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-index-transact-sql) </span></span>  
 [<span data-ttu-id="6a6a1-131">DROP INDEX &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="6a6a1-131">DROP INDEX &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/drop-index-transact-sql)  
  
  
