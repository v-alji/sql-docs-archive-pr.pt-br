---
title: Buscar colunas usando IRow::GetColumns (ou IRow::Open) e ISequentialStream | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- Open method
- ISequentialStream interface, samples
- GetColumns method
ms.assetid: 0761f469-9b6c-4fa6-bbd7-f0cb936e4f1c
author: rothja
ms.author: jroth
ms.openlocfilehash: 50c34d537ce790baa68a73789b8db406d12f0859
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570676"
---
# <a name="fetch-columns-using-irowgetcolumns-or-irowopen-and-isequentialstream"></a><span data-ttu-id="d9fcc-102">Buscar colunas usando IRow::GetColumns (ou IRow::Open) e ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="d9fcc-102">Fetch Columns Using IRow::GetColumns (or IRow::Open) and ISequentialStream</span></span>
  <span data-ttu-id="d9fcc-103">Dados grandes podem ser associados ou recuperados por meio da interface `ISequentialStream`.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-103">Large data can be bound or retrieved using the `ISequentialStream` interface.</span></span> <span data-ttu-id="d9fcc-104">Para colunas associadas, o sinalizador de status DBSTATUS_S_TRUNCATED indica que os dados estão truncados.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-104">For bound columns, the status flag DBSTATUS_S_TRUNCATED indicates that the data is truncated.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d9fcc-105">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-105">When possible, use Windows Authentication.</span></span> <span data-ttu-id="d9fcc-106">Se a Autenticação do Windows não estiver disponível, solicite aos usuários que digitem suas credenciais em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-106">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="d9fcc-107">Evite armazenar as credenciais em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-107">Avoid storing credentials in a file.</span></span> <span data-ttu-id="d9fcc-108">Se for necessário manter as credenciais, criptografe-as com a [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532)(em inglês).</span><span class="sxs-lookup"><span data-stu-id="d9fcc-108">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-fetch-columns-using-irowgetcolumns-or-irowopen-and-isequentialstream"></a><span data-ttu-id="d9fcc-109">Para buscar colunas usando IRow::GetColumns (ou IRow::Open) e ISequentialStream</span><span class="sxs-lookup"><span data-stu-id="d9fcc-109">To fetch columns using IRow::GetColumns (or IRow::Open) and ISequentialStream</span></span>  
  
1.  <span data-ttu-id="d9fcc-110">Estabeleça uma conexão com a fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-110">Establish a connection to the data source.</span></span>  
  
2.  <span data-ttu-id="d9fcc-111">Execute o comando (neste exemplo, `ICommandExecute::Execute()` é chamado com IID_IRow).</span><span class="sxs-lookup"><span data-stu-id="d9fcc-111">Execute the command (in this example, `ICommandExecute::Execute()` is called with IID_IRow).</span></span>  
  
3.  <span data-ttu-id="d9fcc-112">Busque os dados da coluna que usam `IRow::Open()` ou `IRow::GetColumns()`.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-112">Fetch the column data using `IRow::Open()` or `IRow::GetColumns()`.</span></span>  
  
    -   <span data-ttu-id="d9fcc-113">`IRow::Open()` pode ser usado para abrir um `ISequentialStream` na linha.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-113">`IRow::Open()` can be used to open an `ISequentialStream` on the row.</span></span> <span data-ttu-id="d9fcc-114">Especifique DBGUID_STREAM para indicar que uma coluna contém um fluxo de dados binários (`IStream` ou `ISequentialStream` que pode ser usada para ler os dados da coluna).</span><span class="sxs-lookup"><span data-stu-id="d9fcc-114">Specify DBGUID_STREAM to indicate that the column contains a stream of binary data (`IStream` or `ISequentialStream` can then be used to read the data from the column).</span></span>  
  
    -   <span data-ttu-id="d9fcc-115">Se `IRow::GetColumns()` for usado, o elemento **pData** da estrutura DBCOLUMNACCESS será definido para apontar para um objeto de fluxo.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-115">If `IRow::GetColumns()` is used, the **pData** element of DBCOLUMNACCESS structure is set to point to a stream object.</span></span>  
  
4.  <span data-ttu-id="d9fcc-116">Use **ISequentialStream::Read()** repetidamente para ler o número especificado de bytes no buffer de consumidor.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-116">Use **ISequentialStream::Read()** repeatedly to read the specified number of bytes into the consumer buffer.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d9fcc-117">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d9fcc-117">Example</span></span>  
 <span data-ttu-id="d9fcc-118">Este exemplo mostra como buscar uma única linha por meio de IRow.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-118">This example shows how to fetch a single row using IRow.</span></span> <span data-ttu-id="d9fcc-119">Neste exemplo, uma coluna de cada vez é recuperada da linha.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-119">In this example one column at a time is retrieved from the row.</span></span> <span data-ttu-id="d9fcc-120">Este exemplo ilustra o uso de IRow::Open() e de IRow::GetColumns().</span><span class="sxs-lookup"><span data-stu-id="d9fcc-120">This example illustrate the use of IRow::Open() as well as IRow::GetColumns().</span></span> <span data-ttu-id="d9fcc-121">Para ler os dados da coluna, o exemplo usa ISequentialStream::Read.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-121">To read the column data, the example uses ISequentialStream::Read.</span></span>  
  
 <span data-ttu-id="d9fcc-122">Este exemplo exige o banco de dados de exemplo AdventureWorks, que pode ser baixado na home page de [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) (em inglês).</span><span class="sxs-lookup"><span data-stu-id="d9fcc-122">This sample requires the AdventureWorks sample database, which you can download from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.</span></span>  
  
 <span data-ttu-id="d9fcc-123">A primeira listagem de código ([!INCLUDE[tsql](../../includes/tsql-md.md)]) cria uma tabela usada pelo exemplo.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-123">The first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing creates a table used by the sample.</span></span>  
  
 <span data-ttu-id="d9fcc-124">Compile com ole32.lib oleaut32.lib e execute a segunda listagem de códigos (C++).</span><span class="sxs-lookup"><span data-stu-id="d9fcc-124">Compile with ole32.lib oleaut32.lib  and execute the second (C++) code listing.</span></span> <span data-ttu-id="d9fcc-125">Esse aplicativo se conecta à instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do computador.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-125">This application connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="d9fcc-126">Em alguns sistemas operacionais Windows, será necessário alterar (localhost) ou (local) para o nome de sua instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="d9fcc-126">On some Windows operating systems, you will need to change (localhost) or (local) to the name of your [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="d9fcc-127">Para se conectar a uma instância nomeada, altere a cadeia de conexão de L"(local)" para L"(local)\\\name", em que name é a instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-127">To connect to a named instance, change the connection string from L"(local)" to L"(local)\\\name" , where name is the named instance.</span></span> <span data-ttu-id="d9fcc-128">Por padrão, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express é instalado em uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-128">By default, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Express installs to a named instance.</span></span> <span data-ttu-id="d9fcc-129">Verifique se a variável de ambiente INCLUDE inclui o diretório que contém sqlncli.h.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-129">Make sure your INCLUDE environment variable includes the directory that contains sqlncli.h.</span></span>  
  
 <span data-ttu-id="d9fcc-130">A terceira listagem de código ([!INCLUDE[tsql](../../includes/tsql-md.md)]) exclui a tabela usada pelo exemplo.</span><span class="sxs-lookup"><span data-stu-id="d9fcc-130">The third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing deletes the table used by the sample.</span></span>  
  
```  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'MyTable')  
     DROP TABLE MyTable  
GO  
  
CREATE TABLE MyTable  
(  
     col1  int,  
     col2  varchar(50),  
     col3  char(50),  
     col4  datetime,  
     col5  float,  
     col6  money,  
     col7  sql_variant,  
     col8  binary(50),  
     col9  text,  
     col10 image  
)  
GO  
  
-- Enter data  
INSERT INTO MyTable  
values  
(  
     10,  
     'abcdefghijklmnopqrstuvwxyz',  
     'ABCDEFGHIJKLMNOPQRSTUVWXYZ',  
     '11/1/1999 11:52 AM',  
     3.14,  
     99.95,  
     CONVERT(nchar(50), N'AbCdEfGhIjKlMnOpQrStUvWxYz'),  
     0x123456789,  
     REPLICATE('AAAAABBBBB', 500),  
     REPLICATE(0x123456789, 500)  
)  
GO  
```  
  
```  
// compile with: ole32.lib oleaut32.lib  
#define DBINITCONSTANTS  
#define INITGUID  
#define OLEDBVER 0x0250   // to include correct interfaces  
  
#include <stdio.h>  
#include <windows.h>  
#include <iostream>  
#include <oledb.h>  
#include <sqlncli.h>  
  
using namespace std;  
  
const int kMaxBuff = 50;  
int InitializeAndEstablishConnection();  
HRESULT GetColumnSize(IRow* pUnkRow, ULONG iCol);  
ULONG PrintData(ULONG iCols, ULONG iStart, DBCOLUMNINFO* prgInfo, DBCOLUMNACCESS* prgColumns);  
HRESULT GetColumns(IRow* pUnkRow, ULONG iStart, ULONG iEnd);  
HRESULT GetSequentialColumn(IRow* pUnkRow, ULONG iCol, BOOL fOpen = TRUE);  
  
IDBInitialize*       pIDBInitialize     = NULL;  
IDBProperties*       pIDBProperties     = NULL;  
IDBCreateSession*    pIDBCreateSession  = NULL;  
IDBCreateCommand*    pIDBCreateCommand  = NULL;  
ICommandText*        pICommandText      = NULL;  
IRow*                pIRow              = NULL;  
DBCOLUMNINFO*        pDBColumnInfo      = NULL;  
IAccessor*           pIAccessor         = NULL;  
DBPROP               InitProperties[4];  
DBPROPSET            rgInitPropSet[1];  
ULONG                i, j;  
HRESULT              hresult;  
DBROWCOUNT           cNumRows = 0;  
ULONG                lNumCols;  
WCHAR*               pStringsBuffer;  
DBBINDING*           pBindings;  
ULONG                ConsumerBufColOffset = 0;  
HACCESSOR            hAccessor;  
ULONG                lNumRowsRetrieved;  
HROW                 hRows[10];  
HROW*                pRows = &hRows[0];  
  
int main() {  
   ULONG iidx = 0;  
   WCHAR* wCmdString = OLESTR("SELECT * FROM MyTable ");    
  
   // Call a function to initialize and establish connection.   
   if (InitializeAndEstablishConnection() == -1) {  
      cout << "Failed to initialize and establish connection.\n";  
      // Insert your code for cleanup and error handling  
      return -1;  
   }  
  
   // Create a session object.  
   if (FAILED(pIDBInitialize->QueryInterface( IID_IDBCreateSession, (void**) &pIDBCreateSession))) {  
      cout << "Failed to obtain IDBCreateSession interface.\n";  
      // Insert your code for cleanup and error handling  
      return -1;  
   }  
  
   if (FAILED(pIDBCreateSession->CreateSession( NULL,  
                                                IID_IDBCreateCommand,  
                                                (IUnknown**) &pIDBCreateCommand))) {  
      cout << "pIDBCreateSession->CreateSession failed.\n";  
      // Insert your code for cleanup and error handling  
      return -1;  
   }  
  
   // Access the ICommandText interface.  
   if (FAILED(pIDBCreateCommand->CreateCommand( NULL, IID_ICommandText, (IUnknown**) &pICommandText))) {  
      cout << "Failed to access ICommand interface.\n";  
      // Insert your code for cleanup and error handling  
      return -1;  
   }  
  
   // Use SetCommandText() to specify the command text.  
   if (FAILED(pICommandText->SetCommandText(DBGUID_DBSQL, wCmdString))) {  
      cout << "Failed to set command text.\n";  
      // Insert your code for cleanup and error handling  
      return -1;  
   }  
  
   // Execute the command.  
   if (FAILED(hresult = pICommandText->Execute( NULL, IID_IRow, NULL, &cNumRows, (IUnknown **) &pIRow))) {  
      cout << "Failed to execute command.\n";  
      // Insert your code for cleanup and error handling  
      return -1;  
   }  
  
   DBORDINAL cColumns = 0;  
   DBCOLUMNINFO* prgInfo = 0;  
   OLECHAR* pColNames;  
  
   // Get column count  
   HRESULT hr;  
   IColumnsInfo* pIColumnsInfo;  
   hr = pIRow->QueryInterface(IID_IColumnsInfo, (void**) &pIColumnsInfo);  
   if (FAILED(hr))  
      goto CLEANUP;  
  
   hr = pIColumnsInfo->GetColumnInfo(&cColumns, &prgInfo, &pColNames);  
   if (FAILED(hr))  
      goto CLEANUP;  
  
   // Get columns (one at a time) using ISequentialStream and Open  
   // 3rd parameter is by default TRUE indicating use of ISequentialStream and Open.  
   DBCOLUMNINFO* colInfo;   
   for ( iidx = 1 ; iidx <= cColumns ; iidx++ ) {  
  colInfo = (DBCOLUMNINFO*)(prgInfo + (iidx - 1));  
  if (colInfo->dwFlags & DBCOLUMNFLAGS_ISLONG)  
  hresult = GetSequentialColumn(pIRow, iidx);  
  else  
  hresult = GetColumns(pIRow, iidx, iidx);  
   }  
  
   // Release the Row object.  
   pIRow->Release();  
  
   // Execute the command again.  
   if (FAILED(hresult = pICommandText->Execute(NULL,  
                                               IID_IRow,  
                                               NULL,  
                                               &cNumRows,  
                                               (IUnknown **) &pIRow))) {  
      cout << "Failed to execute command.\n";  
      // Insert your code for cleanup and error handling  
      return -1;  
   }  
  
   // Now get columns (one at a time) using ISequentialStream and GetColumns.   
   // The 3rd parameter is by default TRUE indicating use of ISequentialStream   
   // and GetColumns  
   for ( iidx = 1 ; iidx <= cColumns ; iidx++ ) {  
  colInfo = (DBCOLUMNINFO*)(prgInfo + (iidx - 1));  
  if (colInfo->dwFlags & DBCOLUMNFLAGS_ISLONG)  
  hresult = GetSequentialColumn(pIRow, iidx, FALSE);  
  else  
  hresult = GetColumns(pIRow, iidx, iidx);  
   }  
  
CLEANUP:  
   // Release memory.  
   pICommandText->Release();  
   pIDBCreateCommand->Release();  
   pIDBCreateSession->Release();  
  
   if (FAILED(pIDBInitialize->Uninitialize())) {  
      // Uninitialize not required, but it fails if an interface has not been released, can be used for debugging.   
      // cout << "Problem uninitializing.\n";  
   }  
  
   pIDBInitialize->Release();  
  
   CoTaskMemFree(prgInfo);  
   CoTaskMemFree(pColNames);  
   if( pIColumnsInfo )  
      pIColumnsInfo->Release();  
  
   // Release the COM library.  
   CoUninitialize();  
}  
  
HRESULT GetSequentialColumn(IRow* pUnkRow, ULONG iCol, BOOL fOpen) {  
   HRESULT hr = NOERROR;  
   ULONG cbRead = 0;  
   ULONG cbTotal = 0;  
   DBORDINAL cColumns = 0;  
   ULONG cReads = 0;  
   ISequentialStream* pIStream = NULL;  
   WCHAR* pBuffer[kMaxBuff];   // 50 chars read by ISequentialStream::Read()  
   DBCOLUMNINFO* prgInfo = 0;  
   OLECHAR* pColNames = 0;  
   IColumnsInfo* pIColumnsInfo;  
   DBID columnid;  
   DBCOLUMNACCESS column;  
  
   wprintf(L"[RETRIEVING COLUMN %d SEQUENTIALLY]\n", iCol);  
  
   // Get column information (basically get column id).  
   hr = pUnkRow->QueryInterface(IID_IColumnsInfo, (void**) &pIColumnsInfo);  
   if (FAILED(hr))  
      goto CLEANUP;  
  
   hr = pIColumnsInfo->GetColumnInfo(&cColumns, &prgInfo, &pColNames);  
   if (FAILED(hr))  
      goto CLEANUP;  
  
   // Get Column ID.  
   columnid = (prgInfo + (iCol - 1))->columnid;  
   if (fOpen) {   // Get columns using ISequentialStream and IRow::Open  
      wprintf(L"[RETRIEVING COLUMNS USING ");  
      wprintf(L" ISequentialSteam and Open]\n");  
  
      // Open sequential stream.  
      hr = pUnkRow->Open(NULL,  
                         &columnid,  
                         DBGUID_STREAM,  
                         0,  
                         IID_ISequentialStream,  
                         (LPUNKNOWN *)&pIStream);  
  
      if (FAILED(hr)) {  
         wprintf(L"Unable to get ISequentialStream interface.\n");  
         goto CLEANUP;  
      }  
   }  
  
   else {   // Get Columns using IRow::GetColumns and ISequentialStream.  
      wprintf(L"[RETRIEVING COLUMNS USING ");  
      wprintf(L" GetColumns and ISequentialStream]\n");  
  
  IUnknown* pUnkStream = NULL;  
  
      ZeroMemory(&column, sizeof(column));  
      column.columnid = prgInfo[iCol - 1].columnid;  
      column.wType = DBTYPE_IUNKNOWN;  
      column.pData = (LPVOID*) &pUnkStream;  
  
      hr = pUnkRow->GetColumns(1, &column);  
      if (FAILED(hr)) {  
         wprintf(L"Error executing IRow::GetColumns.\n");  
         goto CLEANUP;  
      }  
  
      hr = pUnkStream->QueryInterface(IID_ISequentialStream, (LPVOID*) &pIStream);  
      if (FAILED(hr)) {  
         wprintf(L"Unable to get ISequentialStream interface ");  
         wprintf(L"via IRow::GetColumns.\n");  
         goto CLEANUP;  
      }  
  
      pUnkStream->Release();  
   }  
  
   ZeroMemory(pBuffer, kMaxBuff * sizeof(WCHAR));  
  
   // Read 50 chars at a time until no more data.  
   do {  
      hr = pIStream->Read(pBuffer, kMaxBuff, &cbRead);  
      if (FAILED(hr)) {  
         wprintf(L"Error reading data.\n");  
         goto CLEANUP;  
      }  
  
      cbTotal = cbTotal + cbRead;  
  
      // Print the data  
      wprintf(L"READ #%d: %-*S\n", ++cReads, kMaxBuff, pBuffer);  
   } while(cbRead > 0);  
  
   wprintf(L"[READ %d bytes for column %d.\n", cbTotal, iCol);  
  
CLEANUP:  
   if (pIColumnsInfo)  
      pIColumnsInfo->Release();  
  
   CoTaskMemFree(prgInfo);  
   CoTaskMemFree(pColNames);  
  
   if (pIStream)  
      pIStream->Release();  
  
   return hr;  
}  
  
BOOL InitColumn(DBCOLUMNACCESS* pCol, DBCOLUMNINFO* pInfo) {  
   // If maximum possible length of a value column is very large (text or image  
   //  column is read) limit that size to 512 bytes (for illustration purposes).  
  
   ULONG ulSize;  
   if (pInfo->wType == DBTYPE_WSTR || pInfo->wType == DBTYPE_STR)  
      ulSize = (pInfo->ulColumnSize < 0x7fffffff) ? pInfo->ulColumnSize : 512;  
   else  
      ulSize = 128; //default buffer to handle conversion to text of non-string data types  
  
   // Verify data buffer is large enough.  
   if (pCol->cbMaxLen < (ulSize + 1)) {  
      if (pCol->pData) {  
         delete [] pCol->pData;  
         pCol->pData = NULL;  
      }  
  
      // Allocate data buffer  
      void * p = pCol->pData = new WCHAR[ulSize + 1];  
      if (!(p /*pCol->pData = new WCHAR[ulSize + 1]*/ ))  
         return FALSE;  
  
      // set the max length of caller-initialized memory.  
      pCol->cbMaxLen = sizeof(WCHAR) * (ulSize + 1);  
  
      // In the above 2 steps, pData is pointing to memory (it is not NULL) and   
      // cbMaxLen has a value (not 0), so next call to IRow->GetData()   
      // will read the data from the column.  
   }  
  
   // Clear memory buffer  
   ZeroMemory((void*) pCol->pData, pCol->cbMaxLen);  
  
   // Set properties.  
   //pCol->wType = DBTYPE_WSTR;  
   pCol->wType = DBTYPE_WSTR;  
   pCol->columnid = pInfo->columnid;  
   pCol->cbDataLen = 0;  
   pCol->dwStatus = 0;  
   pCol->dwReserved = 0;  
   pCol->bPrecision = 0;  
   pCol->bScale = 0;  
  
   return TRUE;  
}  
  
HRESULT GetColumns(IRow* pUnkRow, ULONG iStart, ULONG iEnd) {  
// Start and end are same. Thus, get only one column.  
   HRESULT          hr = E_FAIL;  
   ULONG            iidx;          // loop counter  
   DBORDINAL        cColumns;      // Count of columns  
   ULONG            cUserCols;     // Count of user columns  
   DBCOLUMNINFO*    prgInfo;       // Column of info. array  
   OLECHAR*         pColNames;     // Array of column names  
   DBCOLUMNACCESS*  prgColumns;    // Ptr to column access structures array  
   DBCOLUMNINFO*    pCurrInfo;  
   DBCOLUMNACCESS*  pCurrCol;  
  
   IColumnsInfo* pIColumnsInfo = NULL;  
  
   // Initialize  
   cColumns    = 0;  
   prgInfo     = NULL;  
   pColNames   = NULL;  
   prgColumns  = NULL;  
  
   printf("Retrieving data with GetColumns\n");  
  
   // Get column info to build column access array  
   hr = pUnkRow->QueryInterface(IID_IColumnsInfo, (void**)&pIColumnsInfo);  
  
   if (FAILED(hr))  
      goto CLEANUP;  
  
   hr = pIColumnsInfo->GetColumnInfo(&cColumns, &prgInfo, &pColNames);  
  
   if (FAILED(hr))  
      goto CLEANUP;  
  
   // Determine no. of columns to retrieve.  Since iEnd and iStart is same,   
   // this is redundent step.  cUserCols will always be 1.  
   cUserCols = iEnd - iStart + 1;   
  
   // Walk list of columns and setup a DBCOLUMNACCESS structure  
   DBCOLUMNACCESS * x = (prgColumns = new DBCOLUMNACCESS[cUserCols]);  
   if (!(x /*prgColumns = new DBCOLUMNACCESS[cUserCols]*/ )) {   // cUserCols is only 1  
      hr = E_FAIL;  
      goto CLEANUP;  
   }  
  
   ZeroMemory((void*) prgColumns, sizeof(DBCOLUMNACCESS) * cUserCols);  
  
   for ( iidx = 0 ; iidx < cUserCols ; iidx++ ) {  
      pCurrInfo = prgInfo + iidx + iStart - 1;  
      pCurrCol = prgColumns + iidx;  
  
      // Here the values of pData and cbMaxLen elements of DBCOLUMNACCESS   
      // elements is set. Thus IRow->GetColumns() will return actual data.  
      if ( InitColumn(pCurrCol, pCurrInfo) == FALSE )  
         goto CLEANUP;  
   }  
  
   hr = pUnkRow->GetColumns(cUserCols, prgColumns);   // cUserCols = 1  
   if (FAILED(hr))  
      printf("Error occured\n");  
  
   // Show data.  
   PrintData(cUserCols, iStart, prgInfo, prgColumns);  
  
CLEANUP:  
   if (pIColumnsInfo)  
      pIColumnsInfo->Release();  
   if (prgColumns)  
      delete [] prgColumns;  
  
   return hr;  
}  
// This function returns the actual width of the data in the column (not the   
// columnwidth in DBCOLUMNFO structure which is the width of the column)  
HRESULT GetColumnSize(IRow* pUnkRow, ULONG iCol) {  
   HRESULT         hr = NOERROR;  
   DBORDINAL       cColumns = 0;   // Count the columns  
   DBCOLUMNINFO*   prgInfo;        // Column info array  
   OLECHAR*        pColNames;  
   DBCOLUMNACCESS  column;            
   DBCOLUMNINFO*   pCurrInfo;  
   IColumnsInfo*   pIColumnsInfo = NULL;  
  
   // Initialize  
   prgInfo = NULL;  
   pColNames = NULL;  
  
   printf("Checking column size\n");  
  
   // Get column info to build column access array  
   hr = pUnkRow->QueryInterface(IID_IColumnsInfo, (void**) &pIColumnsInfo);  
   if (FAILED(hr))  
      goto CLEANUP;  
  
   hr = pIColumnsInfo->GetColumnInfo(&cColumns, &prgInfo, &pColNames);  
   if (FAILED(hr))  
      goto CLEANUP;  
   printf("Value of cColumns is %d\n", cColumns);  
  
   // Setup a DBCOLUMNACCESS structure: pData is set to NULL and cbMaxLen is set   
   // to 0. Thus IRow->GetColumns() returns only the actual column length in  
   // cbDataLen member of DBCOLUMNACCESS structure.In this case you can call   
   // IRow->GetColumns() again for the same column to retrieve actual data in the second call.  
   ZeroMemory((void*) &column, sizeof(DBCOLUMNACCESS));  
   column.pData = NULL;  
  
   pCurrInfo = prgInfo + iCol - 1;  
   // Get column id in DBCOLUMNACCESS structure. It is then used in GetColumn().  
   column.columnid = pCurrInfo->columnid;   
  
   printf("column.columnid value is %d\n", column.columnid);  
   // We know which column to get.  The column.columnid gives the column number.  
   hr = pUnkRow->GetColumns(1, &column);   
   if (FAILED(hr))  
      printf("Errors occured\n");  
  
   // Show data  
   PrintData(1, iCol, prgInfo, &column);  
  
CLEANUP:  
   if (pIColumnsInfo)  
      pIColumnsInfo->Release();  
   return hr;  
}  
  
BOOL GetStatus(DWORD dwStatus, WCHAR* pwszStatus) {  
   switch (dwStatus) {  
   case DBSTATUS_S_OK:  
      wcscpy_s(pwszStatus, 255, L"DBSTATUS_S_OK");  
      break;  
   case DBSTATUS_E_CANTCONVERTVALUE:  
   wcscpy_s(pwszStatus, 255, L"DBSTATUS_E_CANTCONVERTVALUE");  
   break;  
   case DBSTATUS_S_ISNULL:  
   wcscpy_s(pwszStatus, 255, L"DBSTATUS_S_ISNULL");  
   break;  
   case DBSTATUS_E_UNAVAILABLE:  
      wcscpy_s(pwszStatus, 255, L"DBSTATUS_E_UNAVAILABLE");  
      break;  
   case DBSTATUS_S_TRUNCATED:  
      wcscpy_s(pwszStatus, 255, L"DBSTATUS_S_TRUNCATED");  
      break;  
   default:  
      swprintf_s(pwszStatus, sizeof(pwszStatus), L"OTHER STATUS VALUE: %d", dwStatus);  
   }  
   return TRUE;  
}  
  
ULONG PrintData(ULONG iCols,   
                ULONG iStart,   
                DBCOLUMNINFO* prgInfo,   
                DBCOLUMNACCESS* prgColumns) {  
  
   WCHAR wszStatus[255];  
   DBCOLUMNINFO* pCurrInfo;  
   DBCOLUMNACCESS* pCurrCol;  
   ULONG iidx = 0;       // Loop counter  
  
   printf("%-3s %-20s %-21s %-9s %-9s %-50s\n", "No.", "Name", "Status", "Length", "Max", "Data");  
  
   for ( iidx = 0 ; iidx < iCols ; iidx++ ) {  
      pCurrInfo = prgInfo + iidx + iStart - 1;  
      pCurrCol = prgColumns + iidx;  
  
      GetStatus(pCurrCol->dwStatus, wszStatus);   
      // was the data successfully retrieved?  
      wprintf(L"%-3d %-20s %-21s %-9d %-9d %-50s\n", iStart + iidx,  
                                                    pCurrInfo->pwszName,  
                                                    wszStatus,  
                                                    pCurrCol->cbDataLen,  
                                                    pCurrCol->cbMaxLen,  
pCurrCol->dwStatus == DBSTATUS_S_ISNULL ? L"(NULL)" : (WCHAR*) pCurrCol->pData);  
   }  
  
   wprintf(L"\n");  
   return iidx;  
}  
  
int InitializeAndEstablishConnection() {      
   // Initialize the COM library.  
   CoInitialize(NULL);  
  
   // Obtain access to the SQLNCLI provider.  
   hresult = CoCreateInstance(CLSID_SQLNCLI11,   
                              NULL,   
                              CLSCTX_INPROC_SERVER,  
                              IID_IDBInitialize,   
                              (void **) &pIDBInitialize);  
  
   if(FAILED(hresult)) {  
      printf("Failed to get IDBInitialize interface.\n");  
      // Insert your code for cleanup and error handling  
      return -1;  
   }  
  
   // Initialize the property values needed to establish the connection.  
   for (i =  0 ; i < 4 ; i++ )  
      VariantInit(&InitProperties[i].vValue);  
  
   // Server name.  
   InitProperties[0].dwPropertyID = DBPROP_INIT_DATASOURCE;  
   InitProperties[0].vValue.vt = VT_BSTR;  
  
   InitProperties[0].vValue.bstrVal = SysAllocString(L"(local)");  
   InitProperties[0].dwOptions     = DBPROPOPTIONS_REQUIRED;  
   InitProperties[0].colid         = DB_NULLID;  
  
   // Database.  
   InitProperties[1].dwPropertyID  = DBPROP_INIT_CATALOG;  
   InitProperties[1].vValue.vt     = VT_BSTR;  
   InitProperties[1].vValue.bstrVal= SysAllocString(L"AdventureWorks");  
   InitProperties[1].dwOptions     = DBPROPOPTIONS_REQUIRED;  
   InitProperties[1].colid         = DB_NULLID;  
  
   // connection  
   InitProperties[2].dwPropertyID  = DBPROP_AUTH_INTEGRATED;  
   InitProperties[2].vValue.vt     = VT_BSTR;  
   InitProperties[2].vValue.bstrVal= SysAllocString(L"SSPI");  
   InitProperties[2].dwOptions     = DBPROPOPTIONS_REQUIRED;  
   InitProperties[2].colid         = DB_NULLID;  
  
   // Now that the properties are set, construct the DBPROPSET structure  
   // (rgInitPropSet). The DBPROPSET structure is used to pass an array   
   // of DBPROP structures (InitProperties) to the SetProperties method.  
   rgInitPropSet[0].guidPropertySet = DBPROPSET_DBINIT;  
   rgInitPropSet[0].cProperties    = 4;  
   rgInitPropSet[0].rgProperties   = InitProperties;  
  
   // Set initialization properties.  
   hresult = pIDBInitialize->QueryInterface(IID_IDBProperties, (void **)&pIDBProperties);  
   if (FAILED(hresult)) {  
      cout << "Failed to get IDBProperties interface.\n";  
      // Insert your code for cleanup and error handling  
      return -1;  
   }  
  
   hresult = pIDBProperties->SetProperties(1, rgInitPropSet);   
   if (FAILED(hresult)) {  
      cout << "Failed to set initialization properties.\n";  
      // Insert your code for cleanup and error handling  
      return -1;  
   }  
  
   pIDBProperties->Release();  
  
   // Now establish the connection to the data source.  
   if (FAILED(pIDBInitialize->Initialize())) {  
      cout << "Problem establishing connection to the data source.\n";  
      // Insert your code for cleanup and error handling  
      return -1;  
   }  
  
   return 0;  
}  
```  
  
```  
USE AdventureWorks  
GO  
  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'MyTable')  
     DROP TABLE MyTable  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="d9fcc-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d9fcc-131">See Also</span></span>  
 [<span data-ttu-id="d9fcc-132">Tópicos de instruções do OLE DB</span><span class="sxs-lookup"><span data-stu-id="d9fcc-132">OLE DB How-to Topics</span></span>](ole-db-how-to-topics.md)  
  
  
