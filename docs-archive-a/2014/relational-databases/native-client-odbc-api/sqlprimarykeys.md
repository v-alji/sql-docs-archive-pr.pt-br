---
title: SQLPrimaryKeys | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLPrimaryKeys function
ms.assetid: bc61cd5b-d2f4-4f87-abc7-743cf9ea772d
author: rothja
ms.author: jroth
ms.openlocfilehash: 67a932996ccbf52f5ab21fd6aa62381184ebc510
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87583007"
---
# <a name="sqlprimarykeys"></a><span data-ttu-id="e7f3a-102">SQLPrimaryKeys</span><span class="sxs-lookup"><span data-stu-id="e7f3a-102">SQLPrimaryKeys</span></span>
  <span data-ttu-id="e7f3a-103">Uma tabela pode ter uma coluna ou colunas que podem servir como identificadores de linha exclusivos, e tabelas criadas sem uma restrição de chave primária retornam um conjunto de resultados vazio para SQLPrimaryKeys.</span><span class="sxs-lookup"><span data-stu-id="e7f3a-103">A table might have a column or columns that can serve as unique row identifiers, and tables created without a PRIMARY KEY constraint return an empty result set to SQLPrimaryKeys.</span></span> <span data-ttu-id="e7f3a-104">A função ODBC [SQLSpecialColumns](sqlspecialcolumns.md) relata candidatos de identificador de linha para tabelas sem chaves primárias.</span><span class="sxs-lookup"><span data-stu-id="e7f3a-104">The ODBC function [SQLSpecialColumns](sqlspecialcolumns.md) reports row identifier candidates for tables without primary keys.</span></span>  
  
 <span data-ttu-id="e7f3a-105">SQLPrimaryKeys retorna SQL_SUCCESS se os valores existem ou não para os parâmetros *CatalogName*, *schemas*ou *TableName* .</span><span class="sxs-lookup"><span data-stu-id="e7f3a-105">SQLPrimaryKeys returns SQL_SUCCESS whether or not values exist for *CatalogName*, *SchemaName*, or *TableName* parameters.</span></span> <span data-ttu-id="e7f3a-106">SQLFetch retorna SQL_NO_DATA quando são usados valores inválidos nesses parâmetros.</span><span class="sxs-lookup"><span data-stu-id="e7f3a-106">SQLFetch returns SQL_NO_DATA when invalid values are used in these parameters.</span></span>  
  
 <span data-ttu-id="e7f3a-107">SQLPrimaryKeys pode ser executado em um cursor de servidor estático.</span><span class="sxs-lookup"><span data-stu-id="e7f3a-107">SQLPrimaryKeys can be executed on a static server cursor.</span></span> <span data-ttu-id="e7f3a-108">Uma tentativa de executar SQLPrimaryKeys em um cursor atualizável (dinâmico ou de conjunto de chaves) retornará SQL_SUCCESS_WITH_INFO indicando que o tipo de cursor foi alterado.</span><span class="sxs-lookup"><span data-stu-id="e7f3a-108">An attempt to execute SQLPrimaryKeys on an updatable (dynamic or keyset) cursor will return SQL_SUCCESS_WITH_INFO indicating that the cursor type has been changed.</span></span>  
  
 <span data-ttu-id="e7f3a-109">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client dá suporte ao relatório de informações de tabelas em servidores vinculados, aceitando um nome de duas partes para o parâmetro *CatalogName* : *Linked_Server_Name.Catalog_Name*.</span><span class="sxs-lookup"><span data-stu-id="e7f3a-109">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver supports reporting information for tables on linked servers by accepting a two-part name for the *CatalogName* parameter: *Linked_Server_Name.Catalog_Name*.</span></span>  
  
## <a name="sqlprimarykeys-and-table-valued-parameters"></a><span data-ttu-id="e7f3a-110">SQLPrimaryKeys e parâmetros com valor de tabela</span><span class="sxs-lookup"><span data-stu-id="e7f3a-110">SQLPrimaryKeys and Table-Valued Parameters</span></span>  
 <span data-ttu-id="e7f3a-111">Se o atributo de instrução SQL_SOPT_SS_NAME_SCOPE tiver o valor SQL_SS_NAME_SCOPE_TABLE_TYPE, em vez de seu valor padrão de SQL_SS_NAME_SCOPE_TABLE, SQLPrimaryKeys retornará informações sobre as colunas de chave primária dos tipos de tabela.</span><span class="sxs-lookup"><span data-stu-id="e7f3a-111">If the statement attribute SQL_SOPT_SS_NAME_SCOPE has the value SQL_SS_NAME_SCOPE_TABLE_TYPE, rather than its default value of SQL_SS_NAME_SCOPE_TABLE, SQLPrimaryKeys will return information about primary key columns of table types.</span></span> <span data-ttu-id="e7f3a-112">Para obter mais informações sobre SQL_SOPT_SS_NAME_SCOPE, consulte [SQLSetStmtAttr](sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="e7f3a-112">For more information on SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="e7f3a-113">Para obter mais informações sobre parâmetros com valor de tabela, consulte [parâmetros com valor de tabela &#40;&#41;ODBC ](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="e7f3a-113">For more information about table-valued parameters, see [Table-Valued Parameters &#40;ODBC&#41;](../native-client-odbc-table-valued-parameters/table-valued-parameters-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e7f3a-114">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e7f3a-114">See Also</span></span>  
 <span data-ttu-id="e7f3a-115">[Função SQLPrimaryKeys](https://go.microsoft.com/fwlink/?LinkId=59361) </span><span class="sxs-lookup"><span data-stu-id="e7f3a-115">[SQLPrimaryKeys Function](https://go.microsoft.com/fwlink/?LinkId=59361) </span></span>  
 [<span data-ttu-id="e7f3a-116">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="e7f3a-116">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
