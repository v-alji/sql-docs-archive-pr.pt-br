---
title: Consultas de execução longa de log (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- queries [ODBC]
ms.assetid: b9c1ddce-1dd9-409d-a414-8b544d616273
author: rothja
ms.author: jroth
ms.openlocfilehash: f73dbf6fe8fc4b3dfbbbc0012d14a58614b218dd
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685105"
---
# <a name="log-long-running-queries-odbc"></a><span data-ttu-id="d386f-102">Registrar Consultas de execução longa (ODBC)</span><span class="sxs-lookup"><span data-stu-id="d386f-102">Log Long-Running Queries (ODBC)</span></span>
  <span data-ttu-id="d386f-103">Este exemplo mostra as opções específicas do driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para registrar consultas de longa execução.</span><span class="sxs-lookup"><span data-stu-id="d386f-103">This sample shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver-specific options to log long-running queries.</span></span> <span data-ttu-id="d386f-104">Quando executado, esse exemplo cria o Odbcqry.log, que contém uma lista de consultas cuja execução excede um conjunto de intervalos pelo aplicativo.</span><span class="sxs-lookup"><span data-stu-id="d386f-104">When run, this sample creates Odbcqry.log, which contains a list of queries whose execution exceeds an interval set by the application.</span></span> <span data-ttu-id="d386f-105">Este exemplo não tem suporte em IA64.</span><span class="sxs-lookup"><span data-stu-id="d386f-105">This sample is not supported on IA64.</span></span> <span data-ttu-id="d386f-106">Esse exemplo foi desenvolvido para o ODBC versão 3.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="d386f-106">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d386f-107">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="d386f-107">When possible, use Windows Authentication.</span></span> <span data-ttu-id="d386f-108">Se a Autenticação do Windows não estiver disponível, solicite aos usuários que digitem suas credenciais em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="d386f-108">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="d386f-109">Evite armazenar as credenciais em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="d386f-109">Avoid storing credentials in a file.</span></span> <span data-ttu-id="d386f-110">Se for necessário manter as credenciais, criptografe-as com a [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532)(em inglês).</span><span class="sxs-lookup"><span data-stu-id="d386f-110">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-log-long-running-queries-using-odbc-administrator"></a><span data-ttu-id="d386f-111">Para registrar consultas de execução demorada que usam o Administrador ODBC</span><span class="sxs-lookup"><span data-stu-id="d386f-111">To log long-running queries using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="d386f-112">No **painel de controle**, clique duas vezes em **Ferramentas administrativas** e, em seguida, clique duas vezes em **fontes de dados (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="d386f-112">In **Control Panel**, double-click **Administrative Tools** and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="d386f-113">(Como alternativa, você pode executar odbcad32.exe no prompt de comando.)</span><span class="sxs-lookup"><span data-stu-id="d386f-113">(Alternatively, you can run odbcad32.exe from the command prompt.)</span></span>  
  
2.  <span data-ttu-id="d386f-114">Clique na guia **DSN do usuário**, DSN do **sistema**ou DSN de **arquivo** .</span><span class="sxs-lookup"><span data-stu-id="d386f-114">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="d386f-115">Clique na fonte de dados para a qual serão registradas as consultas de execução demorada.</span><span class="sxs-lookup"><span data-stu-id="d386f-115">Click the data source for which to log long-running queries.</span></span>  
  
4.  <span data-ttu-id="d386f-116">Clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="d386f-116">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="d386f-117">No Microsoft SQL Server configurar o assistente de DSN, navegue até a página com **salvar consultas de execução longa no arquivo de log**.</span><span class="sxs-lookup"><span data-stu-id="d386f-117">In the Microsoft SQL Server Configure DSN Wizard, navigate to the page with **Save long-running queries to the log file**.</span></span>  
  
6.  <span data-ttu-id="d386f-118">Selecione **salvar consultas de execução longa no arquivo de log**.</span><span class="sxs-lookup"><span data-stu-id="d386f-118">Select **Save long-running queries to the log file**.</span></span> <span data-ttu-id="d386f-119">Na caixa, coloque o nome do arquivo em que as consultas de execução demorada devem ser registradas.</span><span class="sxs-lookup"><span data-stu-id="d386f-119">In the box, place the name of the file where the long-running queries should be logged.</span></span> <span data-ttu-id="d386f-120">Opcionalmente, clique em **procurar** para procurar o log de consultas no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="d386f-120">Optionally, click **Browse** to browse the file system for the query log.</span></span>  
  
7.  <span data-ttu-id="d386f-121">Defina um intervalo de tempo limite de consulta, em milissegundos, na caixa **tempo de consulta longa (milissegundos)** .</span><span class="sxs-lookup"><span data-stu-id="d386f-121">Set a query time-out interval, in milliseconds, in the **Long query time (milliseconds)** box.</span></span>  
  
### <a name="to-log-long-running-queries-data-programmatically"></a><span data-ttu-id="d386f-122">Para registrar dados de consultas de execução demorada via programação</span><span class="sxs-lookup"><span data-stu-id="d386f-122">To log long-running queries data programmatically</span></span>  
  
1.  <span data-ttu-id="d386f-123">Chame [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) com SQL_COPT_SS_PERF_QUERY_LOG e o caminho completo e o nome de arquivo do arquivo de log de consulta de longa execução.</span><span class="sxs-lookup"><span data-stu-id="d386f-123">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_QUERY_LOG and the full path and file name of the long-running query log file.</span></span> <span data-ttu-id="d386f-124">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="d386f-124">For example:</span></span>  
  
    ```  
    C:\\Odbcqry.log  
    ```  
  
2.  <span data-ttu-id="d386f-125">Chame [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) com SQL_COPT_SS_PERF_QUERY_INTERVAL e defina como o intervalo de tempo limite, em milissegundos.</span><span class="sxs-lookup"><span data-stu-id="d386f-125">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_QUERY_INTERVAL and set to the time-out interval, in milliseconds.</span></span>  
  
3.  <span data-ttu-id="d386f-126">Chame [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) com SQL_COPT_SS_PERF_QUERY e SQL_PERF_START para iniciar o log de consultas de longa execução.</span><span class="sxs-lookup"><span data-stu-id="d386f-126">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_QUERY and SQL_PERF_START to start logging long-running queries.</span></span>  
  
4.  <span data-ttu-id="d386f-127">Chame [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) com SQL_COPT_SS_PERF_QUERY e SQL_PERF_STOP para interromper o log de consultas de longa execução.</span><span class="sxs-lookup"><span data-stu-id="d386f-127">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_QUERY and SQL_PERF_STOP to stop logging long-running queries.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d386f-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d386f-128">Example</span></span>  
 <span data-ttu-id="d386f-129">Será necessária uma fonte de dados ODBC chamada AdventureWorks, cujo banco de dados padrão é o banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="d386f-129">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="d386f-130">(Você pode baixar o banco de dados de exemplo AdventureWorks do [Microsoft SQL Server exemplos e projetos da comunidade](https://go.microsoft.com/fwlink/?LinkID=85384) Home Page.) Essa fonte de dados deve ser baseada no driver ODBC fornecido pelo sistema operacional (o nome do driver é "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="d386f-130">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="d386f-131">Se você compilar e executar esse exemplo como um aplicativo de 32 bits em um sistema operacional de 64 bits, deverá criar a fonte de dados ODBC com o Administrador ODBC em %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="d386f-131">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="d386f-132">Esse aplicativo se conecta à instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do computador.</span><span class="sxs-lookup"><span data-stu-id="d386f-132">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="d386f-133">Para conectar-se a uma instância nomeada, altere a definição da fonte de dados ODBC para especificar a instância usando o seguinte formato: servidor\instância_nomeada.</span><span class="sxs-lookup"><span data-stu-id="d386f-133">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="d386f-134">Por padrão, o [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] é instalado em uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="d386f-134">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="d386f-135">Compile com odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="d386f-135">Compile with odbc32.lib.</span></span>  
  
```  
// compile with: odbc32.lib  
#include <stdio.h>  
#include <string.h>  
#include <windows.h>  
#include <sql.h>  
#include <sqlext.h>  
#include <odbcss.h>  
  
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
}  
  
int main() {  
   RETCODE retcode;  
  
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
  
   // Allocate ODBC connection handle and connect.  
   retcode = SQLAllocHandle(SQL_HANDLE_DBC, henv, &hdbc1);  
   if ( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(hdbc1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // sample uses Integrated Security, create SQL Server DSN using the Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"",SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set options to log long-running queries, including the file to use for the log.  
   retcode = SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_QUERY_LOG, &"odbcqry.log", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set the long-running query interval (in milliseconds).  Note that for version 2.50 and 2.65  
   // drivers, this value is specified in seconds, not milliseconds.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_QUERY_INTERVAL, (SQLPOINTER)3000, SQL_IS_UINTEGER);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Start the long-running query log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_QUERY, (SQLPOINTER)SQL_PERF_START, SQL_IS_UINTEGER);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle then execute commands.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle(hstmt1) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Purchasing.Vendor", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults Failed\n\n");  
         Cleanup();  
           return(9);  
      }  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Sales.Store", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Generate a long-running query.  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"waitfor delay '00:00:04' ", SQL_NTS);  
   if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if ( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Cleanup  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="d386f-136">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d386f-136">See Also</span></span>  
 [<span data-ttu-id="d386f-137">Tópicos de instruções de desempenho do driver ODBC de criação de perfil &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="d386f-137">Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;</span></span>](profiling-odbc-driver-performance-odbc.md)  
  
  
