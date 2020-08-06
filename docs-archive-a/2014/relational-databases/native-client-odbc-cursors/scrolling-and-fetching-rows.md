---
title: Rolagem e busca de linhas | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- scrollable cursors [SQL Server]
- SQL Server Native Client ODBC driver, cursors
- SQLFetchScroll function
- ODBC applications, cursors
- cursors [ODBC], fetching rows
- ODBC cursors, fetching rows
- cursors [ODBC], scrolling rows
- fetching [ODBC]
- ODBC cursors, scrolling rows
ms.assetid: 9109f10d-326b-4a6d-8c97-831f60da8c4c
author: rothja
ms.author: jroth
ms.openlocfilehash: 97586f82ddddb79581b0f9c027aa60d7822b472c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684720"
---
# <a name="scrolling-and-fetching-rows"></a><span data-ttu-id="b035c-102">Rolando e buscando linhas</span><span class="sxs-lookup"><span data-stu-id="b035c-102">Scrolling and Fetching Rows</span></span>
  <span data-ttu-id="b035c-103">Para usar um cursor rolável, um aplicativo ODBC deve:</span><span class="sxs-lookup"><span data-stu-id="b035c-103">To use a scrollable cursor, an ODBC application must:</span></span>  
  
-   <span data-ttu-id="b035c-104">Defina os recursos de cursor usando [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span><span class="sxs-lookup"><span data-stu-id="b035c-104">Set the cursor capabilities using [SQLSetStmtAttr](../native-client-odbc-api/sqlsetstmtattr.md).</span></span>  
  
-   <span data-ttu-id="b035c-105">Abra o cursor usando **SQLExecute** ou **SQLExecDirect**.</span><span class="sxs-lookup"><span data-stu-id="b035c-105">Open the cursor using **SQLExecute** or **SQLExecDirect**.</span></span>  
  
-   <span data-ttu-id="b035c-106">Role e busque linhas usando **SQLFetch** ou [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span><span class="sxs-lookup"><span data-stu-id="b035c-106">Scroll and fetch rows using **SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md).</span></span>  
  
 <span data-ttu-id="b035c-107">**SQLFetch** e **SQLFetchSroll** podem buscar blocos de linhas por vez.</span><span class="sxs-lookup"><span data-stu-id="b035c-107">Both **SQLFetch** and **SQLFetchSroll** can fetch blocks of rows at a time.</span></span> <span data-ttu-id="b035c-108">O número de linhas retornadas é especificado usando **SQLSetStmtAttr** para definir o parâmetro SQL_ATTR_ROW_ARRAY_SIZE.</span><span class="sxs-lookup"><span data-stu-id="b035c-108">The number of rows returned is specified by using **SQLSetStmtAttr** to set the SQL_ATTR_ROW_ARRAY_SIZE parameter.</span></span>  
  
 <span data-ttu-id="b035c-109">Os aplicativos ODBC podem usar **SQLFetch** para buscar por meio de um cursor de somente avanço.</span><span class="sxs-lookup"><span data-stu-id="b035c-109">ODBC applications can use **SQLFetch** to fetch through a forward-only cursor.</span></span>  
  
 <span data-ttu-id="b035c-110">**SQLFetchScroll** é usado para rolar em um cursor.</span><span class="sxs-lookup"><span data-stu-id="b035c-110">**SQLFetchScroll** is used to scroll around a cursor.</span></span> <span data-ttu-id="b035c-111">O **SQLFetchScroll** dá suporte à busca dos próximos conjuntos de linhas, antes, primeiro e último, além da busca relativa (busque o conjunto de linha *n* linhas do início do conjunto de linhas atual) e a busca absoluta (busque o conjunto de linhas começando na linha *n*).</span><span class="sxs-lookup"><span data-stu-id="b035c-111">**SQLFetchScroll** supports fetching the next, prior, first, and last rowsets in addition to relative fetching (fetch the rowset *n* rows from the start of the current rowset) and absolute fetching (fetch the rowset starting at row *n*).</span></span> <span data-ttu-id="b035c-112">Se *n* for negativo em uma busca absoluta, as linhas serão contadas a partir do final do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="b035c-112">If *n* is negative in an absolute fetch, rows are counted from the end of the result set.</span></span> <span data-ttu-id="b035c-113">Uma busca absoluta da linha -1 significa buscar o conjunto de linhas que inicia com a última linha no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="b035c-113">An absolute fetch of row -1 means to fetch the rowset that starts with the last row in the result set.</span></span>  
  
 <span data-ttu-id="b035c-114">Os aplicativos que usam **SQLFetchScroll** apenas para seus recursos de cursor de bloco, como relatórios, provavelmente passarão pelo conjunto de resultados uma única vez, usando apenas a opção para buscar o próximo conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="b035c-114">Applications that use **SQLFetchScroll** only for its block cursor capabilities, such as reports, are likely to pass through the result set a single time, using only the option to fetch the next rowset.</span></span> <span data-ttu-id="b035c-115">Os aplicativos baseados em tela, por outro lado, podem tirar proveito de todos os recursos do **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="b035c-115">Screen-based applications, on the other hand, can take advantage of all the capabilities of **SQLFetchScroll**.</span></span> <span data-ttu-id="b035c-116">Se o aplicativo definir o tamanho do conjunto de linhas como o número de linhas exibidas na tela e associar os buffers de tela ao conjunto de resultados, ele poderá converter as operações da barra de rolagem diretamente em chamadas para **SQLFetchScroll**.</span><span class="sxs-lookup"><span data-stu-id="b035c-116">If the application sets the rowset size to the number of rows displayed on the screen and binds the screen buffers to the result set, it can translate scroll bar operations directly to calls to **SQLFetchScroll**.</span></span>  
  
|<span data-ttu-id="b035c-117">Operação de barra de rolagem</span><span class="sxs-lookup"><span data-stu-id="b035c-117">Scroll bar operation</span></span>|<span data-ttu-id="b035c-118">Opção de rolagem SQLFetchScroll</span><span class="sxs-lookup"><span data-stu-id="b035c-118">SQLFetchScroll scrolling option</span></span>|  
|--------------------------|-------------------------------------|  
|<span data-ttu-id="b035c-119">Uma página acima</span><span class="sxs-lookup"><span data-stu-id="b035c-119">Page up</span></span>|<span data-ttu-id="b035c-120">SQL_FETCH_PRIOR</span><span class="sxs-lookup"><span data-stu-id="b035c-120">SQL_FETCH_PRIOR</span></span>|  
|<span data-ttu-id="b035c-121">Page Down</span><span class="sxs-lookup"><span data-stu-id="b035c-121">Page down</span></span>|<span data-ttu-id="b035c-122">SQL_FETCH_NEXT</span><span class="sxs-lookup"><span data-stu-id="b035c-122">SQL_FETCH_NEXT</span></span>|  
|<span data-ttu-id="b035c-123">Uma linha acima</span><span class="sxs-lookup"><span data-stu-id="b035c-123">Line up</span></span>|<span data-ttu-id="b035c-124">SQL_FETCH_RELATIVE com FetchOffset igual a-1</span><span class="sxs-lookup"><span data-stu-id="b035c-124">SQL_FETCH_RELATIVE with FetchOffset equal to -1</span></span>|  
|<span data-ttu-id="b035c-125">Uma linha abaixo</span><span class="sxs-lookup"><span data-stu-id="b035c-125">Line down</span></span>|<span data-ttu-id="b035c-126">SQL_FETCH_RELATIVE com FetchOffset igual a 1</span><span class="sxs-lookup"><span data-stu-id="b035c-126">SQL_FETCH_RELATIVE with FetchOffset equal to 1</span></span>|  
|<span data-ttu-id="b035c-127">Caixa de rolagem no início</span><span class="sxs-lookup"><span data-stu-id="b035c-127">Scroll box to top</span></span>|<span data-ttu-id="b035c-128">SQL_FETCH_FIRST</span><span class="sxs-lookup"><span data-stu-id="b035c-128">SQL_FETCH_FIRST</span></span>|  
|<span data-ttu-id="b035c-129">Caixa de rolagem no fim</span><span class="sxs-lookup"><span data-stu-id="b035c-129">Scroll box to bottom</span></span>|<span data-ttu-id="b035c-130">SQL_FETCH_LAST</span><span class="sxs-lookup"><span data-stu-id="b035c-130">SQL_FETCH_LAST</span></span>|  
|<span data-ttu-id="b035c-131">Posição aleatória da caixa de rolagem</span><span class="sxs-lookup"><span data-stu-id="b035c-131">Random scroll box position</span></span>|<span data-ttu-id="b035c-132">SQL_FETCH_ABSOLUTE</span><span class="sxs-lookup"><span data-stu-id="b035c-132">SQL_FETCH_ABSOLUTE</span></span>|  
  
## <a name="in-this-section"></a><span data-ttu-id="b035c-133">Nesta seção</span><span class="sxs-lookup"><span data-stu-id="b035c-133">In This Section</span></span>  
  
-   [<span data-ttu-id="b035c-134">Indicando linhas em ODBC</span><span class="sxs-lookup"><span data-stu-id="b035c-134">Bookmarking Rows in ODBC</span></span>](scrolling-and-fetching-rows-bookmarking-rows-in-odbc.md)  
  
## <a name="see-also"></a><span data-ttu-id="b035c-135">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b035c-135">See Also</span></span>  
 [<span data-ttu-id="b035c-136">Usando cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="b035c-136">Using Cursors &#40;ODBC&#41;</span></span>](using-cursors-odbc.md)  
  
  
