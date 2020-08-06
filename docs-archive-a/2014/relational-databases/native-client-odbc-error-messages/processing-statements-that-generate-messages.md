---
title: Processando instruções que geram mensagens | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- PRINT statement
- messages [ODBC], statements generating messages
- statements [ODBC], message generation
- errors [ODBC], statements generating messages
- SQL Server Native Client ODBC driver, errors
- STATISTICS IO option
- STATISTICS TIME option
- DBCC statements
- SQLExecute function
- RAISERROR statement
- SQLGetDiagRec function
- ODBC error handling, statements generating messages
- SQLExecDirect function
ms.assetid: 672ebdc5-7fa1-4ceb-8d52-fd25ef646654
author: rothja
ms.author: jroth
ms.openlocfilehash: c26376eabb756d356dd71fb3bd8284a6b11dced7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679945"
---
# <a name="processing-statements-that-generate-messages"></a><span data-ttu-id="e39c1-102">Processando instruções que geram mensagens</span><span class="sxs-lookup"><span data-stu-id="e39c1-102">Processing Statements That Generate Messages</span></span>
  <span data-ttu-id="e39c1-103">As opções STATISTICS TIME e STATISTICS IO da instrução SET do [!INCLUDE[tsql](../../includes/tsql-md.md)] são usadas para obter informações que auxiliem a diagnosticar consultas de longa execução.</span><span class="sxs-lookup"><span data-stu-id="e39c1-103">The [!INCLUDE[tsql](../../includes/tsql-md.md)] SET statement options STATISTICS TIME and STATISTICS IO are used to get information that aids in diagnosing long-running queries.</span></span> <span data-ttu-id="e39c1-104">As versões anteriores do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] também dão suporte à opção SHOWPLAN para analisar planos de consulta.</span><span class="sxs-lookup"><span data-stu-id="e39c1-104">Earlier versions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] also support the SHOWPLAN option for analyzing query plans.</span></span> <span data-ttu-id="e39c1-105">Um aplicativo ODBC pode definir essas opções executando as seguintes instruções:</span><span class="sxs-lookup"><span data-stu-id="e39c1-105">An ODBC application can set these options by executing the following statements:</span></span>  
  
```  
SQLExecDirect(hstmt, "SET SHOWPLAN ON", SQL_NTS);  
SQLExecDirect(hstmt, "SET STATISTICS TIME ON", SQL_NTS90  
);  
SQLExecDirect(hstmt, "SET STATISTICS IO ON", SQL_NTS);  
```  
  
 <span data-ttu-id="e39c1-106">Quando SET STATISTICs TIME ou SET SHOWPLAN são ON, **SQLExecute** e **SQLExecDirect** retornam SQL_SUCCESS_WITH_INFO e, nesse ponto, o aplicativo pode recuperar o SHOWPLAN ou a saída de tempo de estatísticas chamando **SQLGetDiagRec** até que ele retorne SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="e39c1-106">When SET STATISTICS TIME or SET SHOWPLAN are ON, **SQLExecute** and **SQLExecDirect** return SQL_SUCCESS_WITH_INFO, and, at that point, the application can retrieve the SHOWPLAN or STATISTICS TIME output by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span> <span data-ttu-id="e39c1-107">Cada linha de dados de SHOWPLAN volta no formato:</span><span class="sxs-lookup"><span data-stu-id="e39c1-107">Each line of SHOWPLAN data comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError=6223,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]   
              Table Scan"  
```  
  
 <span data-ttu-id="e39c1-108">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] versão 7.0 substituiu a opção SHOWPLAN por SHOWPLAN_ALL e SHOWPLAN_TEXT, que retornam a saída como um conjunto de resultados e não um conjunto de mensagens.</span><span class="sxs-lookup"><span data-stu-id="e39c1-108">[!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] version 7.0 replaced the SHOWPLAN option with SHOWPLAN_ALL and SHOWPLAN_TEXT, both of which return output as a result set, not a set of messages.</span></span>  
  
 <span data-ttu-id="e39c1-109">Cada linha de STATISTICS TIME volta no formato:</span><span class="sxs-lookup"><span data-stu-id="e39c1-109">Each line of STATISTICS TIME comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError= 3613,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
   SQL Server Parse and Compile Time: cpu time = 0 ms."  
```  
  
 <span data-ttu-id="e39c1-110">A saída de SET STATISTICS IO não está disponível até o final de um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="e39c1-110">The output of SET STATISTICS IO is not available until the end of a result set.</span></span> <span data-ttu-id="e39c1-111">Para obter estatísticas de saída de e/s, o aplicativo chama **SQLGetDiagRec** no momento em que **SQLFetch** ou [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md) retorna SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="e39c1-111">To get STATISTICS IO output, the application calls **SQLGetDiagRec** at the time **SQLFetch** or [SQLFetchScroll](../native-client-odbc-api/sqlfetchscroll.md) returns SQL_NO_DATA.</span></span> <span data-ttu-id="e39c1-112">A saída de STATISTICS IO volta no formato:</span><span class="sxs-lookup"><span data-stu-id="e39c1-112">The output of STATISTICS IO comes back in the format:</span></span>  
  
```  
szSqlState="01000", *pfNativeError= 3615,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Table: testshow  scan count 1,  logical reads: 1,  
   physical reads: 0."  
```  
  
## <a name="using-dbcc-statements"></a><span data-ttu-id="e39c1-113">Usando instruções DBCC</span><span class="sxs-lookup"><span data-stu-id="e39c1-113">Using DBCC Statements</span></span>  
 <span data-ttu-id="e39c1-114">As instruções DBCC retornam seus dados como mensagens, não como conjuntos de resultados.</span><span class="sxs-lookup"><span data-stu-id="e39c1-114">DBCC statements return their data as messages, not result sets.</span></span> <span data-ttu-id="e39c1-115">**SQLExecDirect** ou **SQLExecute** retornam SQL_SUCCESS_WITH_INFO e o aplicativo recupera a saída chamando **SQLGetDiagRec** até que ela retorne SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="e39c1-115">**SQLExecDirect** or **SQLExecute** return SQL_SUCCESS_WITH_INFO, and the application retrieves the output by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span>  
  
 <span data-ttu-id="e39c1-116">Por exemplo, a instrução a seguir retorna SQL_SUCCESS_WITH_INFO:</span><span class="sxs-lookup"><span data-stu-id="e39c1-116">For example, the following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect(hstmt, "DBCC CHECKTABLE(Authors)", SQL_NTS);  
```  
  
 <span data-ttu-id="e39c1-117">Chamadas para retorno de **SQLGetDiagRec** :</span><span class="sxs-lookup"><span data-stu-id="e39c1-117">Calls to **SQLGetDiagRec** return:</span></span>  
  
```  
szSqlState = "01000", *pfNativeError = 2536,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Checking authors"  
szSqlState = "01000", *pfNativeError = 2579,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   The total number of data pages in this table is 1."  
szSqlState = "01000", *pfNativeError = 7929,  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   Table has 23 data rows."  
szSqlState = "01000", *pfNativeError = 2528  
szErrorMsg="[Microsoft][ SQL Server Native Client][SQL Server]  
   DBCC execution completed. If DBCC printed error messages,  
   see your System Administrator."  
```  
  
## <a name="using-print-and-raiserror-statements"></a><span data-ttu-id="e39c1-118">Usando as instruções PRINT e RAISERROR</span><span class="sxs-lookup"><span data-stu-id="e39c1-118">Using PRINT and RAISERROR Statements</span></span>  
 [!INCLUDE[tsql](../../includes/tsql-md.md)]<span data-ttu-id="e39c1-119">As instruções PRINT e RAISERROR também retornam dados chamando **SQLGetDiagRec**.</span><span class="sxs-lookup"><span data-stu-id="e39c1-119">PRINT and RAISERROR statements also return data by calling **SQLGetDiagRec**.</span></span> <span data-ttu-id="e39c1-120">As instruções PRINT fazem com que a execução da instrução SQL retorne SQL_SUCCESS_WITH_INFO, e uma chamada subsequente para **SQLGetDiagRec** retorna um *SQLSTATE* de 01000.</span><span class="sxs-lookup"><span data-stu-id="e39c1-120">PRINT statements cause the SQL statement execution to return SQL_SUCCESS_WITH_INFO, and a subsequent call to **SQLGetDiagRec** returns a *SQLState* of 01000.</span></span> <span data-ttu-id="e39c1-121">Um RAISERROR com uma severidade de dez ou menor se comporta da mesma forma que PRINT.</span><span class="sxs-lookup"><span data-stu-id="e39c1-121">A RAISERROR with a severity of ten or lower behaves the same as PRINT.</span></span> <span data-ttu-id="e39c1-122">Um RAISERROR com uma severidade de 11 ou superior faz com que a execução seja retornada SQL_ERROR, e uma chamada subsequente para **SQLGetDiagRec** retorna *SQLSTATE* 42000.</span><span class="sxs-lookup"><span data-stu-id="e39c1-122">A RAISERROR with a severity of 11 or higher causes the execute to return SQL_ERROR, and a subsequent call to **SQLGetDiagRec** returns *SQLState* 42000.</span></span> <span data-ttu-id="e39c1-123">Por exemplo, a instrução a seguir retorna SQL_SUCCESS_WITH_INFO:</span><span class="sxs-lookup"><span data-stu-id="e39c1-123">For example, the following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect (hstmt, "PRINT  'Some message' ", SQL_NTS);  
```  
  
 <span data-ttu-id="e39c1-124">Chamar **SQLGetDiagRec** retorna:</span><span class="sxs-lookup"><span data-stu-id="e39c1-124">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "01000", *pfNative Error = 0,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Some message"  
```  
  
 <span data-ttu-id="e39c1-125">A instrução a seguir retorna SQL_SUCCESS_WITH_INFO:</span><span class="sxs-lookup"><span data-stu-id="e39c1-125">The following statement returns SQL_SUCCESS_WITH_INFO:</span></span>  
  
```  
SQLExecDirect (hstmt, "RAISERROR ('Sample error 1.', 10, -1)",  
   SQL_NTS)  
```  
  
 <span data-ttu-id="e39c1-126">Chamar **SQLGetDiagRec** retorna:</span><span class="sxs-lookup"><span data-stu-id="e39c1-126">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "01000", *pfNative Error = 50000,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Sample error 1."  
```  
  
 <span data-ttu-id="e39c1-127">A instrução a seguir retorna SQL_ERROR:</span><span class="sxs-lookup"><span data-stu-id="e39c1-127">The following statement returns SQL_ERROR:</span></span>  
  
```  
SQLExecDirect (hstmt, "RAISERROR ('Sample error 2.', 11, -1)", SQL_NTS)  
```  
  
 <span data-ttu-id="e39c1-128">Chamar **SQLGetDiagRec** retorna:</span><span class="sxs-lookup"><span data-stu-id="e39c1-128">Calling **SQLGetDiagRec** returns:</span></span>  
  
```  
szSQLState = "42000", *pfNative Error = 50000,  
szErrorMsg= "[Microsoft] [SQL Server Native Client][SQL Server]  
   Sample error 2."  
```  
  
 <span data-ttu-id="e39c1-129">O tempo de chamar **SQLGetDiagRec** é crítico quando a saída de instruções PRINT ou RAISERROR é incluída em um conjunto de resultados.</span><span class="sxs-lookup"><span data-stu-id="e39c1-129">The timing of calling **SQLGetDiagRec** is critical when output from PRINT or RAISERROR statements is included in a result set.</span></span> <span data-ttu-id="e39c1-130">A chamada para **SQLGetDiagRec** para recuperar a saída de impressão ou RAISERROR deve ser feita imediatamente após a instrução que recebe SQL_ERROR ou SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="e39c1-130">The call to **SQLGetDiagRec** to retrieve the PRINT or RAISERROR output must be made immediately after the statement that receives SQL_ERROR or SQL_SUCCESS_WITH_INFO.</span></span> <span data-ttu-id="e39c1-131">Isto é direto quando apenas uma única instrução SQL é executada, como nos exemplos acima.</span><span class="sxs-lookup"><span data-stu-id="e39c1-131">This is straightforward when only a single SQL statement is executed, as in the examples above.</span></span> <span data-ttu-id="e39c1-132">Nesses casos, a chamada para **SQLExecDirect** ou **SQLExecute** retorna SQL_ERROR ou SQL_SUCCESS_WITH_INFO e o **SQLGetDiagRec** , em seguida, pode ser chamado.</span><span class="sxs-lookup"><span data-stu-id="e39c1-132">In these cases, the call to **SQLExecDirect** or **SQLExecute** returns SQL_ERROR or SQL_SUCCESS_WITH_INFO and **SQLGetDiagRec** can then be called.</span></span> <span data-ttu-id="e39c1-133">Isso é menos direto quando ao codificar loops para tratar a saída de um lote de instruções SQL ou ao executar procedimentos armazenados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="e39c1-133">It is less straightforward when coding loops to handle the output of a batch of SQL statements or when executing [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] stored procedures.</span></span>  
  
 <span data-ttu-id="e39c1-134">Neste caso, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] retorna um conjunto de resultados para cada instrução SELECT executada em um lote ou um procedimento armazenado.</span><span class="sxs-lookup"><span data-stu-id="e39c1-134">In this case, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] returns a result set for every SELECT statement executed in a batch or stored procedure.</span></span> <span data-ttu-id="e39c1-135">Se o lote ou o procedimento contiver instruções PRINT ou RAISERROR, sua saída será intercalada com os conjuntos de resultados da instrução SELECT.</span><span class="sxs-lookup"><span data-stu-id="e39c1-135">If the batch or procedure contains PRINT or RAISERROR statements, the output for these is interleaved with the SELECT statement result sets.</span></span> <span data-ttu-id="e39c1-136">Se a primeira instrução no lote ou procedimento for uma impressão ou um RAISERROR, o **SQLExecute** ou **SQLExecDirect** retornará SQL_SUCCESS_WITH_INFO ou SQL_ERROR, e o aplicativo precisará chamar **SQLGetDiagRec** até que ele retorne SQL_NO_DATA para recuperar as informações de impressão ou RAISERROR.</span><span class="sxs-lookup"><span data-stu-id="e39c1-136">If the first statement in the batch or procedure is a PRINT or RAISERROR, the **SQLExecute** or **SQLExecDirect** returns SQL_SUCCESS_WITH_INFO or SQL_ERROR, and the application needs to call **SQLGetDiagRec** until it returns SQL_NO_DATA to retrieve the PRINT or RAISERROR information.</span></span>  
  
 <span data-ttu-id="e39c1-137">Se a instrução PRINT ou RAISERROR vier após uma instrução SQL (como uma instrução SELECT), as informações PRINT ou RAISERROR serão retornadas quando [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md)Positions no conjunto de resultados que contém o erro.</span><span class="sxs-lookup"><span data-stu-id="e39c1-137">If the PRINT or RAISERROR statement comes after an SQL statement (such as a SELECT statement), then the PRINT or RAISERROR information is returned when [SQLMoreResults](../native-client-odbc-api/sqlmoreresults.md)positions on the result set containing the error.</span></span> <span data-ttu-id="e39c1-138">**SQLMoreResults** retorna SQL_SUCCESS_WITH_INFO ou SQL_ERROR dependendo da severidade da mensagem.</span><span class="sxs-lookup"><span data-stu-id="e39c1-138">**SQLMoreResults** returns SQL_SUCCESS_WITH_INFO or SQL_ERROR depending on the severity of the message.</span></span> <span data-ttu-id="e39c1-139">As mensagens são recuperadas chamando **SQLGetDiagRec** até que ela retorne SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="e39c1-139">Messages are retrieved by calling **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e39c1-140">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e39c1-140">See Also</span></span>  
 [<span data-ttu-id="e39c1-141">Tratando de erros e mensagens</span><span class="sxs-lookup"><span data-stu-id="e39c1-141">Handling Errors and Messages</span></span>](handling-errors-and-messages.md)  
  
  
