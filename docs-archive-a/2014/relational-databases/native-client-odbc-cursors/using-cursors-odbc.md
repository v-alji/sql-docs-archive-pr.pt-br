---
title: Usando cursores (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- SQL Server Native Client ODBC driver, cursors
- ODBC cursors, about ODBC cursors
- ODBC applications, cursors
- cursors [ODBC]
- ODBC cursors
ms.assetid: 51322f92-0d76-44c9-9c33-9223676cf1d3
author: rothja
ms.author: jroth
ms.openlocfilehash: 61afedab4f4a1e309a08d9c2421ca7889811da8a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684716"
---
# <a name="using-cursors-odbc"></a><span data-ttu-id="46e0e-102">Usando cursores (ODBC)</span><span class="sxs-lookup"><span data-stu-id="46e0e-102">Using Cursors (ODBC)</span></span>
  <span data-ttu-id="46e0e-103">ODBC dá suporte a um modelo de cursor que permite:</span><span class="sxs-lookup"><span data-stu-id="46e0e-103">ODBC supports a cursor model that allows:</span></span>  
  
-   <span data-ttu-id="46e0e-104">Vários tipos de cursor.</span><span class="sxs-lookup"><span data-stu-id="46e0e-104">Several types of cursors.</span></span>  
  
-   <span data-ttu-id="46e0e-105">Recursos de rolagem e posicionamento dentro de um cursor.</span><span class="sxs-lookup"><span data-stu-id="46e0e-105">Scrolling and positioning within a cursor.</span></span>  
  
-   <span data-ttu-id="46e0e-106">Várias opções de simultaneidade.</span><span class="sxs-lookup"><span data-stu-id="46e0e-106">Several concurrency options.</span></span>  
  
-   <span data-ttu-id="46e0e-107">Atualizações posicionadas.</span><span class="sxs-lookup"><span data-stu-id="46e0e-107">Positioned updates.</span></span>  
  
 <span data-ttu-id="46e0e-108">Os aplicativos ODBC raramente declaram e abrem cursores ou usam qualquer instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] relacionada com cursor.</span><span class="sxs-lookup"><span data-stu-id="46e0e-108">ODBC applications rarely declare and open cursors or use any cursor-related [!INCLUDE[tsql](../../includes/tsql-md.md)] statements.</span></span> <span data-ttu-id="46e0e-109">O ODBC abre automaticamente um cursor para cada conjunto de resultados retornado de uma instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="46e0e-109">ODBC automatically opens a cursor for every result set returned from an SQL statement.</span></span> <span data-ttu-id="46e0e-110">As características dos cursores são controladas pelos atributos de instrução definidos com [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) antes da execução da instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="46e0e-110">The characteristics of the cursors are controlled by statement attributes set with [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md) before the SQL statement is executed.</span></span> <span data-ttu-id="46e0e-111">As funções API ODBC para o processamento de conjuntos de resultados dão suporte à gama completa de funcionalidades de cursor, como buscar, rolar e posicionar atualizações.</span><span class="sxs-lookup"><span data-stu-id="46e0e-111">The ODBC API functions for processing result sets support the full range of cursor functionality, including fetching, scrolling, and positioned updates.</span></span>  
  
 <span data-ttu-id="46e0e-112">Esta é uma comparação de como scripts [!INCLUDE[tsql](../../includes/tsql-md.md)] e aplicativos ODBC funcionam com cursores.</span><span class="sxs-lookup"><span data-stu-id="46e0e-112">This is a comparison of how [!INCLUDE[tsql](../../includes/tsql-md.md)] scripts and ODBC applications work with cursors.</span></span>  
  
|<span data-ttu-id="46e0e-113">Ação</span><span class="sxs-lookup"><span data-stu-id="46e0e-113">Action</span></span>|[!INCLUDE[tsql](../../includes/tsql-md.md)]|<span data-ttu-id="46e0e-114">ODBCODBC</span><span class="sxs-lookup"><span data-stu-id="46e0e-114">ODBC</span></span>|  
|------------|------------------------|----------|  
|<span data-ttu-id="46e0e-115">Definir o comportamento do cursor</span><span class="sxs-lookup"><span data-stu-id="46e0e-115">Define cursor behavior</span></span>|<span data-ttu-id="46e0e-116">Especifique por meio de parâmetros DECLARE CURSOR</span><span class="sxs-lookup"><span data-stu-id="46e0e-116">Specify through DECLARE CURSOR parameters</span></span>|<span data-ttu-id="46e0e-117">Definir atributos de cursor usando [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md)</span><span class="sxs-lookup"><span data-stu-id="46e0e-117">Set cursor attributes by using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md)</span></span>|  
|<span data-ttu-id="46e0e-118">Abrir um cursor</span><span class="sxs-lookup"><span data-stu-id="46e0e-118">Open a cursor</span></span>|<span data-ttu-id="46e0e-119">DECLARAR CURSOR aberto *cursor_name*</span><span class="sxs-lookup"><span data-stu-id="46e0e-119">DECLARE CURSOR OPEN *cursor_name*</span></span>|<span data-ttu-id="46e0e-120">**SQLExecDirect** ou **SQLExecute**</span><span class="sxs-lookup"><span data-stu-id="46e0e-120">**SQLExecDirect** or **SQLExecute**</span></span>|  
|<span data-ttu-id="46e0e-121">Buscar linhas</span><span class="sxs-lookup"><span data-stu-id="46e0e-121">Fetch rows</span></span>|<span data-ttu-id="46e0e-122">FETCH</span><span class="sxs-lookup"><span data-stu-id="46e0e-122">FETCH</span></span>|<span data-ttu-id="46e0e-123">**SQLFetch** ou [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)</span><span class="sxs-lookup"><span data-stu-id="46e0e-123">**SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md)</span></span>|  
|<span data-ttu-id="46e0e-124">Atualização posicionada</span><span class="sxs-lookup"><span data-stu-id="46e0e-124">Positioned update</span></span>|<span data-ttu-id="46e0e-125">Cláusula WHERE CURRENT OF em UPDATE ou DELETE</span><span class="sxs-lookup"><span data-stu-id="46e0e-125">WHERE CURRENT OF clause on UPDATE or DELETE</span></span>|<span data-ttu-id="46e0e-126">**SQLSetPos**</span><span class="sxs-lookup"><span data-stu-id="46e0e-126">**SQLSetPos**</span></span>|  
|<span data-ttu-id="46e0e-127">Fechar um cursor</span><span class="sxs-lookup"><span data-stu-id="46e0e-127">Close a cursor</span></span>|<span data-ttu-id="46e0e-128">FECHAR *cursor_name* desalocar</span><span class="sxs-lookup"><span data-stu-id="46e0e-128">CLOSE *cursor_name* DEALLOCATE</span></span>|[<span data-ttu-id="46e0e-129">SQLCloseCursor</span><span class="sxs-lookup"><span data-stu-id="46e0e-129">SQLCloseCursor</span></span>](../native-client-odbc-api/sqlclosecursor.md)|  
  
 <span data-ttu-id="46e0e-130">Os cursores de servidor implementados no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] dão suporte à funcionalidade de modelo do cursor ODBC.</span><span class="sxs-lookup"><span data-stu-id="46e0e-130">The server cursors implemented in [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] support the functionality of the ODBC cursor model.</span></span> <span data-ttu-id="46e0e-131">O driver do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client usa cursores de servidor para dar suporte à funcionalidade da API ODBC.</span><span class="sxs-lookup"><span data-stu-id="46e0e-131">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client driver uses server cursors to support the cursor functionality of the ODBC API.</span></span>  
  
## <a name="in-this-section"></a><span data-ttu-id="46e0e-132">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="46e0e-132">In This Section</span></span>  
  
-   [<span data-ttu-id="46e0e-133">Como os cursores são implementados</span><span class="sxs-lookup"><span data-stu-id="46e0e-133">How Cursors Are Implemented</span></span>](implementation/how-cursors-are-implemented.md)  
  
-   [<span data-ttu-id="46e0e-134">Tipos de cursor</span><span class="sxs-lookup"><span data-stu-id="46e0e-134">Cursor Types</span></span>](cursor-types.md)  
  
-   [<span data-ttu-id="46e0e-135">Comportamentos de cursor</span><span class="sxs-lookup"><span data-stu-id="46e0e-135">Cursor Behaviors</span></span>](cursor-behaviors.md)  
  
-   [<span data-ttu-id="46e0e-136">Propriedades do cursor</span><span class="sxs-lookup"><span data-stu-id="46e0e-136">Cursor Properties</span></span>](properties/cursor-properties.md)  
  
-   [<span data-ttu-id="46e0e-137">Detalhes de programação do cursor &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="46e0e-137">Cursor Programming Details &#40;ODBC&#41;</span></span>](programming/cursor-programming-details-odbc.md)  
  
-   [<span data-ttu-id="46e0e-138">Rolando e buscando linhas</span><span class="sxs-lookup"><span data-stu-id="46e0e-138">Scrolling and Fetching Rows</span></span>](../native-client-ole-db-rowsets/fetching-rows.md)  
  
-   [<span data-ttu-id="46e0e-139">Atualizações posicionadas &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="46e0e-139">Positioned Updates &#40;ODBC&#41;</span></span>](positioned-updates-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="46e0e-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="46e0e-140">See Also</span></span>  
 <span data-ttu-id="46e0e-141">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="46e0e-141">[SQL Server Native Client &#40;ODBC&#41;](../native-client/odbc/sql-server-native-client-odbc.md) </span></span>  
 <span data-ttu-id="46e0e-142">[FECHAR &#40;&#41;Transact-SQL](/sql/t-sql/language-elements/close-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="46e0e-142">[CLOSE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/close-transact-sql) </span></span>  
 <span data-ttu-id="46e0e-143">[Cursores](../../relational-databases/cursors.md) </span><span class="sxs-lookup"><span data-stu-id="46e0e-143">[Cursors](../../relational-databases/cursors.md) </span></span>  
 <span data-ttu-id="46e0e-144">[Desalocar &#40;&#41;de Transact-SQL](/sql/t-sql/language-elements/deallocate-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="46e0e-144">[DEALLOCATE &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/deallocate-transact-sql) </span></span>  
 <span data-ttu-id="46e0e-145">[DECLARAR CURSOR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-cursor-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="46e0e-145">[DECLARE CURSOR &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/declare-cursor-transact-sql) </span></span>  
 <span data-ttu-id="46e0e-146">[FETCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/fetch-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="46e0e-146">[FETCH &#40;Transact-SQL&#41;](/sql/t-sql/language-elements/fetch-transact-sql) </span></span>  
 [<span data-ttu-id="46e0e-147">OPEN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="46e0e-147">OPEN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/language-elements/open-transact-sql)  
  
  
