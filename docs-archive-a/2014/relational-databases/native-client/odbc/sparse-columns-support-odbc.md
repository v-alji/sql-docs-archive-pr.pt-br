---
title: Suporte a colunas esparsas (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: 11ae959f-2fb6-4b85-ac5d-1476a82136d4
author: rothja
ms.author: jroth
ms.openlocfilehash: 076709f3f37e92492f7c3f8c20ee692416d9e867
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87681628"
---
# <a name="sparse-columns-support-odbc"></a><span data-ttu-id="c5bf1-102">Suporte a colunas esparsas (ODBC)</span><span class="sxs-lookup"><span data-stu-id="c5bf1-102">Sparse Columns Support (ODBC)</span></span>
  <span data-ttu-id="c5bf1-103">Este tópico descreve o suporte a ODBC do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client para colunas esparsas.</span><span class="sxs-lookup"><span data-stu-id="c5bf1-103">This topic describes [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC support for sparse columns.</span></span> <span data-ttu-id="c5bf1-104">Para obter um exemplo que demonstra o suporte ODBC para colunas esparsas, consulte [chamar SQLColumns em uma tabela com colunas esparsas](../../native-client-odbc-how-to/call-sqlcolumns-on-a-table-with-sparse-columns.md).</span><span class="sxs-lookup"><span data-stu-id="c5bf1-104">For a sample demonstrating ODBC support for sparse columns, see [Call SQLColumns on a Table with Sparse Columns](../../native-client-odbc-how-to/call-sqlcolumns-on-a-table-with-sparse-columns.md).</span></span> <span data-ttu-id="c5bf1-105">Para obter mais informações sobre colunas esparsas, consulte [suporte a colunas esparsas em SQL Server Native Client](../features/sparse-columns-support-in-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="c5bf1-105">For more information about sparse columns, see [Sparse Columns Support in SQL Server Native Client](../features/sparse-columns-support-in-sql-server-native-client.md).</span></span>  
  
## <a name="statement-metadata"></a><span data-ttu-id="c5bf1-106">Metadados de instrução</span><span class="sxs-lookup"><span data-stu-id="c5bf1-106">Statement Metadata</span></span>  
 <span data-ttu-id="c5bf1-107">O campo do descritor APD (descritor de parâmetro de aplicativo) e o atributo da instrução SQL_SOPT_SS_NAME_SCOPE aceitam os valores adicionais SQL_SS_NAME_SCOPE_EXTENDED e SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span><span class="sxs-lookup"><span data-stu-id="c5bf1-107">The application parameter descriptor (APD) descriptor field and SQL_SOPT_SS_NAME_SCOPE statement attribute accepts the additional values SQL_SS_NAME_SCOPE_EXTENDED and SQL_SS_NAME_SCOPE_SPARSE_COLUMN_SET.</span></span> <span data-ttu-id="c5bf1-108">Esses valores especificam quais colunas são incluídas no conjunto de resultados retornado por [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="c5bf1-108">These values specify which columns are included in the result set returned by [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span></span> <span data-ttu-id="c5bf1-109">Para obter mais informações sobre SQL_SOPT_SS_NAME_SCOPE, consulte [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="c5bf1-109">For more information about SQL_SOPT_SS_NAME_SCOPE, see [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
 <span data-ttu-id="c5bf1-110">Um novo IRD (descritor de linha de implementação), um campo SQLSMALLINT somente leitura chamado SQL_CA_SS_IS_COLUMN_SET, pode ser usado para determinar se uma coluna é um valor XML `column_set`.</span><span class="sxs-lookup"><span data-stu-id="c5bf1-110">A new implementation row descriptor (IRD), a read-only SQLSMALLINT field called SQL_CA_SS_IS_COLUMN_SET, can be used to determine if a column is an XML `column_set` value.</span></span> <span data-ttu-id="c5bf1-111">SQL_CA_SS_IS_COLUMN_SET usa os valores SQL_TRUE e SQL_FALSE.</span><span class="sxs-lookup"><span data-stu-id="c5bf1-111">SQL_CA_SS_IS_COLUMN_SET takes the values SQL_TRUE and SQL_FALSE.</span></span>  
  
## <a name="catalog-metadata"></a><span data-ttu-id="c5bf1-112">Metadados de catálogo</span><span class="sxs-lookup"><span data-stu-id="c5bf1-112">Catalog Metadata</span></span>  
 <span data-ttu-id="c5bf1-113">Duas colunas específicas do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (SS_IS_SPARSE e SS_IS_COLUMN_SET) foram adicionadas ao conjunto de resultados de [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span><span class="sxs-lookup"><span data-stu-id="c5bf1-113">Two [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] specific columns (SS_IS_SPARSE and SS_IS_COLUMN_SET) have been added to the result set for [SQLColumns](../../native-client-odbc-api/sqlcolumns.md).</span></span>  
  
## <a name="odbc-function-support-for-sparse-columns"></a><span data-ttu-id="c5bf1-114">Suporte da função de ODBC para colunas esparsas</span><span class="sxs-lookup"><span data-stu-id="c5bf1-114">ODBC Function Support for Sparse Columns</span></span>  
 <span data-ttu-id="c5bf1-115">As seguintes funções de ODBC foram atualizadas para oferecer suporte a colunas esparsas no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span><span class="sxs-lookup"><span data-stu-id="c5bf1-115">The following ODBC functions have been updated to support sparse columns in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client:</span></span>  
  
-   [<span data-ttu-id="c5bf1-116">SQLColAttribute</span><span class="sxs-lookup"><span data-stu-id="c5bf1-116">SQLColAttribute</span></span>](../../native-client-odbc-api/sqlcolattribute.md)  
  
-   [<span data-ttu-id="c5bf1-117">SQLColumns</span><span class="sxs-lookup"><span data-stu-id="c5bf1-117">SQLColumns</span></span>](../../native-client-odbc-api/sqlcolumns.md)  
  
-   [<span data-ttu-id="c5bf1-118">SQLGetDescField</span><span class="sxs-lookup"><span data-stu-id="c5bf1-118">SQLGetDescField</span></span>](../../native-client-odbc-api/sqlgetdescfield.md)  
  
-   [<span data-ttu-id="c5bf1-119">SQLSetDescField</span><span class="sxs-lookup"><span data-stu-id="c5bf1-119">SQLSetDescField</span></span>](../../native-client-odbc-api/sqlsetdescfield.md)  
  
-   [<span data-ttu-id="c5bf1-120">SQLSetStmtAttr</span><span class="sxs-lookup"><span data-stu-id="c5bf1-120">SQLSetStmtAttr</span></span>](../../native-client-odbc-api/sqlsetstmtattr.md)  
  
## <a name="see-also"></a><span data-ttu-id="c5bf1-121">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c5bf1-121">See Also</span></span>  
 [<span data-ttu-id="c5bf1-122">SQL Server Native Client &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="c5bf1-122">SQL Server Native Client &#40;ODBC&#41;</span></span>](sql-server-native-client-odbc.md)  
  
  
