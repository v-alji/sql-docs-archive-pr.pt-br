---
title: Dados de desempenho do driver de perfil (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- driver performance data [ODBC]
ms.assetid: b997790a-8cc6-4800-8867-74c1bef07be3
author: rothja
ms.author: jroth
ms.openlocfilehash: 3575cfd304d526bdb25eee6a2578d67c6bb67bc9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679940"
---
# <a name="profile-driver-performance-data-odbc"></a><span data-ttu-id="e18da-102">Analisar dados de desempenho de driver (ODBC)</span><span class="sxs-lookup"><span data-stu-id="e18da-102">Profile Driver Performance Data (ODBC)</span></span>
  <span data-ttu-id="e18da-103">Este exemplo mostra as opções específicas do driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para registrar estatísticas de desempenho.</span><span class="sxs-lookup"><span data-stu-id="e18da-103">This sample shows the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] ODBC driver-specific options to record performance statistics.</span></span> <span data-ttu-id="e18da-104">O exemplo cria um arquivo: odbcperf.log. Esse exemplo mostra tanto a criação de um arquivo de log de dados de desempenho quanto a exibição dos dados de desempenho diretamente da estrutura de dados SQLPERF (a estrutura SQLPERF é definida em Odbcss.h.).</span><span class="sxs-lookup"><span data-stu-id="e18da-104">The sample creates one file: odbcperf.log.This sample shows both the creation of a performance data log file and displaying performance data directly from the SQLPERF data structure (The SQLPERF structure is defined in Odbcss.h.).</span></span> <span data-ttu-id="e18da-105">Esse exemplo foi desenvolvido para o ODBC versão 3.0 ou posterior.</span><span class="sxs-lookup"><span data-stu-id="e18da-105">This sample was developed for ODBC version 3.0 or later.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="e18da-106">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="e18da-106">When possible, use Windows Authentication.</span></span> <span data-ttu-id="e18da-107">Se a Autenticação do Windows não estiver disponível, solicite aos usuários que digitem suas credenciais em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="e18da-107">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="e18da-108">Evite armazenar as credenciais em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="e18da-108">Avoid storing credentials in a file.</span></span> <span data-ttu-id="e18da-109">Se for necessário manter as credenciais, criptografe-as com a [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532)(em inglês).</span><span class="sxs-lookup"><span data-stu-id="e18da-109">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
### <a name="to-log-driver-performance-data-using-odbc-administrator"></a><span data-ttu-id="e18da-110">Para registrar dados de desempenho de driver usando o Administrador ODBC</span><span class="sxs-lookup"><span data-stu-id="e18da-110">To log driver performance data using ODBC Administrator</span></span>  
  
1.  <span data-ttu-id="e18da-111">No **painel de controle**, clique duas vezes em **Ferramentas administrativas** e, em seguida, clique duas vezes em **fontes de dados (ODBC)**.</span><span class="sxs-lookup"><span data-stu-id="e18da-111">In **Control Panel**, double-click **Administrative Tools** and then double-click **Data Sources (ODBC)**.</span></span> <span data-ttu-id="e18da-112">Como alternativa, você pode invocar odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="e18da-112">Alternatively, you can invoke odbcad32.exe.</span></span>  
  
2.  <span data-ttu-id="e18da-113">Clique na guia **DSN do usuário**, DSN do **sistema**ou DSN de **arquivo** .</span><span class="sxs-lookup"><span data-stu-id="e18da-113">Click the **User DSN**, **System DSN**, or **File DSN** tab.</span></span>  
  
3.  <span data-ttu-id="e18da-114">Clique na fonte de dados para a qual você registrará o desempenho.</span><span class="sxs-lookup"><span data-stu-id="e18da-114">Click the data source for which to log performance.</span></span>  
  
4.  <span data-ttu-id="e18da-115">Clique em **Configurar**.</span><span class="sxs-lookup"><span data-stu-id="e18da-115">Click **Configure**.</span></span>  
  
5.  <span data-ttu-id="e18da-116">No Microsoft SQL Server configurar o assistente de DSN, navegue até a página com **log ODBC Driver Statistics para o arquivo de log**.</span><span class="sxs-lookup"><span data-stu-id="e18da-116">In the Microsoft SQL Server Configure DSN Wizard, navigate to the page with **Log ODBC driver statistics to the log file**.</span></span>  
  
6.  <span data-ttu-id="e18da-117">Selecione **registrar estatísticas do driver ODBC para o arquivo de log**.</span><span class="sxs-lookup"><span data-stu-id="e18da-117">Select **Log ODBC driver statistics to the log file**.</span></span> <span data-ttu-id="e18da-118">Na caixa, coloque o nome do arquivo em que as estatísticas deveriam ser registradas.</span><span class="sxs-lookup"><span data-stu-id="e18da-118">In the box, place the name of the file where the statistics should be logged.</span></span> <span data-ttu-id="e18da-119">Opcionalmente, clique em **procurar** para procurar o log de estatísticas no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="e18da-119">Optionally, click **Browse** to browse the file system for the statistics log.</span></span>  
  
### <a name="to-log-driver-performance-data-programmatically"></a><span data-ttu-id="e18da-120">Para registrar os dados de desempenho de driver por programação</span><span class="sxs-lookup"><span data-stu-id="e18da-120">To log driver performance data programmatically</span></span>  
  
1.  <span data-ttu-id="e18da-121">Chame [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) com SQL_COPT_SS_PERF_DATA_LOG e o caminho completo e o nome de arquivo do arquivo de log de dados de desempenho.</span><span class="sxs-lookup"><span data-stu-id="e18da-121">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA_LOG and the full path and file name of the performance data log file.</span></span> <span data-ttu-id="e18da-122">Por exemplo:</span><span class="sxs-lookup"><span data-stu-id="e18da-122">For example:</span></span>  
  
    ```  
    "C:\\Odbcperf.log"  
    ```  
  
2.  <span data-ttu-id="e18da-123">Chame [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) com SQL_COPT_SS_PERF_DATA e SQL_PERF_START para iniciar o log de dados de desempenho.</span><span class="sxs-lookup"><span data-stu-id="e18da-123">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_START to start logging performance data.</span></span>  
  
3.  <span data-ttu-id="e18da-124">Opcionalmente, chame [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) com SQL_COPT_SS_LOG_NOW e NULL para gravar um registro delimitado por tabulação de dados de desempenho no arquivo de log de dados de desempenho.</span><span class="sxs-lookup"><span data-stu-id="e18da-124">Optionally, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_LOG_NOW and NULL to write a tab-delimited record of performance data to the performance data log file.</span></span> <span data-ttu-id="e18da-125">Isso pode ser feito várias vezes enquanto o aplicativo é executado.</span><span class="sxs-lookup"><span data-stu-id="e18da-125">This can be done multiple times as the application runs.</span></span>  
  
4.  <span data-ttu-id="e18da-126">Chame [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) com SQL_COPT_SS_PERF_DATA e SQL_PERF_STOP para interromper o log de dados de desempenho.</span><span class="sxs-lookup"><span data-stu-id="e18da-126">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_STOP to stop logging performance data.</span></span>  
  
### <a name="to-pull-driver-performance-data-into-an-application"></a><span data-ttu-id="e18da-127">Para receber os dados de desempenho de driver em um aplicativo</span><span class="sxs-lookup"><span data-stu-id="e18da-127">To pull driver performance data into an application</span></span>  
  
1.  <span data-ttu-id="e18da-128">Chame [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) com SQL_COPT_SS_PERF_DATA e SQL_PERF_START para iniciar a criação de perfil de dados de desempenho.</span><span class="sxs-lookup"><span data-stu-id="e18da-128">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_START to start profiling performance data.</span></span>  
  
2.  <span data-ttu-id="e18da-129">Chame [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) com SQL_COPT_SS_PERF_DATA e o endereço de um ponteiro para uma estrutura SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="e18da-129">Call [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) with SQL_COPT_SS_PERF_DATA and the address of a pointer to a SQLPERF structure.</span></span> <span data-ttu-id="e18da-130">A primeira chamada define o ponteiro como o endereço de uma estrutura SQLPERF válida que contém os dados de desempenho atuais.</span><span class="sxs-lookup"><span data-stu-id="e18da-130">The first such call sets the pointer to the address of a valid SQLPERF structure that contains current performance data.</span></span> <span data-ttu-id="e18da-131">O driver não atualiza os dados continuamente na estrutura de desempenho.</span><span class="sxs-lookup"><span data-stu-id="e18da-131">The driver does not continually refresh the data in the performance structure.</span></span> <span data-ttu-id="e18da-132">O aplicativo deve repetir a chamada para [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) sempre que precisar atualizar a estrutura com dados de desempenho mais atuais.</span><span class="sxs-lookup"><span data-stu-id="e18da-132">The application must repeat the call to [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) any time it needs to refresh the structure with more current performance data.</span></span>  
  
3.  <span data-ttu-id="e18da-133">Chame [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) com SQL_COPT_SS_PERF_DATA e SQL_PERF_STOP para interromper o log de dados de desempenho.</span><span class="sxs-lookup"><span data-stu-id="e18da-133">Call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) with SQL_COPT_SS_PERF_DATA and SQL_PERF_STOP to stop logging performance data.</span></span>  
  
## <a name="example"></a><span data-ttu-id="e18da-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="e18da-134">Example</span></span>  
 <span data-ttu-id="e18da-135">Será necessária uma fonte de dados ODBC chamada AdventureWorks, cujo banco de dados padrão é o banco de dados de exemplo AdventureWorks.</span><span class="sxs-lookup"><span data-stu-id="e18da-135">You will need an ODBC data source called AdventureWorks, whose default database is the AdventureWorks sample database.</span></span> <span data-ttu-id="e18da-136">(Você pode baixar o banco de dados de exemplo AdventureWorks do [Microsoft SQL Server exemplos e projetos da comunidade](https://go.microsoft.com/fwlink/?LinkID=85384) Home Page.) Essa fonte de dados deve ser baseada no driver ODBC fornecido pelo sistema operacional (o nome do driver é "SQL Server").</span><span class="sxs-lookup"><span data-stu-id="e18da-136">(You can download the AdventureWorks sample database from the [Microsoft SQL Server Samples and Community Projects](https://go.microsoft.com/fwlink/?LinkID=85384) home page.) This data source must be based on the ODBC driver that is supplied by the operating system (the driver name is "SQL Server").</span></span> <span data-ttu-id="e18da-137">Se você compilar e executar esse exemplo como um aplicativo de 32 bits em um sistema operacional de 64 bits, deverá criar a fonte de dados ODBC com o Administrador ODBC em %windir%\SysWOW64\odbcad32.exe.</span><span class="sxs-lookup"><span data-stu-id="e18da-137">If you will build and run this sample as a 32-bit application on a 64-bit operating system, you must create the ODBC data source with the ODBC Administrator in %windir%\SysWOW64\odbcad32.exe.</span></span>  
  
 <span data-ttu-id="e18da-138">Esse aplicativo se conecta à instância padrão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] do computador.</span><span class="sxs-lookup"><span data-stu-id="e18da-138">This sample connects to your computer's default [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance.</span></span> <span data-ttu-id="e18da-139">Para conectar-se a uma instância nomeada, altere a definição da fonte de dados ODBC para especificar a instância usando o seguinte formato: servidor\instância_nomeada.</span><span class="sxs-lookup"><span data-stu-id="e18da-139">To connect to a named instance, change the definition of the ODBC data source to specify the instance using the following format: server\namedinstance.</span></span> <span data-ttu-id="e18da-140">Por padrão, o [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] é instalado em uma instância nomeada.</span><span class="sxs-lookup"><span data-stu-id="e18da-140">By default, [!INCLUDE[ssExpress](../../includes/ssexpress-md.md)] installs to a named instance.</span></span>  
  
 <span data-ttu-id="e18da-141">Compile com odbc32.lib.</span><span class="sxs-lookup"><span data-stu-id="e18da-141">Compile with odbc32.lib.</span></span>  
  
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
  
   // Pointer to the ODBC driver performance structure.  
   SQLPERF *PerfPtr;  
   SQLINTEGER cbPerfPtr;  
  
   // Allocate the ODBC environment and save handle.  
   retcode = SQLAllocHandle (SQL_HANDLE_ENV, NULL, &henv);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
      printf("SQLAllocHandle(Env) Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Notify ODBC that this is an ODBC 3.0 app.  
   retcode = SQLSetEnvAttr(henv, SQL_ATTR_ODBC_VERSION, (SQLPOINTER) SQL_OV_ODBC3, SQL_IS_INTEGER);  
   if( (retcode != SQL_SUCCESS_WITH_INFO) && (retcode != SQL_SUCCESS)) {  
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
  
   // This sample use Integrated Security. Please create the SQL Server   
   // DSN by using the Windows NT authentication.   
   retcode = SQLConnect(hdbc1, (UCHAR*)"AdventureWorks", SQL_NTS, (UCHAR*)"", SQL_NTS, (UCHAR*)"", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLConnect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Set options to log performance statistics.  Specify file to use for the log.  
   retcode = SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA_LOG, &"odbcperf.log", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Start the performance statistics log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA, (SQLPOINTER)SQL_PERF_START, SQL_IS_UINTEGER);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Allocate statement handle, then execute command.  
   retcode = SQLAllocHandle(SQL_HANDLE_STMT, hdbc1, &hstmt1);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLAllocHandle() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Purchasing.Vendor", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"SELECT * FROM Sales.Store", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Generate a long-running query.  
   retcode = SQLExecDirect(hstmt1, (UCHAR*)"waitfor delay '00:00:04' ", SQL_NTS);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLExecDirect() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Clear any result sets generated.  
   while ( ( retcode = SQLMoreResults(hstmt1) ) != SQL_NO_DATA ) {  
      if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
         printf("SQLMoreResults() Failed\n\n");  
         Cleanup();  
         return(9);  
      }  
   }  
  
   // Write current statistics to the performance log.  
   retcode =   
      SQLSetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA_LOG_NOW, (SQLPOINTER)NULL, SQL_IS_UINTEGER);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLSetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   // Get pointer to current SQLPerf structure.  
   // Print a couple of statistics.  
   retcode =   
      SQLGetConnectAttr( hdbc1, SQL_COPT_SS_PERF_DATA, (SQLPOINTER)&PerfPtr, SQL_IS_POINTER, &cbPerfPtr);  
   if( (retcode != SQL_SUCCESS) && (retcode != SQL_SUCCESS_WITH_INFO) ) {  
      printf("SQLGetConnectAttr() Failed\n\n");  
      Cleanup();  
      return(9);  
   }  
  
   printf("SQLSelects = %d, SQLSelectRows = %d\n", PerfPtr->SQLSelects, PerfPtr->SQLSelectRows);  
  
   // Cleanup  
   SQLFreeHandle(SQL_HANDLE_STMT, hstmt1);  
   SQLDisconnect(hdbc1);  
   SQLFreeHandle(SQL_HANDLE_DBC, hdbc1);  
   SQLFreeHandle(SQL_HANDLE_ENV, henv);  
}  
```  
  
## <a name="see-also"></a><span data-ttu-id="e18da-142">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="e18da-142">See Also</span></span>  
 <span data-ttu-id="e18da-143">[Tópicos de instruções de desempenho do driver ODBC de criação de perfil &#40;ODBC&#41;](profiling-odbc-driver-performance-odbc.md) </span><span class="sxs-lookup"><span data-stu-id="e18da-143">[Profiling ODBC Driver Performance How-to Topics &#40;ODBC&#41;](profiling-odbc-driver-performance-odbc.md) </span></span>  
 [<span data-ttu-id="e18da-144">Criando perfil de desempenho do driver ODBC</span><span class="sxs-lookup"><span data-stu-id="e18da-144">Profiling ODBC Driver Performance</span></span>](../native-client/odbc/profiling-odbc-driver-performance.md)  
  
  
