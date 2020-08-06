---
title: Criar um arquivo de formato de cópia em massa (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- bulk copy [ODBC], file formats
- bulk copy [ODBC], data files
ms.assetid: 0572fef3-daf5-409e-b557-c2a632f9a06d
author: rothja
ms.author: jroth
ms.openlocfilehash: 9d35342b2f6b25a129df968383d204931d64bfa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87569430"
---
# <a name="create-a-bulk-copy-format-file-odbc"></a><span data-ttu-id="79484-102">Criar um arquivo de formato de cópia em massa (ODBC)</span><span class="sxs-lookup"><span data-stu-id="79484-102">Create a Bulk Copy Format File (ODBC)</span></span>
  <span data-ttu-id="79484-103">Este exemplo mostra como usar funções de cópia em massa para criar um arquivo de dados e um arquivo de formato.</span><span class="sxs-lookup"><span data-stu-id="79484-103">This sample shows how to use bulk copy functions to create both a data file and a format file.</span></span> <span data-ttu-id="79484-104">Esse exemplo foi desenvolvido para o ODBC versão 3.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="79484-104">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="79484-105">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="79484-105">When possible, use Windows Authentication.</span></span> <span data-ttu-id="79484-106">Se a Autenticação do Windows não estiver disponível, solicite aos usuários que digitem suas credenciais em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="79484-106">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="79484-107">Evite armazenar as credenciais em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="79484-107">Avoid storing credentials in a file.</span></span> <span data-ttu-id="79484-108">Se for necessário manter as credenciais, criptografe-as com a [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532)(em inglês).</span><span class="sxs-lookup"><span data-stu-id="79484-108">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-create-a-bulk-copy-format-file"></a><span data-ttu-id="79484-109">Para criar um arquivo de formato de cópia em massa</span><span class="sxs-lookup"><span data-stu-id="79484-109">To create a bulk copy format file</span></span>  
  
1.  <span data-ttu-id="79484-110">Aloque um identificador de ambiente e um identificador de conexão.</span><span class="sxs-lookup"><span data-stu-id="79484-110">Allocate an environment handle and a connection handle.</span></span>  
  
2.  <span data-ttu-id="79484-111">Defina SQL_COPT_SS_BCP e SQL_BCP_ON para habilitar operações de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="79484-111">Set SQL_COPT_SS_BCP and SQL_BCP_ON to enable bulk copy operations.</span></span>  
  
3.  <span data-ttu-id="79484-112">Conecte-se ao SQL Server.</span><span class="sxs-lookup"><span data-stu-id="79484-112">Connect to SQL Server.</span></span>  
  
4.  <span data-ttu-id="79484-113">Chame [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) para definir as seguintes informações:</span><span class="sxs-lookup"><span data-stu-id="79484-113">Call [bcp_init](../../native-client-odbc-extensions-bulk-copy-functions/bcp-init.md) to set the following information:</span></span>  
  
    -   <span data-ttu-id="79484-114">O nome da tabela ou da exibição da qual ou para a qual será feita a cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="79484-114">The name of the table or view to bulk copy from or to.</span></span>  
  
    -   <span data-ttu-id="79484-115">O nome do arquivo de dados que contém os dados a serem copiados para o banco de dados ou que recebe os dados ao copiar do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="79484-115">The name of the data file that contains the data to copy into the database or that receives data when copying from the database.</span></span>  
  
    -   <span data-ttu-id="79484-116">O nome de um arquivo de dados que receberá qualquer mensagem de erro de cópia em massa (especifique NULL se não desejar um arquivo de mensagens).</span><span class="sxs-lookup"><span data-stu-id="79484-116">The name of a data file to receive any bulk copy error messages (specify NULL if you do not want a message file).</span></span>  
  
    -   <span data-ttu-id="79484-117">A direção da cópia: DB_OUT para o arquivo da tabela ou exibição.</span><span class="sxs-lookup"><span data-stu-id="79484-117">The direction of the copy: DB_OUT to the file from the table or view.</span></span>  
  
5.  <span data-ttu-id="79484-118">Chame [bcp_columns](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) para definir o número de colunas.</span><span class="sxs-lookup"><span data-stu-id="79484-118">Call [bcp_columns](../../native-client-odbc-extensions-bulk-copy-functions/bcp-columns.md) to set the number of columns.</span></span>  
  
6.  <span data-ttu-id="79484-119">Chame [bcp_colfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) para cada coluna para definir suas características no arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="79484-119">Call [bcp_colfmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-colfmt.md) for each column to define its characteristics in the data file.</span></span>  
  
7.  <span data-ttu-id="79484-120">Chame [bcp_writefmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) para criar um arquivo de formato que descreve o arquivo de dados a ser criado pela operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="79484-120">Call [bcp_writefmt](../../native-client-odbc-extensions-bulk-copy-functions/bcp-writefmt.md) to create a format file describing the data file to be created by the bulk copy operation.</span></span>  
  
8.  <span data-ttu-id="79484-121">Chame [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) para executar a operação de cópia em massa.</span><span class="sxs-lookup"><span data-stu-id="79484-121">Call [bcp_exec](../../native-client-odbc-extensions-bulk-copy-functions/bcp-exec.md) to execute the bulk copy operation.</span></span>  
  
 <span data-ttu-id="79484-122">Uma operação de cópia em massa executada dessa forma cria um arquivo de dados que contém os dados copiados e um arquivo de formato que descreve o layout do arquivo de dados.</span><span class="sxs-lookup"><span data-stu-id="79484-122">A bulk copy operation run in this way creates both a data file containing the bulk copied data and a format file describing the layout of the data file.</span></span>  
  
## <a name="example"></a><span data-ttu-id="79484-123">Exemplo</span><span class="sxs-lookup"><span data-stu-id="79484-123">Example</span></span>  
 <span data-ttu-id="79484-124">Será necessária uma fonte de dados ODBC chamada AdventureWorks, cujo banco de dados padrão é o banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="79484-124">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="79484-125">(Você pode baixar o banco de dados de exemplo AdventureWorks do [Microsoft SQL Server exemplos e projetos da comunidade](https://go.microsoft.com/fwlink/?LinkID=85384) Home Page.) Essa fonte de dados deve ser baseada no driver ODBC fornecido pelo sistema operacional (o nome do driver é "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="79484-125">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="79484-126">Se você compilar e executar esse exemplo como um aplicativo de 32 bits em um sistema operacional de 64 bits, deverá criar a fonte de dados ODBC com o Administrador ODBC em %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="79484-126">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="79484-127">Esse aplicativo se conecta à instância padrão do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] do computador.</span><span class="sxs-lookup"><span data-stu-id="79484-127">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="79484-128">Para conectar-se a uma instância nomeada, altere a definição da fonte de dados ODBC para especificar a instância usando o seguinte formato: servidor\instância_nomeada.</span><span class="sxs-lookup"><span data-stu-id="79484-128">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="79484-129">Por padrão, o [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] é instalado em uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="79484-129">By default, [!INCLUDE[ssExpress](../../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="79484-130">Execute a primeira listagem de código ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) para criar a tabela que será usada pelo exemplo.</span><span class="sxs-lookup"><span data-stu-id="79484-130">Execute the first ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to create the table that the sample will use.</span></span>  
  
 <span data-ttu-id="79484-131">Compile a segunda listagem de código (C++) com odbc32.lib e odbcbcp.lib.</span><span class="sxs-lookup"><span data-stu-id="79484-131">Compile the second (C++) code listing with odbc32.lib and odbcbcp.lib.</span></span>  
  
 <span data-ttu-id="79484-132">Execute a terceira listagem de código ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) para excluir a tabela usada pelo exemplo.</span><span class="sxs-lookup"><span data-stu-id="79484-132">Execute the third ([!INCLUDE[tsql](../../../includes/tsql-md.md)]) code listing to delete the table that the sample used.</span></span>  
  
```  
use AdventureWorks  
  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
  
CREATE TABLE BCPDate (cola int, colb datetime)  
insert BCPDate(cola) values(1)   
insert BCPDate(cola) values(2)   
insert BCPDate(cola) values(3)   
insert BCPDate(cola) values(4)  
```  
  
```  
// compile with: odbc32.lib odbcbcp.lib  
#include <stdio.h>  
#include <string.h>  
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
  
   // BCP variables.  
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
  
   // Allocate ODBC connection handle, set bulk copy mode, and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLSetConnectAttr(hdbc1, SQL_COPT_SS_BCP, (void *)SQL_BCP_ON, SQL_IS_INTEGER);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLSetEnvAttr(ODBC version) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Sample uses Integrated Security, create SQL Server DSN using Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"",SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Initialize the bulk copy.  
   retcode = bcp_init(hdbc1, "BCPDate", "BCPODBC.bcp", NULL, DB_OUT);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set the number of output columns.  
   retcode = bcp_columns(hdbc1, 2);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Describe the format of column 1 in the data file.  
   retcode = bcp_colfmt(hdbc1, 1, SQLCHARACTER, -1, 5, NULL, 0, 1);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Describe the format of column 2 in the data file.  
   retcode = bcp_colfmt(hdbc1, 2, SQLCHARACTER, -1, 20, NULL, 0, 2);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Create the format file.  
   retcode = bcp_writefmt(hdbc1, "c:\\BCPFMT.fmt");  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Execute the bulk copy.  
   retcode = bcp_exec(hdbc1, &cRows);  
   if (retcode != SUCCEED) {  
      printf("bcp_init() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("Number of rows bulk copied out = %d.\n", cRows);  
  
   // Cleanup  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
   return(0);  
}  
```  
  
```  
use AdventureWorks  
IF EXISTS (SELECT name FROM sysobjects WHERE name = 'BCPDate')  
     DROP TABLE BCPDate  
GO  
```  
  
## <a name="see-also"></a><span data-ttu-id="79484-133">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="79484-133">See Also</span></span>  
 <span data-ttu-id="79484-134">[Tópicos de instruções sobre cópia em massa com o SQL Server ODBC Driver &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="79484-134">[Bulk Copying with the SQL Server ODBC Driver How-to Topics &#40;ODBC&#41;](bulk-copying-with-the-sql-server-odbc-driver-how-to-topics-odbc.md) </span></span>  
 [<span data-ttu-id="79484-135">Usando arquivos de dados e de formato</span><span class="sxs-lookup"><span data-stu-id="79484-135">Using Data Files and Format Files</span></span>](../../native-client-odbc-bulk-copy-operations/using-data-files-and-format-files.md)  
  
  
