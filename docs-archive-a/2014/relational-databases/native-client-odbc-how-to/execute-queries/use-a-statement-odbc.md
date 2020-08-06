---
title: Usar uma instrução (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- statements [ODBC]
ms.assetid: f7573f8f-6f21-4e03-8dd5-a5f2ea4878cc
author: rothja
ms.author: jroth
ms.openlocfilehash: 8ff3bc8c545cc9b55f0da3bb31d68d1ecbb5b547
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684712"
---
# <a name="use-a-statement-odbc"></a><span data-ttu-id="3d424-102">Usar uma instrução (ODBC)</span><span class="sxs-lookup"><span data-stu-id="3d424-102">Use a Statement (ODBC)</span></span>
    
### <a name="to-use-a-statement"></a><span data-ttu-id="3d424-103">Para usar uma instrução</span><span class="sxs-lookup"><span data-stu-id="3d424-103">To use a statement</span></span>  
  
1.  <span data-ttu-id="3d424-104">Chame [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) com um *HandleType* de SQL_HANDLE_STMT para alocar um identificador da instrução.</span><span class="sxs-lookup"><span data-stu-id="3d424-104">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a *HandleType* of SQL_HANDLE_STMT to allocate a statement handle.</span></span>  
  
2.  <span data-ttu-id="3d424-105">Outra opção é chamar o [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) para definir opções de instrução ou [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) para obter atributos de instrução.</span><span class="sxs-lookup"><span data-stu-id="3d424-105">Optionally, call [SQLSetStmtAttr](../../native-client-odbc-api/sqlsetstmtattr.md) to set statement options or [SQLGetStmtAttr](../../native-client-odbc-api/sqlgetstmtattr.md) to get statement attributes.</span></span>  
  
     <span data-ttu-id="3d424-106">Para usar cursores de servidor, você deve definir atributos de cursor como valores diferente de seus padrões.</span><span class="sxs-lookup"><span data-stu-id="3d424-106">To use server cursors, you must set cursor attributes to values other than their defaults.</span></span>  
  
3.  <span data-ttu-id="3d424-107">Opcionalmente, se a instrução for executada várias vezes, prepare a instrução para execução com a [Função SQLPrepare](https://go.microsoft.com/fwlink/?LinkId=59360).</span><span class="sxs-lookup"><span data-stu-id="3d424-107">Optionally, if the statement will be executed several times, prepare the statement for execution with [SQLPrepare Function](https://go.microsoft.com/fwlink/?LinkId=59360).</span></span>  
  
4.  <span data-ttu-id="3d424-108">Opcionalmente, se a instrução associou marcadores de parâmetro, associe os marcadores de parâmetro para programar variáveis usando [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span><span class="sxs-lookup"><span data-stu-id="3d424-108">Optionally, if the statement has bound parameter markers, bind the parameter markers to program variables by using [SQLBindParameter](../../native-client-odbc-api/sqlbindparameter.md).</span></span> <span data-ttu-id="3d424-109">Se a instrução tiver sido preparada, você poderá chamar [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) e [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) para localizar o número e características dos parâmetros.</span><span class="sxs-lookup"><span data-stu-id="3d424-109">If the statement was prepared, you can call [SQLNumParams](https://go.microsoft.com/fwlink/?LinkId=58404) and [SQLDescribeParam](../../native-client-odbc-api/sqldescribeparam.md) to find the number and characteristics of the parameters.</span></span>  
  
5.  <span data-ttu-id="3d424-110">Execute uma instrução diretamente usando SQLExecDirect.</span><span class="sxs-lookup"><span data-stu-id="3d424-110">Execute a statement directly by using SQLExecDirect.</span></span>  
  
     <span data-ttu-id="3d424-111">\- ou –</span><span class="sxs-lookup"><span data-stu-id="3d424-111">\- or -</span></span>  
  
     <span data-ttu-id="3d424-112">Se a instrução tiver sido preparada, execute-a várias vezes usando [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400).</span><span class="sxs-lookup"><span data-stu-id="3d424-112">If the statement was prepared, execute it multiple times by using [SQLExecute](https://go.microsoft.com/fwlink/?LinkId=58400).</span></span>  
  
     <span data-ttu-id="3d424-113">\- ou –</span><span class="sxs-lookup"><span data-stu-id="3d424-113">\- or -</span></span>  
  
     <span data-ttu-id="3d424-114">Chame uma função de catálogo, que retorna resultados.</span><span class="sxs-lookup"><span data-stu-id="3d424-114">Call a catalog function, which returns results.</span></span>  
  
6.  <span data-ttu-id="3d424-115">Processe os resultados associando as colunas de conjunto de resultados a variáveis do programa, movendo dados das colunas do conjunto de resultados para programar variáveis usando [SQLGetData](../../native-client-odbc-api/sqlgetdata.md) ou uma combinação de dois métodos.</span><span class="sxs-lookup"><span data-stu-id="3d424-115">Process the results by binding the result set columns to program variables, by moving data from the result set columns to program variables by using [SQLGetData](../../native-client-odbc-api/sqlgetdata.md), or a combination of the two methods.</span></span>  
  
     <span data-ttu-id="3d424-116">Busque uma linha de cada vez no conjunto de resultados de uma instrução.</span><span class="sxs-lookup"><span data-stu-id="3d424-116">Fetch through the result set of a statement one row at a time.</span></span>  
  
     <span data-ttu-id="3d424-117">\- ou –</span><span class="sxs-lookup"><span data-stu-id="3d424-117">\- or -</span></span>  
  
     <span data-ttu-id="3d424-118">Busque várias linhas por vez no conjunto de resultados usando um cursor em bloco.</span><span class="sxs-lookup"><span data-stu-id="3d424-118">Fetch through the result set several rows at a time by using a block cursor.</span></span>  
  
     <span data-ttu-id="3d424-119">\- ou –</span><span class="sxs-lookup"><span data-stu-id="3d424-119">\- or -</span></span>  
  
     <span data-ttu-id="3d424-120">Chame [SQLRowCount](../../native-client-odbc-api/sqlrowcount.md) para determinar o número de linhas afetadas por uma instrução INSERT, UPDATE ou DELETE.</span><span class="sxs-lookup"><span data-stu-id="3d424-120">Call [SQLRowCount](../../native-client-odbc-api/sqlrowcount.md) to determine the number of rows affected by an INSERT, UPDATE, or DELETE statement.</span></span>  
  
     <span data-ttu-id="3d424-121">Se a instrução SQL tiver vários conjuntos de resultados, chame [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) no fim de cada conjunto de resultados para ver se há outros conjuntos de resultados para processar.</span><span class="sxs-lookup"><span data-stu-id="3d424-121">If the SQL statement can have multiple result sets, call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) at the end of each result set to see if there are additional result sets to process.</span></span>  
  
7.  <span data-ttu-id="3d424-122">Depois que os resultados forem processados, as ações a seguir poderão ser necessárias para tornar o identificador da instrução disponível para executar uma nova instrução:</span><span class="sxs-lookup"><span data-stu-id="3d424-122">After results are processed, the following actions may be necessary to make the statement handle available to execute a new statement:</span></span>  
  
    -   <span data-ttu-id="3d424-123">Se você não tiver chamado [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) até ele retornar SQL_NO_DATA, chame [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) para fechar o cursor.</span><span class="sxs-lookup"><span data-stu-id="3d424-123">If you did not call [SQLMoreResults](../../native-client-odbc-api/sqlmoreresults.md) until it returned SQL_NO_DATA, call [SQLCloseCursor](../../native-client-odbc-api/sqlclosecursor.md) to close the cursor.</span></span>  
  
    -   <span data-ttu-id="3d424-124">Se você associar marcadores de parâmetro para programar variáveis, chame [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) com *Option* definido como SQL_RESET_PARAMS para liberar os parâmetros associados.</span><span class="sxs-lookup"><span data-stu-id="3d424-124">If you bound parameter markers to program variables, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with *Option* set to SQL_RESET_PARAMS to free the bound parameters.</span></span>  
  
    -   <span data-ttu-id="3d424-125">Se você associar colunas do conjunto de resultados para programar variáveis, chame [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) com *Option* definido como SQL_UNBIND para liberar as colunas associadas.</span><span class="sxs-lookup"><span data-stu-id="3d424-125">If you bound result set columns to program variables, call [SQLFreeStmt](../../native-client-odbc-api/sqlfreestmt.md) with *Option* set to SQL_UNBIND to free the bound columns.</span></span>  
  
    -   <span data-ttu-id="3d424-126">Para reutilizar o identificador de instrução, vá para Etapa 2.</span><span class="sxs-lookup"><span data-stu-id="3d424-126">To reuse the statement handle, go to Step 2.</span></span>  
  
8.  <span data-ttu-id="3d424-127">Chame [SQLFreeHandle](../../native-client-odbc-api/sqlfreehandle.md) com um *HandleType* de SQL_HANDLE_STMT para liberar o identificador de instrução.</span><span class="sxs-lookup"><span data-stu-id="3d424-127">Call [SQLFreeHandle](../../native-client-odbc-api/sqlfreehandle.md) with a *HandleType* of SQL_HANDLE_STMT to free the statement handle.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="3d424-128">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3d424-128">See Also</span></span>  
 [<span data-ttu-id="3d424-129">Tópicos de instruções sobre como executar consultas &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="3d424-129">Executing Queries How-to Topics &#40;ODBC&#41;</span></span>](executing-queries-how-to-topics-odbc.md)  
  
  
