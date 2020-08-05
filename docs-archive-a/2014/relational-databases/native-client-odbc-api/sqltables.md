---
title: SQLTables | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLTables function
ms.assetid: 77b6c15c-9cf7-4019-b3f0-3d27d23ef656
author: rothja
ms.author: jroth
ms.openlocfilehash: bad60aa102a7771935e37ac963e6fa0d3cb2fd57
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573953"
---
# <a name="sqltables"></a><span data-ttu-id="52fc9-102">SQLTables</span><span class="sxs-lookup"><span data-stu-id="52fc9-102">SQLTables</span></span>
  <span data-ttu-id="52fc9-103">SQLTables pode ser executado em um cursor de servidor estático.</span><span class="sxs-lookup"><span data-stu-id="52fc9-103">SQLTables can be executed on a static server cursor.</span></span> <span data-ttu-id="52fc9-104">Uma tentativa de executar SQLTables em um cursor atualizável (dinâmico ou de conjunto de chaves) retornará SQL_SUCCESS_WITH_INFO indicando que o tipo de cursor foi alterado.</span><span class="sxs-lookup"><span data-stu-id="52fc9-104">An attempt to execute SQLTables on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="52fc9-105">SQLTables relata tabelas de todos os bancos de dados quando o parâmetro *CatalogName* é SQL_ALL_CATALOGS e todos os outros parâmetros contêm valores padrão (PONTEIROs nulos).</span><span class="sxs-lookup"><span data-stu-id="52fc9-105">SQLTables reports tables from all databases when the *CatalogName* parameter is SQL_ALL_CATALOGS and all other parameters contain default values (NULL pointers).</span></span>  
  
 <span data-ttu-id="52fc9-106">Para relatar os catálogos, os esquemas e os tipos de tabela disponíveis, o SQLTables faz uso especial de cadeias de caracteres vazias (ponteiros de byte de comprimento zero).</span><span class="sxs-lookup"><span data-stu-id="52fc9-106">To report available catalogs, schemas, and table types, SQLTables makes special use of empty strings (zero-length byte pointers).</span></span> <span data-ttu-id="52fc9-107">As cadeias de caracteres vazias não são os valores padrões (ponteiros NULL).</span><span class="sxs-lookup"><span data-stu-id="52fc9-107">Empty strings are not default values (NULL pointers).</span></span>  
  
 <span data-ttu-id="52fc9-108">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client dá suporte ao relatório de informações de tabelas em servidores vinculados, aceitando um nome de duas partes para o parâmetro *CatalogName* : *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="52fc9-108">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
 <span data-ttu-id="52fc9-109">SQLTables retorna informações sobre todas as tabelas cujos nomes correspondem a *TableName* e pertencem ao usuário atual.</span><span class="sxs-lookup"><span data-stu-id="52fc9-109">SQLTables returns information about any tables whose names match *TableName* and are owned by the current user.</span></span>  
  
## <a name="sqltables-and-table-valued-parameters"></a><span data-ttu-id="52fc9-110">SQLTables e parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="52fc9-110">SQLTables and Table-Valued Parameters</span></span>  
 <span data-ttu-id="52fc9-111">Quando o atributo de instrução SQL_SOPT_SS_NAME_SCOPE tem o valor SQL_SS_NAME_SCOPE_TABLE_TYPE, em vez de seu valor padrão de SQL_SS_NAME_SCOPE_TABLE, SQLTables retorna informações sobre tipos de tabela.</span><span class="sxs-lookup"><span data-stu-id="52fc9-111">When the statement attribute SQL_SOPT_SS_NAME_SCOPE has the value SQL_SS_NAME_SCOPE_TABLE_TYPE, rather than its default value of SQL_SS_NAME_SCOPE_TABLE, SQLTables returns information about table types.</span></span> <span data-ttu-id="52fc9-112">O valor de TABLE_TYPE retornado para um tipo de tabela na coluna 4 do conjunto de resultados retornado por SQLTables é o tipo de tabela.</span><span class="sxs-lookup"><span data-stu-id="52fc9-112">The TABLE_TYPE value returned for a table type in column 4 of the result set returned by SQLTables is TABLE TYPE.</span></span> <span data-ttu-id="52fc9-113">Para obter mais informações sobre SQL_SOPT_SS_NAME_SCOPE, consulte [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="52fc9-113">For more information on SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="52fc9-114">Tabelas, exibições e sinônimos compartilham um namespace comum que é diferente do namespace usado por tipos de tabela.</span><span class="sxs-lookup"><span data-stu-id="52fc9-114">Tables, views, and synonyms share a common namespace that is distinct from the namespace used by table types.</span></span> <span data-ttu-id="52fc9-115">Apesar de não ser possível ter uma tabela e uma exibição com o mesmo nome, é possível ter uma tabela de um tipo de tabela com o mesmo nome, no mesmo catálogo e no mesmo esquema.</span><span class="sxs-lookup"><span data-stu-id="52fc9-115">Although it is not possible to have a table and a view with the same name, it is possible to have a table and a table type with the same in the same catalog and schema.</span></span>  
  
 <span data-ttu-id="52fc9-116">Para obter mais informações sobre parâmetros com valor de tabela, consulte [parâmetros com valor de tabela &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="52fc9-116">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="52fc9-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="52fc9-117">Example</span></span>  
  
```  
// Get a list of all tables in the current database.  
SQLTables(hstmt, NULL, 0, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of all tables in all databases.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, NULL, 0, NULL, 0, NULL,0);  
  
// Get a list of databases on the current connection's server.  
SQLTables(hstmt, (SQLCHAR*) "%", SQL_NTS, (SQLCHAR*)"", 0, (SQLCHAR*)"",  
    0, NULL, 0);  
```  
  
## <a name="see-also"></a><span data-ttu-id="52fc9-118">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="52fc9-118">See Also</span></span>  
 <span data-ttu-id="52fc9-119">[Função SQLTables](https://go.microsoft.com/fwlink/?LinkId=59374) </span><span class="sxs-lookup"><span data-stu-id="52fc9-119">[SQLTables Function](https://go.microsoft.com/fwlink/?LinkId=59374) </span></span>  
 [<span data-ttu-id="52fc9-120">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="52fc9-120">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
