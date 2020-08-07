---
title: Usando funções de catálogo | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC, functions
- SQLLinkedCatalogs function
- SQL Server Native Client ODBC driver, catalog functions
- SQLLinkedServers function
- catalog functions [ODBC]
- functions [ODBC]
ms.assetid: 7773fb2e-06b5-4c4b-88e9-0ad9132ad273
author: rothja
ms.author: jroth
ms.openlocfilehash: 6cac35e658343f606c1953f265c752335c70d81f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582425"
---
# <a name="using-catalog-functions"></a><span data-ttu-id="02c42-102">Usando funções de catálogo</span><span class="sxs-lookup"><span data-stu-id="02c42-102">Using Catalog Functions</span></span>
  <span data-ttu-id="02c42-103">Todos os bancos de dados têm uma estrutura que contém os dados armazenados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="02c42-103">All databases have a structure containing the data stored in the database.</span></span> <span data-ttu-id="02c42-104">Uma definição dessa estrutura, juntamente com outras informações, como permissões, é armazenada em um catálogo (implementado como um conjunto de tabelas do sistema), também conhecido como um dicionário de dados.</span><span class="sxs-lookup"><span data-stu-id="02c42-104">A definition of this structure, along with other information such as permissions, is stored in a catalog (implemented as a set of system tables), also known as a data dictionary.</span></span>  
  
 <span data-ttu-id="02c42-105">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client permite que um aplicativo determine a estrutura do banco de dados por meio de chamadas para funções de catálogo ODBC.</span><span class="sxs-lookup"><span data-stu-id="02c42-105">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver enables an application to determine the database structure through calls to ODBC catalog functions.</span></span> <span data-ttu-id="02c42-106">As funções de catálogo retornam informações em conjuntos de resultados e são implementadas usando procedimentos armazenados de catálogo para consultar as tabelas do sistema no catálogo.</span><span class="sxs-lookup"><span data-stu-id="02c42-106">Catalog functions return information in result sets and are implemented using catalog stored procedures to query the system tables in the catalog.</span></span> <span data-ttu-id="02c42-107">Por exemplo, um aplicativo pode solicitar um conjunto de resultados que contém informações sobre todas as tabelas no sistema ou todas as colunas de uma tabela específica.</span><span class="sxs-lookup"><span data-stu-id="02c42-107">For example, an application might request a result set containing information about all the tables on the system or all the columns in a particular table.</span></span> <span data-ttu-id="02c42-108">As funções de catálogo ODBC padrão são usadas para obter informações de catálogo do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] com o qual o aplicativo está conectado.</span><span class="sxs-lookup"><span data-stu-id="02c42-108">The standard ODBC catalog functions are used to get catalog information from the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to which the application connected.</span></span>  
  
 <span data-ttu-id="02c42-109">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] dá suporte a consultas distribuídas nas quais dados de várias fontes de dados OLE DB heterogêneas são acessadas em uma única consulta.</span><span class="sxs-lookup"><span data-stu-id="02c42-109">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] supports distributed queries in which data from multiple, heterogeneous OLE DB data sources is accessed in a single query.</span></span> <span data-ttu-id="02c42-110">Um dos métodos para acessar uma fonte de dados OLE DB remota é definir a fonte de dados como um servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="02c42-110">One of the methods of accessing a remote OLE DB data source is to define the data source as a linked server.</span></span> <span data-ttu-id="02c42-111">Isso pode ser feito usando [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="02c42-111">This can be done by using [sp_addlinkedserver](/sql/relational-databases/system-stored-procedures/sp-addlinkedserver-transact-sql).</span></span> <span data-ttu-id="02c42-112">Depois que o servidor vinculado foi definido, é possível referenciar objetos nesse servidor em instruções Transact-SQL usando um nome de quatro partes:</span><span class="sxs-lookup"><span data-stu-id="02c42-112">After the linked server has been defined, objects in that server can be referenced in Transact-SQL statements by using a four-part name:</span></span>  
  
 <span data-ttu-id="02c42-113">*linked_server_name. Catalog. Schema. object_name*.</span><span class="sxs-lookup"><span data-stu-id="02c42-113">*linked_server_name.catalog.schema.object_name*.</span></span>  
  
 <span data-ttu-id="02c42-114">O driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client dá suporte a duas funções específicas do driver que ajudam a obter informações de catálogo de servidores vinculados:</span><span class="sxs-lookup"><span data-stu-id="02c42-114">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports two driver-specific functions that help get catalog information from linked servers:</span></span>  
  
-   <span data-ttu-id="02c42-115">**SQLLinkedServers**</span><span class="sxs-lookup"><span data-stu-id="02c42-115">**SQLLinkedServers**</span></span>  
  
     <span data-ttu-id="02c42-116">Retorna uma lista dos servidores vinculados definidos para o servidor local.</span><span class="sxs-lookup"><span data-stu-id="02c42-116">Returns a list of the linked servers defined to the local server.</span></span>  
  
-   <span data-ttu-id="02c42-117">**SQLLinkedCatalogs**</span><span class="sxs-lookup"><span data-stu-id="02c42-117">**SQLLinkedCatalogs**</span></span>  
  
     <span data-ttu-id="02c42-118">Retorna uma lista dos catálogos contidos em um servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="02c42-118">Returns a list of the catalogs contained in a linked server.</span></span>  
  
 <span data-ttu-id="02c42-119">Depois que você tiver um nome de servidor vinculado e um nome de catálogo, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client dará suporte à obtenção de informações do catálogo usando um nome de duas partes de _linked_server_name_**.** _Catálogo_ para *CatalogName* nas seguintes funções de catálogo ODBC:</span><span class="sxs-lookup"><span data-stu-id="02c42-119">After you have a linked server name and a catalog name, the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports getting information from the catalog by using a two-part name of _linked_server_name_**.**_catalog_ for *CatalogName* on the following ODBC catalog functions:</span></span>  
  
-   <span data-ttu-id="02c42-120">**SQLColumnPrivileges**</span><span class="sxs-lookup"><span data-stu-id="02c42-120">**SQLColumnPrivileges**</span></span>  
  
-   <span data-ttu-id="02c42-121">**SQLColumns**</span><span class="sxs-lookup"><span data-stu-id="02c42-121">**SQLColumns**</span></span>  
  
-   <span data-ttu-id="02c42-122">**SQLPrimaryKeys**</span><span class="sxs-lookup"><span data-stu-id="02c42-122">**SQLPrimaryKeys**</span></span>  
  
-   <span data-ttu-id="02c42-123">**SQLStatistics**</span><span class="sxs-lookup"><span data-stu-id="02c42-123">**SQLStatistics**</span></span>  
  
-   <span data-ttu-id="02c42-124">**SQLTablePrivileges**</span><span class="sxs-lookup"><span data-stu-id="02c42-124">**SQLTablePrivileges**</span></span>  
  
-   <span data-ttu-id="02c42-125">**SQLTables**</span><span class="sxs-lookup"><span data-stu-id="02c42-125">**SQLTables**</span></span>  
  
 <span data-ttu-id="02c42-126">A _linked_server_name_de duas partes **.** o _Catálogo_ também tem suporte para *FKCatalogName* e *PKCatalogName* em [SQLForeignKeys](../../native-client-odbc-api/sqlforeignkeys.md).</span><span class="sxs-lookup"><span data-stu-id="02c42-126">The two-part _linked_server_name_**.**_catalog_ is also supported for *FKCatalogName* and *PKCatalogName* on [SQLForeignKeys](../../native-client-odbc-api/sqlforeignkeys.md).</span></span>  
  
 <span data-ttu-id="02c42-127">O uso de SQLLinkedServers e SQLLinkedCatalogs exige os seguintes arquivos:</span><span class="sxs-lookup"><span data-stu-id="02c42-127">Using SQLLinkedServers and SQLLinkedCatalogs requires the following files:</span></span>  
  
-   <span data-ttu-id="02c42-128">sqlncli.h</span><span class="sxs-lookup"><span data-stu-id="02c42-128">sqlncli.h</span></span>  
  
     <span data-ttu-id="02c42-129">Inclui protótipos de função e definições de constantes para funções de catálogo do servidor vinculado.</span><span class="sxs-lookup"><span data-stu-id="02c42-129">Includes function prototypes and constant definitions for the linked server catalog functions.</span></span> <span data-ttu-id="02c42-130">O sqlncli.h deve ser incluído no aplicativo ODBC e deverá estar no caminho de inclusão quando o aplicativo for compilado.</span><span class="sxs-lookup"><span data-stu-id="02c42-130">sqlncli.h must be included in the ODBC application and must be in the include path when the application is compiled.</span></span>  
  
-   <span data-ttu-id="02c42-131">sqlncli11.lib</span><span class="sxs-lookup"><span data-stu-id="02c42-131">sqlncli11.lib</span></span>  
  
     <span data-ttu-id="02c42-132">Deve estar no caminho da biblioteca do vinculador e ser especificado como um arquivo a ser vinculado.</span><span class="sxs-lookup"><span data-stu-id="02c42-132">Must be in the library path of the linker and specified as a file to be linked.</span></span> <span data-ttu-id="02c42-133">O sqlncli11.lib é distribuído com o driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="02c42-133">sqlncli11.lib is distributed with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
-   <span data-ttu-id="02c42-134">sqlncli11.dll</span><span class="sxs-lookup"><span data-stu-id="02c42-134">sqlncli11.dll</span></span>  
  
     <span data-ttu-id="02c42-135">Deve estar presente no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="02c42-135">Must be present at execution time.</span></span> <span data-ttu-id="02c42-136">O sqlncli11.dll é distribuído com o driver ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="02c42-136">sqlncli11.dll is distributed with the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="02c42-137">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="02c42-137">See Also</span></span>  
 <span data-ttu-id="02c42-138">[SQL Server Native Client &#40;ODBC&#41;](sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="02c42-138">[SQL Server Native Client &#40;ODBC&#41;](sql-server-native-client-odbc.md) </span></span>  
 <span data-ttu-id="02c42-139">[SQLColumnPrivileges](../../native-client-odbc-api/sqlcolumnprivileges.md) </span><span class="sxs-lookup"><span data-stu-id="02c42-139">[SQLColumnPrivileges](../../native-client-odbc-api/sqlcolumnprivileges.md) </span></span>  
 <span data-ttu-id="02c42-140">[SQLColumns](../../native-client-odbc-api/sqlcolumns.md) </span><span class="sxs-lookup"><span data-stu-id="02c42-140">[SQLColumns](../../native-client-odbc-api/sqlcolumns.md) </span></span>  
 <span data-ttu-id="02c42-141">[SQLPrimaryKeys](../../native-client-odbc-api/sqlprimarykeys.md) </span><span class="sxs-lookup"><span data-stu-id="02c42-141">[SQLPrimaryKeys](../../native-client-odbc-api/sqlprimarykeys.md) </span></span>  
 <span data-ttu-id="02c42-142">[SQLTablePrivileges](../../native-client-odbc-api/sqltableprivileges.md) </span><span class="sxs-lookup"><span data-stu-id="02c42-142">[SQLTablePrivileges](../../native-client-odbc-api/sqltableprivileges.md) </span></span>  
 <span data-ttu-id="02c42-143">[SQLTables](../../native-client-odbc-api/sqltables.md) </span><span class="sxs-lookup"><span data-stu-id="02c42-143">[SQLTables](../../native-client-odbc-api/sqltables.md) </span></span>  
 [<span data-ttu-id="02c42-144">SQLStatistics</span><span class="sxs-lookup"><span data-stu-id="02c42-144">SQLStatistics</span></span>](../../statistics/statistics.md)  
  
  
