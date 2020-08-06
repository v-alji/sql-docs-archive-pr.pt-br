---
title: SQLGetData | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetData function
ms.assetid: 204848be-8787-45b4-816f-a60ac9d56fcf
author: rothja
ms.author: jroth
ms.openlocfilehash: c351cf7340bc7b0afeb76b139bd75aa429f56e10
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568547"
---
# <a name="sqlgetdata"></a><span data-ttu-id="beef4-102">SQLGetData</span><span class="sxs-lookup"><span data-stu-id="beef4-102">SQLGetData</span></span>
  <span data-ttu-id="beef4-103">**SQLGetData** é usado para recuperar dados de conjunto de resultados sem valores de coluna de associação.</span><span class="sxs-lookup"><span data-stu-id="beef4-103">**SQLGetData** is used to retrieve result set data without binding column values.</span></span> <span data-ttu-id="beef4-104">**SQLGetData** pode ser chamado sucessivamente na mesma coluna para recuperar grandes quantidades de dados em uma coluna com um tipo de dados **text**, **ntext**ou **image** .</span><span class="sxs-lookup"><span data-stu-id="beef4-104">**SQLGetData** can be called successively on the same column to retrieve large amounts of data from a column with a **text**, **ntext**, or **image** data type.</span></span>  
  
 <span data-ttu-id="beef4-105">Não há nenhum requisito de que aplicativo associe variáveis para buscar dados de conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="beef4-105">There is no requirement that an application bind variables to fetch result set data.</span></span> <span data-ttu-id="beef4-106">Os dados de qualquer coluna podem ser recuperados no driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client usando **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="beef4-106">The data of any column can be retrieved from the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver by using **SQLGetData**.</span></span>  
  
 <span data-ttu-id="beef4-107">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client não oferece suporte ao uso de **SQLGetData** para recuperar dados em ordem de coluna aleatória.</span><span class="sxs-lookup"><span data-stu-id="beef4-107">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver does not support using **SQLGetData** to retrieve data in random column order.</span></span> <span data-ttu-id="beef4-108">Todas as colunas desassociadas processadas com **SQLGetData** devem ter ordinais de coluna mais altos que as colunas associadas no conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="beef4-108">All unbound columns processed with **SQLGetData** must have higher column ordinals than the bound columns in the result set.</span></span> <span data-ttu-id="beef4-109">O aplicativo deve processar dados do valor de coluna ordinal mais baixo desassociado para o mais alto.</span><span class="sxs-lookup"><span data-stu-id="beef4-109">The application must process data from the lowest unbound ordinal column value to the highest.</span></span> <span data-ttu-id="beef4-110">Tentar recuperar dados de uma coluna ordinalmente inferior resulta em um erro.</span><span class="sxs-lookup"><span data-stu-id="beef4-110">Attempting to retrieve data from a lower ordinally numbered column results in an error.</span></span> <span data-ttu-id="beef4-111">Caso esteja usando cursores de servidor para informar linhas do conjunto de resultados, o aplicativo pode buscar novamente a linha atual e buscar o valor de uma coluna.</span><span class="sxs-lookup"><span data-stu-id="beef4-111">If the application is using server cursors to report result set rows, the application can refetch the current row and then fetch the value of a column.</span></span> <span data-ttu-id="beef4-112">Se uma instrução for executada no cursor somente de avanço, somente leitura, você deverá executar novamente a instrução para fazer backup de **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="beef4-112">If a statement is executed on the default read-only, forward-only cursor, you must re-execute the statement to back up **SQLGetData**.</span></span>  
  
 <span data-ttu-id="beef4-113">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client informa o comprimento de **text**com precisão, dos dados **ntext**e **image** recuperados usando **SQLGetData**.</span><span class="sxs-lookup"><span data-stu-id="beef4-113">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver accurately reports the length of **text**, **ntext**, and **image** data retrieved using **SQLGetData**.</span></span> <span data-ttu-id="beef4-114">O aplicativo pode usar bem o retorno do parâmetro *StrLen_or_IndPtr* para recuperar dados longos rapidamente.</span><span class="sxs-lookup"><span data-stu-id="beef4-114">The application can make good use of the *StrLen_or_IndPtr* parameter return to retrieve long data rapidly.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="beef4-115">Para tipos de valor grandes, *StrLen_or_IndPtr* retornará SQL_NO_TOTAL em caixas de truncamento de dados.</span><span class="sxs-lookup"><span data-stu-id="beef4-115">For large value types, *StrLen_or_IndPtr* will return SQL_NO_TOTAL in cases of data truncation.</span></span>  
  
## <a name="sqlgetdata-support-for-enhanced-date-and-time-features"></a><span data-ttu-id="beef4-116">Suporte de SQLGetData a recursos aprimorados de data e hora</span><span class="sxs-lookup"><span data-stu-id="beef4-116">SQLGetData Support for Enhanced Date and Time Features</span></span>  
 <span data-ttu-id="beef4-117">Os valores de coluna de resultado de tipos de data/hora são convertidos conforme descrito em [conversões de SQL para C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span><span class="sxs-lookup"><span data-stu-id="beef4-117">Result column values of date/time types are converted as described in [Conversions from SQL to C](../native-client-odbc-date-time/datetime-data-type-conversions-from-sql-to-c.md).</span></span>  
  
 <span data-ttu-id="beef4-118">Para obter mais informações, consulte [melhorias de data e hora &#40;&#41;ODBC ](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="beef4-118">For more information, see [Date and Time Improvements &#40;ODBC&#41;](../native-client-odbc-date-time/date-and-time-improvements-odbc.md).</span></span>  
  
## <a name="sqlgetdata-support-for-large-clr-udts"></a><span data-ttu-id="beef4-119">Suporte de SQLGetData a UDTs grandes do CLR</span><span class="sxs-lookup"><span data-stu-id="beef4-119">SQLGetData Support for Large CLR UDTs</span></span>  
 <span data-ttu-id="beef4-120">**SQLGetData** dá suporte a UDTs (tipos definidos pelo usuário) grandes do CLR.</span><span class="sxs-lookup"><span data-stu-id="beef4-120">**SQLGetData** supports large CLR user-defined types (UDTs).</span></span> <span data-ttu-id="beef4-121">Para obter mais informações, consulte [tipos CLR grandes definidos pelo usuário &#40;&#41;ODBC ](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="beef4-121">For more information, see [Large CLR User-Defined Types &#40;ODBC&#41;](../native-client/odbc/large-clr-user-defined-types-odbc.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="beef4-122">Exemplo</span><span class="sxs-lookup"><span data-stu-id="beef4-122">Example</span></span>  
  
```  
SQLHDBC     hDbc = NULL;  
SQLHSTMT    hStmt = NULL;  
long        lEmpID;  
PBYTE       pPicture;  
SQLINTEGER  pIndicators[2];  
  
// Get an environment, connection, and so on.  
...  
  
// Get a statement handle and execute a command.  
SQLAllocHandle(SQL_HANDLE_STMT, hDbc, &hStmt);  
  
if (SQLExecDirect(hStmt,  
    (SQLCHAR*) "SELECT EmployeeID, Photo FROM Employees",  
    SQL_NTS) == SQL_ERROR)  
    {  
    // Handle error and return.  
    }  
  
// Retrieve data from row set.  
SQLBindCol(hStmt, 1, SQL_C_LONG, (SQLPOINTER) &lEmpID, sizeof(long),  
    &pIndicators[0]);  
  
while (SQLFetch(hStmt) == SQL_SUCCESS)  
    {  
    cout << "EmployeeID: " << lEmpID << "\n";  
  
    // Call SQLGetData to determine the amount of data that's waiting.  
    if (SQLGetData(hStmt, 2, SQL_C_BINARY, pPicture, 0, &pIndicators[1])  
        == SQL_SUCCESS_WITH_INFO)  
        {  
        cout << "Photo size: " pIndicators[1] << "\n\n";  
  
        // Get all the data at once.  
        pPicture = new BYTE[pIndicators[1]];  
        if (SQLGetData(hStmt, 2, SQL_C_DEFAULT, pPicture,  
            pIndicators[1], &pIndicators[1]) != SQL_SUCCESS)  
            {  
            // Handle error and continue.  
            }  
  
        delete [] pPicture;  
        }  
    else  
        {  
        // Handle error on attempt to get data length.  
        }  
    }  
```  
  
## <a name="see-also"></a><span data-ttu-id="beef4-123">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="beef4-123">See Also</span></span>  
 <span data-ttu-id="beef4-124">[Função SQLGetData](https://go.microsoft.com/fwlink/?LinkId=59350) </span><span class="sxs-lookup"><span data-stu-id="beef4-124">[SQLGetData Function](https://go.microsoft.com/fwlink/?LinkId=59350) </span></span>  
 [<span data-ttu-id="beef4-125">ODBC API Implementation Details</span><span class="sxs-lookup"><span data-stu-id="beef4-125">ODBC API Implementation Details</span></span>](odbc-api-implementation-details.md)  
  
  
