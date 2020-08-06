---
title: Usar colunas de dados em execução (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- data-at-execution
ms.assetid: 4eae58d1-03d4-40ca-8aa1-9b3ea10a38cf
author: rothja
ms.author: jroth
ms.openlocfilehash: 68690208b690f94909100132c966eb59d11e4652
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87684192"
---
# <a name="use-data-at-execution-columns-odbc"></a><span data-ttu-id="120b4-102">Usar colunas de dados em execução (ODBC)</span><span class="sxs-lookup"><span data-stu-id="120b4-102">Use Data-at-Execution Columns (ODBC)</span></span>
    
### <a name="to-use-data-at-execution-text-ntext-or-image-columns"></a><span data-ttu-id="120b4-103">Para usar colunas de dados em execução de text, ntext ou image</span><span class="sxs-lookup"><span data-stu-id="120b4-103">To use data-at-execution text, ntext, or image columns</span></span>  
  
1.  <span data-ttu-id="120b4-104">Para cada coluna de dados em execução, coloque valores especiais nos buffers associados anteriormente por [SQLBindCol](../native-client-odbc-api/sqlbindcol.md):</span><span class="sxs-lookup"><span data-stu-id="120b4-104">For each data-at-execution column, put special values into the buffers previously bound by [SQLBindCol](../native-client-odbc-api/sqlbindcol.md):</span></span>  
  
    -   <span data-ttu-id="120b4-105">Para o último parâmetro, use SQL_LEN_DATA_AT_EXEC(length) onde length é o comprimento total em bytes dos dados de coluna de text, ntext ou image.</span><span class="sxs-lookup"><span data-stu-id="120b4-105">For the last parameter, use SQL_LEN_DATA_AT_EXEC(length) where length is the total length of the text, ntext, or image column data in bytes.</span></span>  
  
    -   <span data-ttu-id="120b4-106">Para o quarto parâmetro, coloque um identificador de coluna definido por programa.</span><span class="sxs-lookup"><span data-stu-id="120b4-106">For the fourth parameter, put a program-defined column identifier.</span></span>  
  
2.  <span data-ttu-id="120b4-107">Chame [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) returns SQL_NEED_DATA, que indica que as colunas de dados em execuções estão prontas para o processamento.</span><span class="sxs-lookup"><span data-stu-id="120b4-107">Calling [SQLSetPos](https://go.microsoft.com/fwlink/?LinkId=58407) returns SQL_NEED_DATA, which indicates that data-at-execution columns are ready for processing.</span></span>  
  
3.  <span data-ttu-id="120b4-108">Para cada coluna de dados em execução:</span><span class="sxs-lookup"><span data-stu-id="120b4-108">For each data-at-execution column:</span></span>  
  
    -   <span data-ttu-id="120b4-109">Chame [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) para obter o ponteiro de matriz da coluna.</span><span class="sxs-lookup"><span data-stu-id="120b4-109">Call [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) to get the column array pointer.</span></span> <span data-ttu-id="120b4-110">SQL_NEED_DATA será retornado se houver outra coluna de dados em execução.</span><span class="sxs-lookup"><span data-stu-id="120b4-110">It will return SQL_NEED_DATA if there is another data-at-execution column.</span></span>  
  
    -   <span data-ttu-id="120b4-111">Chame [SQLPutData](../native-client-odbc-api/sqlputdata.md) uma ou mais vezes para enviar os dados da coluna, até que o comprimento seja enviado.</span><span class="sxs-lookup"><span data-stu-id="120b4-111">Call [SQLPutData](../native-client-odbc-api/sqlputdata.md) one or more times to send the column data, until length is sent.</span></span>  
  
4.  <span data-ttu-id="120b4-112">Chame [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) para indicar que todos os dados da coluna de dados em execução final foram enviados.</span><span class="sxs-lookup"><span data-stu-id="120b4-112">Call [SQLParamData](https://go.microsoft.com/fwlink/?LinkId=58405) to indicate that all the data for the final data-at-execution column is sent.</span></span> <span data-ttu-id="120b4-113">SQL_NEED_DATA não será retornado.</span><span class="sxs-lookup"><span data-stu-id="120b4-113">It will not return SQL_NEED_DATA.</span></span>  
  
## <a name="example"></a><span data-ttu-id="120b4-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="120b4-114">Example</span></span>  
 <span data-ttu-id="120b4-115">O exemplo mostra como ler dados de caracteres variáveis de SQL_LONG usando o SQLGetData.</span><span class="sxs-lookup"><span data-stu-id="120b4-115">The sample shows how to read a SQL_LONG variable character data using SQLGetData.</span></span> <span data-ttu-id="120b4-116">Este exemplo não tem suporte em IA64.</span><span class="sxs-lookup"><span data-stu-id="120b4-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="120b4-117">Será necessária uma fonte de dados ODBC chamada AdventureWorks, cujo banco de dados padrão é o banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="120b4-117">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="120b4-118">(Você pode baixar o banco de dados de exemplo AdventureWorks do [Microsoft SQL Server exemplos e projetos da comunidade](https://go.microsoft.com/fwlink/?LinkID=85384) Home Page.) Essa fonte de dados deve ser baseada no driver ODBC fornecido pelo sistema operacional (o nome do driver é "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="120b4-118">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="120b4-119">Se você compilar e executar esse exemplo como um aplicativo de 32 bits em um sistema operacional de 64 bits, deverá criar a fonte de dados ODBC com o Administrador ODBC em %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="120b4-119">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="120b4-120">Esse aplicativo se conecta à instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do computador.</span><span class="sxs-lookup"><span data-stu-id="120b4-120">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="120b4-121">Para conectar-se a uma instância nomeada, altere a definição da fonte de dados ODBC para especificar a instância usando o seguinte formato: servidor\instância_nomeada.</span><span class="sxs-lookup"><span data-stu-id="120b4-121">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="120b4-122">Por padrão, o [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] é instalado em uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="120b4-122">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="120b4-123">Execute a primeira listagem de código ([!INCLUDE[tsql](../../includes/tsql-md.md)]) para criar a tabela usada pelo exemplo.</span><span class="sxs-lookup"><span data-stu-id="120b4-123">Execute the first ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to create the table used by the sample.</span></span>  
  
 <span data-ttu-id="120b4-124">Compile a segunda listagem de código (C++) com odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="120b4-124">Compile the second (C++) code listing with odbc32.lib.</span></span> <span data-ttu-id="120b4-125">Em seguida, execute o programa.</span><span class="sxs-lookup"><span data-stu-id="120b4-125">Then execute the program.</span></span>  
  
 <span data-ttu-id="120b4-126">Execute a terceira listagem de código ([!INCLUDE[tsql](../../includes/tsql-md.md)]) para excluir a tabela usada pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="120b4-126">Execute the third ([!INCLUDE[tsql](../../includes/tsql-md.md)]) code listing to delete the table used by the sample.</span></span>  
  
```  
use AdventureWorks  
CREATE TABLE emp3 (NAME char(30), AGE int, BIRTHDAY datetime, Memo1 text)  
INSERT INTO emp3 (NAME, AGE, Memo1) VALUES   ('Name1', '12', 'This is the first employee')  
INSERT INTO emp3 (NAME, AGE, Memo1) VALUES   ('Name2', '18', 'This is the second employee')  
```  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
#define BUFFERSIZE  450  
  
SQLHENV henv = SQL_NULL_HENV;  
SQLHDBC hdbc1 = SQL_NULL_HDBC;  
SQLHSTMT hstmt1 = SQL_NULL_HSTMT;  
  
void Cleanup() {  
   if (hstmt1 != SQL_NULL_HSTMT)  
      SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
};  
  
int main() {  
   RETCODE retcode;  
   SWORD cntr;  
  
   // SQLGetData variables.  
   UCHAR Data[BUFFERSIZE];  
   SDWORD cbBatch = (SDWORD)sizeof(Data)-1;  
   SQLLEN cbTxtSize;  
  
   // Clear data array.  
   for (cntr = 0 ; cntr < BUFFERSIZE ; cntr++)  
      Data[cntr] = 0x00;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);      
   }  
  
   // Allocate ODBC connection handle and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security, create SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle; prepare, then execute command.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT Memo1 FROM emp3", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Get first row.  
   retcode = SQLFetch(hstmt1);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLFetch(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Get the SQL_LONG column.  
   cntr = 1;  
   while ( (retcode = SQLGetData(hstmt1, 1, SQL_C_CHAR, Data, cbBatch, &cbTxtSize)) != SQL_NO_DATA) {  
      printf("GetData iteration %d, pcbValue = %d,\n", cntr++, cbTxtSize);  
      printf("Data = %s\n\n", Data);  
  
      if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("GetData(hstmt1) Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }   
  
   // Clean up  
   //SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'emp3')  
     DROP TABLE emp3  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="120b4-127">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="120b4-127">See Also</span></span>  
 [<span data-ttu-id="120b4-128">Tópicos de instruções sobre como gerenciar colunas de texto e imagem &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="120b4-128">Managing text and image Columns How-to Topics &#40;ODBC&#41;</span></span>](../../database-engine/dev-guide/managing-text-and-image-columns-how-to-topics-odbc.md)  
  
  
