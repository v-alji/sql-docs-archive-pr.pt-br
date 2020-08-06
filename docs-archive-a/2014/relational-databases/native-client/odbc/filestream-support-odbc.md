---
title: Suporte a FILESTREAM (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/09/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- FILESTREAM [SQL Server], ODBC
- ODBC, FILESTREAM support
ms.assetid: 87982955-1542-4551-9c06-447ffe8193b9
author: rothja
ms.author: jroth
ms.openlocfilehash: e9b77a6a893c1c7c12e5fc14f23bf9fd719c689f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571363"
---
# <a name="filestream-support-odbc"></a><span data-ttu-id="327ce-102">Suporte a FILESTREAM (ODBC)</span><span class="sxs-lookup"><span data-stu-id="327ce-102">FILESTREAM Support (ODBC)</span></span>
  <span data-ttu-id="327ce-103">O ODBC no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client oferece suporte ao recurso FILESTREAM aprimorado.</span><span class="sxs-lookup"><span data-stu-id="327ce-103">ODBC in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client supports the enhanced FILESTREAM feature.</span></span> <span data-ttu-id="327ce-104">Para obter mais informações sobre esse recurso, consulte [suporte a FileStream](../features/filestream-support.md).</span><span class="sxs-lookup"><span data-stu-id="327ce-104">For more information about this feature, see [FILESTREAM Support](../features/filestream-support.md).</span></span> <span data-ttu-id="327ce-105">Para obter um exemplo que demonstra o suporte do ODB para FILESTREAM, consulte [Enviar e receber dados incrementalmente com FILESTREAM &#40;&#41;ODBC ](../../native-client-odbc-how-to/send-and-receive-data-incrementally-with-filestream-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="327ce-105">For a sample demonstrating ODB support for FILESTREAM, see [Send and Receive Data Incrementally with FILESTREAM &#40;ODBC&#41;](../../native-client-odbc-how-to/send-and-receive-data-incrementally-with-filestream-odbc.md).</span></span>  
  
 <span data-ttu-id="327ce-106">Para enviar e receber `varbinary(max)` valores maiores que 2 GB, um aplicativo deve associar parâmetros usando SQLBindParameter com *ColumnSize* definido como `SQL_SS_LENGTH_UNLIMITED` e definir o conteúdo de *StrLen_or_IndPtr* como antes de `SQL_DATA_AT_EXEC` SQLExecDirect ou SQLExecute.</span><span class="sxs-lookup"><span data-stu-id="327ce-106">To send and receive `varbinary(max)` values greater than 2 GB, an application must bind parameters by using SQLBindParameter with *ColumnSize* set to `SQL_SS_LENGTH_UNLIMITED`, and set the contents of *StrLen_or_IndPtr* to `SQL_DATA_AT_EXEC` before SQLExecDirect or SQLExecute.</span></span>  
  
 <span data-ttu-id="327ce-107">Assim como ocorre com qualquer parâmetro de dados em execução, os dados serão fornecidos com SQLParamData e SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="327ce-107">As with any data-at-execution parameter, the data will be supplied with SQLParamData and SQLPutData.</span></span>  
  
 <span data-ttu-id="327ce-108">Você pode chamar SQLGetData para buscar dados em partes de uma coluna FILESTREAM se a coluna não estiver associada a SQLBindCol.</span><span class="sxs-lookup"><span data-stu-id="327ce-108">You can call SQLGetData to fetch data in chunks for a FILESTREAM column if the column is not bound with SQLBindCol.</span></span>  
  
 <span data-ttu-id="327ce-109">Você pode atualizar dados FILESTREAM se ele estiver associado a SQLBindCol.</span><span class="sxs-lookup"><span data-stu-id="327ce-109">You can update FILESTREAM data if it is bound with SQLBindCol.</span></span>  
  
 <span data-ttu-id="327ce-110">Se você chamar SQLFetch em uma coluna associada, receberá um aviso de "dados truncados" se o buffer não for grande o suficiente para manter o valor inteiro.</span><span class="sxs-lookup"><span data-stu-id="327ce-110">If you call SQLFetch on a bound column, you will receive a "data truncated" warning if the buffer is not large enough to hold the entire value.</span></span> <span data-ttu-id="327ce-111">Ignore este aviso e atualize os dados nessa coluna associada com chamadas SQLParamData e SQLPutData.</span><span class="sxs-lookup"><span data-stu-id="327ce-111">Ignore this warning and update the data in this bound column with SQLParamData and SQLPutData calls.</span></span> <span data-ttu-id="327ce-112">Você pode atualizar dados FILESTREAM usando SQLSetPos se ele estiver associado a SQLBindCol.</span><span class="sxs-lookup"><span data-stu-id="327ce-112">You can update FILESTREAM data by using SQLSetPos if it is bound with SQLBindCol.</span></span>  
  
## <a name="example"></a><span data-ttu-id="327ce-113">Exemplo</span><span class="sxs-lookup"><span data-stu-id="327ce-113">Example</span></span>  
 <span data-ttu-id="327ce-114">Colunas de FILESTREAM se comportam exatamente como colunas `varbinary(max)`, mas sem um limite de tamanho.</span><span class="sxs-lookup"><span data-stu-id="327ce-114">FILESTREAM columns behave exactly like `varbinary(max)` columns, but without a size limit.</span></span> <span data-ttu-id="327ce-115">Elas são associadas como SQL_VARBINARY.</span><span class="sxs-lookup"><span data-stu-id="327ce-115">They are bound as SQL_VARBINARY.</span></span> <span data-ttu-id="327ce-116">(SQL_LONGVARBINARY é usado com colunas de imagem e há restrições neste tipo.</span><span class="sxs-lookup"><span data-stu-id="327ce-116">(SQL_LONGVARBINARY is used with image columns, and there are restrictions on this type.</span></span> <span data-ttu-id="327ce-117">Por exemplo, SQL_LONGVARBINARY Connot ser usado como um parâmetro de saída.) Os exemplos a seguir mostram o acesso direto do NTFS para colunas FILESTREAM.</span><span class="sxs-lookup"><span data-stu-id="327ce-117">For example, SQL_LONGVARBINARY connot be used as an output parameter.) The following examples show direct NTFS access for FILESTREAM columns.</span></span> <span data-ttu-id="327ce-118">Estes exemplos supõem que o seguinte código [!INCLUDE[tsql](../../../includes/tsql-md.md)] tenha sido executado no banco de dados:</span><span class="sxs-lookup"><span data-stu-id="327ce-118">These examples assume that the following [!INCLUDE[tsql](../../../includes/tsql-md.md)] code has been executed in the database:</span></span>  
  
```  
CREATE TABLE fileStreamDocs(  
id uniqueidentifier ROWGUIDCOL NOT NULL UNIQUE,  
author varchar(64),  
document VARBINARY(MAX) FILESTREAM NULL)  
```  
  
### <a name="read"></a><span data-ttu-id="327ce-119">Ler</span><span class="sxs-lookup"><span data-stu-id="327ce-119">Read</span></span>  
  
```  
void selectFilestream (LPCWSTR dstFilePath) {  
SQLRETURN r;  
SQLCHAR transactionToken[1024];  
SQLWCHAR srcFilePath[1024];  
SQLINTEGER cbTransactionToken, cbsrcFilePath;  
  
// The GUID columns must be visible to the query,   
// even if it is not used  
r = SQLExecDirect(hstmt, (SQLTCHAR *)   
_T("select GET_FILESTREAM_TRANSACTION_CONTEXT(); \  
select TOP(1) id, document.PathName() \  
from fileStreamDocs WHERE author = 'Chris Lee'"),   
SQL_NTS);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLFetch(hstmt);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLGetData(hstmt, 1, SQL_C_BINARY,   
transactionToken, sizeof(transactionToken), &cbTransactionToken);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLMoreResults(hstmt);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLFetch(hstmt);  
r = SQLGetData(hstmt, 2, SQL_C_TCHAR,   
srcFilePath, sizeof(srcFilePath), &cbsrcFilePath);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
if (!copyFileFromSql(srcFilePath, dstFilePath, transactionToken, cbTransactionToken)) {  
DeleteFile(dstFilePath);  
}  
r = SQLTransact(henv, hdbc, SQL_ROLLBACK);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
}  
```  
  
### <a name="insert"></a><span data-ttu-id="327ce-120">Inserir</span><span class="sxs-lookup"><span data-stu-id="327ce-120">Insert</span></span>  
  
```  
void insertFilestream(LPCWSTR srcFilePath) {  
SQLRETURN r;  
SQLCHAR transactionToken[64];  
SQLWCHAR dstFilePath[1024];  
SQLINTEGER cbTransactionToken, cbDstFilePath;  
SQLUSMALLINT mode;  
  
r = SQLExecDirect(hstmt, (SQLTCHAR *)   
_T("insert into fileStreamDocs (id, author, document)\  
    output Get_Filestream_Transaction_Context(), inserted.document.PathName() \  
        values (newid(), 'Chris Lee', convert(varbinary, '**Temp**')) "), SQL_NTS);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLFetch(hstmt);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLGetData(hstmt, 1, SQL_C_BINARY,  
transactionToken, sizeof(transactionToken), &cbTransactionToken);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLGetData(hstmt, 2, SQL_C_TCHAR,  
dstFilePath, sizeof(dstFilePath), &cbDstFilePath);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
r = SQLCloseCursor(hstmt);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
  
if (copyFileToSql(  
srcFilePath, dstFilePath,   
transactionToken, cbTransactionToken)) {  
mode = SQL_COMMIT;  
}  
else {  
mode = SQL_ROLLBACK;  
}  
  
r = SQLTransact(henv, hdbc, mode);  
if (r != SQL_SUCCESS && r!=SQL_SUCCESS_WITH_INFO) {  
ODBCError(henv, hdbc, hstmt, NULL, true); exit(-1);  
}  
}  
```  
  
### <a name="helper-routines"></a><span data-ttu-id="327ce-121">Rotinas auxiliares</span><span class="sxs-lookup"><span data-stu-id="327ce-121">Helper Routines</span></span>  
  
```  
#define COPYBUFFERSIZE 4096  
BOOL copyFileContents (HANDLE srcHandle, HANDLE dstHandle) {  
  
BYTE buffer[COPYBUFFERSIZE];  
DWORD bytesRead, bytesWritten;  
BOOL r;  
  
do {  
r = ReadFile(srcHandle, buffer, COPYBUFFERSIZE, &bytesRead,NULL);  
if (bytesRead == 0) {  
return r;  
}  
r = WriteFile(dstHandle, buffer, bytesRead, &bytesWritten, NULL);  
if (bytesWritten == 0) {  
return r;  
}  
} while (TRUE);  
}  
  
BOOL copyFileToSql(LPCWSTR srcFilePath, LPCWSTR dstFilePath, LPBYTE transactionToken, SQLINTEGER cbTransactionToken) {  
  
BOOL r;  
  
HANDLE srcHandle, dstHandle;  
unsigned int NtStatus;  
  
srcHandle =  CreateFile(  
                         srcFilePath,  
                         GENERIC_READ,  
                         FILE_SHARE_READ,  
                         NULL,  
                         OPEN_EXISTING,  
                         FILE_FLAG_SEQUENTIAL_SCAN,  
 NULL);  
  
if (srcHandle == INVALID_HANDLE_VALUE) {  
return FALSE;  
}  
  
dstHandle =  OpenSqlFilestream(  
                         dstFilePath,  
                         Write,  
                         0,  
                         transactionToken,  
                         cbTransactionToken,  
                         0);  
  
if (dstHandle == INVALID_HANDLE_VALUE) {  
NtStatus = GetLastError();  
r = CloseHandle(srcHandle);  
return FALSE;  
}  
  
//copy file  
r = copyFileContents(srcHandle, dstHandle);  
  
CloseHandle(srcHandle);  
  
CloseHandle(dstHandle);  
  
return r;  
}  
  
BOOL copyFileFromSql(LPCWSTR srcFilePath, LPCWSTR dstFilePath, LPBYTE transactionToken, SQLINTEGER cbTransactionToken) {  
  
BOOL r;  
  
HANDLE srcHandle, dstHandle;  
unsigned int NtStatus;  
  
srcHandle =  OpenSqlFilestream(  
                         srcFilePath,  
                         Read,  
                         0,  
                         transactionToken,  
                         cbTransactionToken,  
                         0);  
  
if (srcHandle == INVALID_HANDLE_VALUE) {  
return FALSE;  
}  
  
dstHandle =  CreateFile(  
                         dstFilePath,  
                         GENERIC_WRITE,  
                         0,  
                         NULL,  
                         OPEN_ALWAYS,  
                         FILE_ATTRIBUTE_NORMAL,  
 NULL);  
  
if (dstHandle == INVALID_HANDLE_VALUE) {  
CloseHandle(srcHandle);  
return FALSE;  
}  
  
r = copyFileContents(srcHandle, dstHandle);  
  
CloseHandle(srcHandle);  
  
CloseHandle(dstHandle);  
  
return r;  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="327ce-122">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="327ce-122">See Also</span></span>  
 [<span data-ttu-id="327ce-123">Programação do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="327ce-123">SQL Server Native Client Programming</span></span>](../sql-server-native-client-programming.md)  
  
  
