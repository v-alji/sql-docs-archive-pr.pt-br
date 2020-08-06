---
title: Lotes de instruções | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statements [ODBC], batches
- batches [ODBC]
- ODBC applications, statements
- multiple statements, batches
- SQLMoreResults function
- SQLExecDirect function
ms.assetid: 057d7c1c-1428-4780-9447-a002ea741188
author: rothja
ms.author: jroth
ms.openlocfilehash: 4818b67766dafe851035041c8fd5137a0dfade73
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569418"
---
# <a name="batches-of-statements"></a><span data-ttu-id="45cac-102">Lotes de instruções</span><span class="sxs-lookup"><span data-stu-id="45cac-102">Batches of Statements</span></span>
  <span data-ttu-id="45cac-103">Um lote de [!INCLUDE[tsql](../../../includes/tsql-md.md)] instruções contém duas ou mais instruções, separadas por um ponto-e-vírgula (;), criado em uma única cadeia de caracteres passada para a função **SQLExecDirect** ou [SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360).</span><span class="sxs-lookup"><span data-stu-id="45cac-103">A batch of [!INCLUDE[tsql](../../../includes/tsql-md.md)] statements contains two or more statements, separated by a semicolon (;), built into a single string passed to **SQLExecDirect** or [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360).</span></span> <span data-ttu-id="45cac-104">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="45cac-104">For example:</span></span>  
  
```  
SQLExecDirect(hstmt,   
    "SELECT * FROM Authors; SELECT * FROM Titles",  
    SQL_NTS);  
```  
  
 <span data-ttu-id="45cac-105">Os lotes podem ser mais eficientes do que enviar instruções separadamente porque o tráfego de rede costuma ser reduzido.</span><span class="sxs-lookup"><span data-stu-id="45cac-105">Batches can be more efficient than submitting statements separately because network traffic is often reduced.</span></span> <span data-ttu-id="45cac-106">Use [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) para ficar posicionado no próximo conjunto de resultados quando terminar com o conjunto de resultados atual.</span><span class="sxs-lookup"><span data-stu-id="45cac-106">Use [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) to get positioned on the next result set when finished with the current result set.</span></span>  
  
 <span data-ttu-id="45cac-107">Os lotes sempre podem ser usados quando os atributos de cursor ODBC são definidos como os padrões de um cursor de somente encaminhamento, somente leitura, com um tamanho do conjunto de linhas igual a 1.</span><span class="sxs-lookup"><span data-stu-id="45cac-107">Batches can always be used when the ODBC cursor attributes are set to the defaults of a forward-only, read-only cursor with a rowset size of 1.</span></span>  
  
 <span data-ttu-id="45cac-108">Caso um lote seja executado durante o uso de cursores de servidor no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], o cursor de servidor é convertido implicitamente em um conjunto de resultados padrão.</span><span class="sxs-lookup"><span data-stu-id="45cac-108">If a batch is executed when using server cursors against [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)], the server cursor is implicitly converted to a default result set.</span></span> <span data-ttu-id="45cac-109">**SQLExecDirect** ou **SQLExecute** retornam SQL_SUCCESS_WITH_INFO e uma chamada para **SQLGetDiagRec** retorna:</span><span class="sxs-lookup"><span data-stu-id="45cac-109">**SQLExecDirect** or **SQLExecute** return SQL_SUCCESS_WITH_INFO, and a call to **SQLGetDiagRec** returns:</span></span>  
  
```  
szSqlState = "01S02", pfNativeError = 0  
szErrorMsg = "[Microsoft][SQL Server Native Server Native Client]Cursor type changed."  
```  
  
## <a name="see-also"></a><span data-ttu-id="45cac-110">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="45cac-110">See Also</span></span>  
 [<span data-ttu-id="45cac-111">Executando instruções &#40;&#41;ODBC</span><span class="sxs-lookup"><span data-stu-id="45cac-111">Executing Statements &#40;ODBC&#41;</span></span>](executing-statements-odbc.md)  
  
  
