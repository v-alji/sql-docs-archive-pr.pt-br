---
title: Conversões implícitas de cursor (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- ODBC cursors, implicit cursor conversions
- implicit cursor conversions
- cursors [ODBC], implicit cursor conversions
ms.assetid: fe29a58d-8448-4512-9ffd-b414784ba338
author: rothja
ms.author: jroth
ms.openlocfilehash: ff8350c71a853e39ff1d35a1f3fba6e8e1944934
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87576344"
---
# <a name="implicit-cursor-conversions-odbc"></a><span data-ttu-id="3124a-102">Conversões implícitas de cursor (ODBC)</span><span class="sxs-lookup"><span data-stu-id="3124a-102">Implicit Cursor Conversions (ODBC)</span></span>
  <span data-ttu-id="3124a-103">Os aplicativos podem solicitar um tipo de cursor por meio de [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) e, em seguida, executar uma instrução SQL que não tenha suporte de cursores de servidor do tipo solicitado.</span><span class="sxs-lookup"><span data-stu-id="3124a-103">Applications can request a cursor type through [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) and then execute an SQL statement that is not supported by server cursors of the type requested.</span></span> <span data-ttu-id="3124a-104">Uma chamada para **SQLExecute** ou **SQLExecDirect** retorna SQL_SUCCESS_WITH_INFO e **SQLGetDiagRec** retorna:</span><span class="sxs-lookup"><span data-stu-id="3124a-104">A call to **SQLExecute** or **SQLExecDirect** returns SQL_SUCCESS_WITH_INFO and **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState = "01S02", *pfNativeError = 0,  
szErrorMsg="[Microsoft][SQL Server Native Client] Cursor type changed"  
```  
  
 <span data-ttu-id="3124a-105">O aplicativo pode determinar que tipo de cursor está sendo usado agora chamando **SQLGetStmtOption** definido como SQL_CURSOR_TYPE.</span><span class="sxs-lookup"><span data-stu-id="3124a-105">The application can determine what type of cursor is now being used by calling **SQLGetStmtOption** set to SQL_CURSOR_TYPE.</span></span> <span data-ttu-id="3124a-106">A conversão do tipo de cursor se aplica somente a uma instrução.</span><span class="sxs-lookup"><span data-stu-id="3124a-106">The cursor type conversion applies to only one statement.</span></span> <span data-ttu-id="3124a-107">O próximo **SQLExecDirect** ou **SQLExecute** será feito usando as configurações de cursor da instrução original.</span><span class="sxs-lookup"><span data-stu-id="3124a-107">The next **SQLExecDirect** or **SQLExecute** will be done using the original statement cursor settings.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3124a-108">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3124a-108">See Also</span></span>  
 [<span data-ttu-id="3124a-109">Detalhes de programação do cursor &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="3124a-109">Cursor Programming Details &#40;ODBC&#41;</span></span>](cursor-programming-details-odbc.md)  
  
  
