---
title: Cópia em massa usando um arquivo de formato (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 10/18/2019
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy using format file [ODBC]
- ODBC, bulk copy operations
ms.assetid: 970fd3af-f918-4fc3-a5b1-92596515d4de
author: rothja
ms.author: jroth
ms.openlocfilehash: 19959d5f1da7243275c60560963d577446f809b8
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685645"
---
# <a name="bulk-copy-by-using-a-format-file-odbc"></a><span data-ttu-id="85af0-102">Copiar em massa usando um arquivo de formato (ODBC)</span><span class="sxs-lookup"><span data-stu-id="85af0-102">Bulk Copy by Using a Format File (ODBC)</span></span>
  <span data-ttu-id="85af0-103">Este exemplo mostra como usar a função ODBC bcp_init com um arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="85af0-103">This sample shows how to use the ODBC bcp_init function with a format file.</span></span>  
  
### <a name="to-bulk-copy-by-using-a-format-file"></a><span data-ttu-id="85af0-104">Para copiar em massa usando um arquivo de formato</span><span class="sxs-lookup"><span data-stu-id="85af0-104">To bulk copy by using a format file</span></span>  
  
1.  <span data-ttu-id="85af0-105">Aloque um identificador de ambiente e um identificador de conexão.</span><span class="sxs-lookup"><span data-stu-id="85af0-105">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="85af0-106">Defina SQL_COPT_SS_BCP e SQL_BCP_ON para habilitar operações de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="85af0-106">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="85af0-107">Conecte-se a Microsoft SQL Server.</span><span class="sxs-lookup"><span data-stu-id="85af0-107">Connect to Microsoft SQL Server.</span></span>  
  
4.  <span data-ttu-id="85af0-108">Chame [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) para definir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="85af0-108">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="85af0-109">O nome da tabela ou da exibição da qual ou para a qual será feita a cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="85af0-109">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="85af0-110">O nome do arquivo de dados que contém os dados a serem copiados para o banco de dados ou que recebe os dados ao copiar do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="85af0-110">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="85af0-111">O nome de um arquivo de dados que receberá qualquer mensagem de erro de cópia em massa (especifique NULL se não desejar um arquivo de mensagens).</span><span class="sxs-lookup"><span data-stu-id="85af0-111">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="85af0-112">A direção da cópia: DB_IN do arquivo para a tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="85af0-112">The direction of the copy: DB_IN from the file to the table or view.</span></span>  
  
5.  <span data-ttu-id="85af0-113">Chame [bcp_readfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) para ler o arquivo de formato que descreve o arquivo de dados a ser usado pela operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="85af0-113">Call [bcp_readfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-readfmt.md) to read the format file describing the data file to be used by the bulk copy operation.</span></span>  
  
6.  <span data-ttu-id="85af0-114">Chame [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) para executar a operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="85af0-114">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
## <a name="example"></a><span data-ttu-id="85af0-115">Exemplo</span><span class="sxs-lookup"><span data-stu-id="85af0-115">Example</span></span>  
 <span data-ttu-id="85af0-116">Este exemplo não tem suporte em IA64.</span><span class="sxs-lookup"><span data-stu-id="85af0-116">This sample is not supported on IA64.</span></span>  
  
 <span data-ttu-id="85af0-117">Será necessária uma fonte de dados ODBC chamada AdventureWorks, cujo banco de dados padrão é o banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="85af0-117">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="85af0-118">(Você pode baixar o banco de dados de exemplo AdventureWorks do [Microsoft SQL Server exemplos e projetos da comunidade](https://go.microsoft.com/fwlink/?LinkID=85384) Home Page.) Essa fonte de dados deve ser baseada no driver ODBC fornecido pelo sistema operacional (o nome do driver é "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="85af0-118">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="85af0-119">Se você compilar e executar esse exemplo como um aplicativo de 32 bits em um sistema operacional de 64 bits, deverá criar a fonte de dados ODBC com o Administrador ODBC em %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="85af0-119">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="85af0-120">Esse aplicativo se conecta à instância padrão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] do computador.</span><span class="sxs-lookup"><span data-stu-id="85af0-120">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="85af0-121">Para conectar-se a uma instância nomeada, altere a definição da fonte de dados ODBC para especificar a instância usando o seguinte formato: servidor\instância_nomeada.</span><span class="sxs-lookup"><span data-stu-id="85af0-121">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="85af0-122">Por padrão, o [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] é instalado em uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="85af0-122">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="85af0-123">Execute a primeira listagem de código ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) para criar a tabela que será usada pelo exemplo.</span><span class="sxs-lookup"><span data-stu-id="85af0-123">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create the table that the sample will use.</span></span>  
  
 <span data-ttu-id="85af0-124">Copie a segunda listagem de código e cole-a em um arquivo denominado Bcpfmt.fmt.</span><span class="sxs-lookup"><span data-stu-id="85af0-124">Copy the second code listing and paste it into a file called Bcpfmt.fmt.</span></span> <span data-ttu-id="85af0-125">Cada coluna na tabela é separada por um caractere de tabulação.</span><span class="sxs-lookup"><span data-stu-id="85af0-125">Each column in the table is separated by a tab character.</span></span>  
  
 <span data-ttu-id="85af0-126">Copie a terceira listagem de código e cole-a em um arquivo denominado Bcpodbc.bcp.</span><span class="sxs-lookup"><span data-stu-id="85af0-126">Copy the third code listing and paste it into a file called Bcpodbc.bcp.</span></span> <span data-ttu-id="85af0-127">Um caractere de tabulação precede cada retorno de carro no arquivo.</span><span class="sxs-lookup"><span data-stu-id="85af0-127">A tab character precedes each carriage return in the file.</span></span>  
  
 <span data-ttu-id="85af0-128">Compile a quarta listagem de código (C++) com odbc32.lib e odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="85af0-128">Compile the fourth (C++) code listing with odbc32.lib and odbcbcp.lib.</span></span> <span data-ttu-id="85af0-129">Se você compilou com o MSBuild.exe, copie primeiro o Bcpfmt.fmt e o Bcpodbc.bcp do diretório do projeto no diretório com o .exe e, em seguida, invoque o .exe.</span><span class="sxs-lookup"><span data-stu-id="85af0-129">If you built with MSBuild.exe, copy Bcpfmt.fmt and Bcpodbc.bcp from the project directory into the directory with the .exe and then invoke the .exe.</span></span>  
  
 <span data-ttu-id="85af0-130">Execute a quinta listagem de código ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) para excluir a tabela usada pelo exemplo.</span><span class="sxs-lookup"><span data-stu-id="85af0-130">Execute the fifth ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the table that the sample used.</span></span>  
  
```sql
use AdventureWorks  
CREATE TABLE BCPDate (cola int, colb datetime)  
```  
  
```  
8.0  
2  
1SQLCHAR04"\t"1colaSQL_Latin1_General_Cp437_Bin  
2SQLCHAR08"\r\n"2colbSQL_Latin1_General_Cp437_Bin  
```  
  
```  
1  
2  
```  
  
```cpp
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
SQLHENV henv = SQL_NULL_HENV;  
HDBC hdbc1 = SQL_NULL_HDBC;   
  
void Cleanup() {  
   if (hdbc1 != SQL_NULL_HDBC) {  
      SQLDisconnect(hdbc1);  
      SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   }  
  
   if (henv != SQL_NULL_HENV)  
      SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
  
int main() {  
   RETCODE retcode;  
   SDWORD cRows;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
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
  
   // Allocate ODBC connection handle, set BCP mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetConnectAttr(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security. Create SQL Server DSN using Windows NT authentication.  
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_IN);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_init(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Read the format file.  
   retcode = bcp_readfmt(hdbc1, "BCPFMT.fmt");  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_readfmt(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if ( (retcode != SUCCEED) ) {  
      printf("bcp_exec(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied in = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
```sql
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="85af0-131">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="85af0-131">See Also</span></span>  
 <span data-ttu-id="85af0-132">[Tópicos de instruções sobre cópia em massa com o SQL Server ODBC Driver &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="85af0-132">[Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="85af0-133">Usando arquivos de dados e de formato</span><span class="sxs-lookup"><span data-stu-id="85af0-133">Using Data Files and Format Files</span></span>](../../native-client-odbc-bulk-copy-operations/using-data-files-and-format-files.md)  
  
  
