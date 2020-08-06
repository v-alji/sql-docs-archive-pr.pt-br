---
title: Usar cursores (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- cursors [ODBC], how to topics
ms.assetid: c502736f-bca0-45c3-ae25-d2ad52d296bf
author: rothja
ms.author: jroth
ms.openlocfilehash: e08156b03407c7a05d86278c11482a568d651f5f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568531"
---
# <a name="use-cursors-odbc"></a><span data-ttu-id="761fb-102">Usar cursores (ODBC)</span><span class="sxs-lookup"><span data-stu-id="761fb-102">Use Cursors (ODBC)</span></span>
    
### <a name="to-use-cursors"></a><span data-ttu-id="761fb-103">Para usar cursores</span><span class="sxs-lookup"><span data-stu-id="761fb-103">To use cursors</span></span>  
  
1.  <span data-ttu-id="761fb-104">Chame [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para definir os atributos de cursor desejados:</span><span class="sxs-lookup"><span data-stu-id="761fb-104">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the desired cursor attributes:</span></span>  
  
     <span data-ttu-id="761fb-105">Defina os atributos SQL_ATTR_CURSOR_TYPE e SQL_ATTR_CONCURRENCY (esta é a opção preferencial).</span><span class="sxs-lookup"><span data-stu-id="761fb-105">Set the SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY attributes (this is the preferred option).</span></span>  
  
     <span data-ttu-id="761fb-106">Ou</span><span class="sxs-lookup"><span data-stu-id="761fb-106">Or</span></span>  
  
     <span data-ttu-id="761fb-107">Defina os atributos SQL_CURSOR_SCROLLABLE e SQL_CURSOR_SENSITIVITY.</span><span class="sxs-lookup"><span data-stu-id="761fb-107">Set the SQL_CURSOR_SCROLLABLE and SQL_CURSOR_SENSITIVITY attributes.</span></span>  
  
2.  <span data-ttu-id="761fb-108">Chame [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para definir o tamanho do conjunto de linhas usando o atributo SQL_ATTR_ROW_ARRAY_SIZE.</span><span class="sxs-lookup"><span data-stu-id="761fb-108">Call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set the rowset size by using the SQL_ATTR_ROW_ARRAY_SIZE attribute.</span></span>  
  
3.  <span data-ttu-id="761fb-109">Outra opção será chamar [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) para definir um nome de cursor se as atualizações posicionadas forem feitas usando a cláusula WHERE CURRENT OF.</span><span class="sxs-lookup"><span data-stu-id="761fb-109">Optionally, call [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) to set a cursor name if positioned updates will be done by using the WHERE CURRENT OF clause.</span></span>  
  
4.  <span data-ttu-id="761fb-110">Execute a instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="761fb-110">Execute the SQL statement.</span></span>  
  
5.  <span data-ttu-id="761fb-111">Outra opção será chamar [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md) para definir o nome de cursor se as atualizações posicionadas forem feitas usando a cláusula WHERE CURRENT OF e um nome de cursor não foi fornecido com [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) na Etapa 3.</span><span class="sxs-lookup"><span data-stu-id="761fb-111">Optionally, call [SQLGetCursorName](../../native-client-odbc-api/sqlgetcursorname.md) to get the cursor name if positioned updates will be done by using the WHERE CURRENT OF clause and a cursor name was not supplied with [SQLSetCursorName](https://go.microsoft.com/fwlink/?LinkId=58406) in Step 3.</span></span>  
  
6.  <span data-ttu-id="761fb-112">Chame [SQLNumResultCols](../../native-client-odbc-api/sqlnumresultcols.md) para obter o número de colunas (C) no conjunto de linhas.</span><span class="sxs-lookup"><span data-stu-id="761fb-112">Call [SQLNumResultCols](../../native-client-odbc-api/sqlnumresultcols.md) to get the number of columns (C) in the rowset.</span></span>  
  
     <span data-ttu-id="761fb-113">Use a associação por coluna.</span><span class="sxs-lookup"><span data-stu-id="761fb-113">Use column-wise binding.</span></span>  
  
     <span data-ttu-id="761fb-114">\- ou –</span><span class="sxs-lookup"><span data-stu-id="761fb-114">\- or -</span></span>  
  
     <span data-ttu-id="761fb-115">Use a associação por linha.</span><span class="sxs-lookup"><span data-stu-id="761fb-115">Use row-wise binding.</span></span>  
  
7.  <span data-ttu-id="761fb-116">Busque conjuntos de linhas do cursor conforme desejado.</span><span class="sxs-lookup"><span data-stu-id="761fb-116">Fetch rowsets from the cursor as desired.</span></span>  
  
8.  <span data-ttu-id="761fb-117">Chame [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) para determinar se outro conjunto de resultados está disponível.</span><span class="sxs-lookup"><span data-stu-id="761fb-117">Call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) to determine if another result set is available.</span></span>  
  
    -   <span data-ttu-id="761fb-118">Se SQL_SUCCESS for retornado, outro conjunto de resultados estará disponível.</span><span class="sxs-lookup"><span data-stu-id="761fb-118">If it returns SQL_SUCCESS, another result set is available.</span></span>  
  
    -   <span data-ttu-id="761fb-119">Se SQL_NO_DATA for retornado, nenhum outro conjunto de resultados estará disponível.</span><span class="sxs-lookup"><span data-stu-id="761fb-119">If it returns SQL_NO_DATA, no more result sets are available.</span></span>  
  
    -   <span data-ttu-id="761fb-120">Se SQL_SUCCESS_WITH_INFO ou SQL_ERROR for retornado, chame [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) para determinar se a saída de uma instrução PRINT ou RAISERROR estará disponível.</span><span class="sxs-lookup"><span data-stu-id="761fb-120">If it returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, call [SQLGetDiagRec](https://go.microsoft.com/fwlink/?LinkId=58402) to determine if the output from a PRINT or RAISERROR statement is available.</span></span>  
  
     <span data-ttu-id="761fb-121">Se parâmetros de instrução associados forem usados para parâmetros de saída ou o valor retornado de um procedimento armazenado, use os dados disponíveis agora nos buffers de parâmetro associados.</span><span class="sxs-lookup"><span data-stu-id="761fb-121">If bound statement parameters are used for output parameters or the return value of a stored procedure, use the data now available in the bound parameter buffers.</span></span>  
  
     <span data-ttu-id="761fb-122">Quando são usados parâmetros associados, cada chamada para [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) ou [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) terá executado a instrução SQL por S vezes, em que S é o número de elementos na matriz de parâmetros associados.</span><span class="sxs-lookup"><span data-stu-id="761fb-122">When bound parameters are used, each call to [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400) or [SQLExecDirect](https://go.microsoft.com/fwlink/?LinkId=58399) will have executed the SQL statement S times, where S is the number of elements in the array of bound parameters.</span></span> <span data-ttu-id="761fb-123">Isso significa que haverá S conjuntos de resultados a ser processados, onde cada conjunto consiste em todos os conjuntos de resultados, parâmetros de saída e códigos de retorno normalmente retornados por uma única execução da instrução SQL.</span><span class="sxs-lookup"><span data-stu-id="761fb-123">This means that there will be S sets of results to process, where each set of results comprises all of the result sets, output parameters, and return codes usually returned by a single execution of the SQL statement.</span></span>  
  
     <span data-ttu-id="761fb-124">Observe que, quando um conjunto de resultados contém linhas computadas, cada linha computada é disponibilizada como um conjunto de resultados separado.</span><span class="sxs-lookup"><span data-stu-id="761fb-124">Note that when a result set contains compute rows, each compute row is made available as a separate result set.</span></span> <span data-ttu-id="761fb-125">Esses conjuntos de resultados computados são intercalados nas linhas normais e dividem as linhas normais em vários conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="761fb-125">These compute result sets are interspersed within the normal rows and break normal rows into multiple result sets.</span></span>  
  
9. <span data-ttu-id="761fb-126">Outra opção é chamar [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) com SQL_UNBIND para liberar qualquer buffer de coluna associado.</span><span class="sxs-lookup"><span data-stu-id="761fb-126">Optionally, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with SQL_UNBIND to release any bound column buffers.</span></span>  
  
10. <span data-ttu-id="761fb-127">Se outro conjunto de resultados estiver disponível, vá para a Etapa 6.</span><span class="sxs-lookup"><span data-stu-id="761fb-127">If another result set is available, go to Step 6.</span></span>  
  
     <span data-ttu-id="761fb-128">Na Etapa 9, chamar [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) em um conjunto de resultados parcialmente processado limpa o restante do conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="761fb-128">In Step 9, calling [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) on a partially processed result set clears the remainder of the result set.</span></span> <span data-ttu-id="761fb-129">Outra maneira de limpar um conjunto de resultados parcialmente processado é chamar [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md).</span><span class="sxs-lookup"><span data-stu-id="761fb-129">Another way to clear a partially processed result set is to call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md).</span></span>  
  
     <span data-ttu-id="761fb-130">Você pode controlar o tipo de cursor usado definindo SQL_ATTR_CURSOR_TYPE e SQL_ATTR_CONCURRENCY ou definindo SQL_ATTR_CURSOR_SENSITIVITY e SQL_ATTR_CURSOR_SCROLLABLE.</span><span class="sxs-lookup"><span data-stu-id="761fb-130">You can control the type of cursor used by setting either SQL_ATTR_CURSOR_TYPE and SQL_ATTR_CONCURRENCY, or by setting SQL_ATTR_CURSOR_SENSITIVITY and SQL_ATTR_CURSOR_SCROLLABLE.</span></span> <span data-ttu-id="761fb-131">Você não deve misturar os dois métodos de especificação de comportamento de cursor.</span><span class="sxs-lookup"><span data-stu-id="761fb-131">You should not mix the two methods of specifying cursor behavior.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="761fb-132">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="761fb-132">See Also</span></span>  
 [<span data-ttu-id="761fb-133">Tópicos de instruções sobre o uso de cursores &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="761fb-133">Using Cursors How-to Topics &#40;ODBC&#41;</span></span>](using-cursors-how-to-topics-odbc.md)  
  
  
