---
title: Descoberta de metadados | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
ms.assetid: ec3c0f4f-f838-43ce-85f2-cf2761e2aac5
author: rothja
ms.author: jroth
ms.openlocfilehash: 571df9f21ab46a53c8aba7907039ce02afd6ad05
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679909"
---
# <a name="metadata-discovery"></a><span data-ttu-id="22409-102">Descoberta de metadados</span><span class="sxs-lookup"><span data-stu-id="22409-102">Metadata Discovery</span></span>
  <span data-ttu-id="22409-103">A melhoria na descoberta de metadados no [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] permite que aplicativos do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client assegurem que os metadados de colunas ou parâmetros retornados da execução de uma consulta sejam idênticos ou compatíveis com o formato de metadados especificado antes da execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="22409-103">The metadata discovery improvement in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] allows [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client applications to ensure that column or parameter metadata returned from the execution of a query is identical to or compatible with the metadata format you specified before you executed the query.</span></span> <span data-ttu-id="22409-104">Você receberá um erro se os metadados retornados depois da execução da consulta não forem compatíveis com o formato de metadados especificado antes da execução da consulta.</span><span class="sxs-lookup"><span data-stu-id="22409-104">You will receive an error if the metadata returned after query execution is not compatible with the metadata format you specified before query execution.</span></span>  
  
 <span data-ttu-id="22409-105">Em funções bcp e ODBC, e em interfaces IBCPSession e IBCPSession2, agora você pode especificar uma leitura atrasada (descoberta de metadados atrasada) para evitar a descoberta de metadados para operações de saída de consulta.</span><span class="sxs-lookup"><span data-stu-id="22409-105">In bcp and ODBC functions, and IBCPSession and IBCPSession2 interfaces, you can now specify a delayed read (delayed metadata discovery) to avoid metadata discovery for query out operations.</span></span> <span data-ttu-id="22409-106">Isso melhora o desempenho e elimina falhas de descoberta de metadados.</span><span class="sxs-lookup"><span data-stu-id="22409-106">This improves performance and eliminates metadata discovery failures.</span></span>  
  
 <span data-ttu-id="22409-107">Se você desenvolver um aplicativo usando o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client no [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] , mas se conectar a uma versão de servidor anterior ao [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], a funcionalidade de descoberta de metadados corresponderá à versão do servidor.</span><span class="sxs-lookup"><span data-stu-id="22409-107">If you develop an application using [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] but connect to a server version earlier than [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)], metadata discovery functionality will correspond to the version of the server.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="22409-108">Comentários</span><span class="sxs-lookup"><span data-stu-id="22409-108">Remarks</span></span>  
 <span data-ttu-id="22409-109">As funções bcp a seguir foram aperfeiçoadas no [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] para fornecer descoberta de metadados aprimorada:</span><span class="sxs-lookup"><span data-stu-id="22409-109">The following bcp functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   [<span data-ttu-id="22409-110">bcp_columns</span><span class="sxs-lookup"><span data-stu-id="22409-110">bcp_columns</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md)  
  
-   [<span data-ttu-id="22409-111">bcp_control</span><span class="sxs-lookup"><span data-stu-id="22409-111">bcp_control</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md)  
  
-   [<span data-ttu-id="22409-112">bcp_getcolfmt</span><span class="sxs-lookup"><span data-stu-id="22409-112">bcp_getcolfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-getcolfmt.md)  
  
-   [<span data-ttu-id="22409-113">bcp_readfmt</span><span class="sxs-lookup"><span data-stu-id="22409-113">bcp_readfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md)  
  
-   [<span data-ttu-id="22409-114">bcp_setcolfmt</span><span class="sxs-lookup"><span data-stu-id="22409-114">bcp_setcolfmt</span></span>](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setcolfmt.md)  
  
 <span data-ttu-id="22409-115">Você também verá uma melhoria no desempenho ao especificar o formato de metadados usando [bcp_setbulkmode](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setbulkmode.md).</span><span class="sxs-lookup"><span data-stu-id="22409-115">You will also see a performance improvement when specifying metadata format using [bcp_setbulkmode](../../native-client-odbc-extensions-bulk-copy-functions/bcp-setbulkmode.md).</span></span>  
  
 <span data-ttu-id="22409-116">[bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) tem um novo *eOption* para controlar o comportamento de bcp_readfmt: `BCPDELAYREADFMT` .</span><span class="sxs-lookup"><span data-stu-id="22409-116">[bcp_control](../../native-client-odbc-extensions-bulk-copy-functions/bcp-control.md) has a new *eOption* to control the behavior of bcp_readfmt: `BCPDELAYREADFMT`.</span></span>  
  
 <span data-ttu-id="22409-117">As funções ODBC a seguir foram aperfeiçoadas no [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] para fornecer descoberta de metadados aprimorada:</span><span class="sxs-lookup"><span data-stu-id="22409-117">The following ODBC functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   [<span data-ttu-id="22409-118">SQLNumResultCols</span><span class="sxs-lookup"><span data-stu-id="22409-118">SQLNumResultCols</span></span>](../../native-client-odbc-api/sqlnumresultcols.md)  
  
-   [<span data-ttu-id="22409-119">SQLDescribeCol</span><span class="sxs-lookup"><span data-stu-id="22409-119">SQLDescribeCol</span></span>](../../native-client-odbc-api/sqldescribecol.md)  
  
-   [<span data-ttu-id="22409-120">SQLNumParams</span><span class="sxs-lookup"><span data-stu-id="22409-120">SQLNumParams</span></span>](../../native-client-odbc-api/sqlnumparams.md)  
  
-   [<span data-ttu-id="22409-121">SQLDescribeParam</span><span class="sxs-lookup"><span data-stu-id="22409-121">SQLDescribeParam</span></span>](../../native-client-odbc-api/sqldescribeparam.md)  
  
 <span data-ttu-id="22409-122">As funções de membros OLE DB a seguir foram aperfeiçoadas no [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] para fornecer descoberta de metadados aprimorada:</span><span class="sxs-lookup"><span data-stu-id="22409-122">The following OLE DB member functions have been enhanced in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)] to provide improved metadata discovery:</span></span>  
  
-   <span data-ttu-id="22409-123">IColumnsInfo::GetColumnInfo</span><span class="sxs-lookup"><span data-stu-id="22409-123">IColumnsInfo::GetColumnInfo</span></span>  
  
-   <span data-ttu-id="22409-124">IColumnsRowset::GetColumnsRowset</span><span class="sxs-lookup"><span data-stu-id="22409-124">IColumnsRowset::GetColumnsRowset</span></span>  
  
-   <span data-ttu-id="22409-125">ICommandWithParameters::GetParameterInfo (confira [ICommandWithParameters](../../native-client-ole-db-interfaces/icommandwithparameters.md) para obter mais informações)</span><span class="sxs-lookup"><span data-stu-id="22409-125">ICommandWithParameters::GetParameterInfo (see [ICommandWithParameters](../../native-client-ole-db-interfaces/icommandwithparameters.md) for more information)</span></span>  
  
 <span data-ttu-id="22409-126">Você também verá uma melhoria no desempenho ao especificar o formato de metadados usando IBCPSession::BCPSetBulkMode</span><span class="sxs-lookup"><span data-stu-id="22409-126">You will also see a performance improvement when specifying metadata format using IBCPSession::BCPSetBulkMode</span></span>  
  
 <span data-ttu-id="22409-127">A descoberta de metadados aprimorada no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client é possível devido à adição de dois procedimentos armazenados no [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="22409-127">The improved metadata discovery in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client is possible because of the addition of two stored procedures in [!INCLUDE[ssSQL11](../../../includes/sssql11-md.md)]:</span></span>  
  
-   <span data-ttu-id="22409-128">sp_describe_first_result_set</span><span class="sxs-lookup"><span data-stu-id="22409-128">sp_describe_first_result_set</span></span>  
  
-   <span data-ttu-id="22409-129">sp_describe_undeclared_parameters</span><span class="sxs-lookup"><span data-stu-id="22409-129">sp_describe_undeclared_parameters</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22409-130">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="22409-130">See Also</span></span>  
 [<span data-ttu-id="22409-131">Recursos do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="22409-131">SQL Server Native Client Features</span></span>](sql-server-native-client-features.md)  
  
  
