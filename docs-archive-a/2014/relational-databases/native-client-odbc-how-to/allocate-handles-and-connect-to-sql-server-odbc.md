---
title: Alocar identificadores e conectar-se ao SQL Server (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- handles [ODBC]
- handles [ODBC], connection
- handles [ODBC], about handles
ms.assetid: 6172cd52-9c9a-467d-992f-def07f3f3bb1
author: rothja
ms.author: jroth
ms.openlocfilehash: 615a6dbe966b4c681e9cd4285ff55864d7a13370
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685648"
---
# <a name="allocate-handles-and-connect-to-sql-server-odbc"></a><span data-ttu-id="0bc0a-102">Alocar identificadores e se conectar ao SQL Server (ODBC)</span><span class="sxs-lookup"><span data-stu-id="0bc0a-102">Allocate Handles and Connect to SQL Server (ODBC)</span></span>
    
### <a name="to-allocate-handles-and-connect-to-sql-server"></a><span data-ttu-id="0bc0a-103">Para alocar identificadores e se conectar ao SQL Server</span><span class="sxs-lookup"><span data-stu-id="0bc0a-103">To allocate handles and connect to SQL Server</span></span>  
  
1.  <span data-ttu-id="0bc0a-104">Inclua o arquivos de cabeçalho ODBC Sql.h, Sqlext.h, Sqltypes.h.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-104">Include the ODBC header files Sql.h, Sqlext.h, Sqltypes.h.</span></span>  
  
2.  <span data-ttu-id="0bc0a-105">Inclua o arquivo de cabeçalho específico do driver do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], Odbcss.h.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-105">Include the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver-specific header file, Odbcss.h.</span></span>  
  
3.  <span data-ttu-id="0bc0a-106">Chame [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) com um `HandleType` de SQL_HANDLE_ENV para inicializar o ODBC e alocar um identificador de ambiente.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-106">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a `HandleType` of SQL_HANDLE_ENV to initialize ODBC and allocate an environment handle.</span></span>  
  
4.  <span data-ttu-id="0bc0a-107">Chame [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) com `Attribute` definido como SQL_ATTR_ODBC_VERSION e `ValuePtr` defina como SQL_OV_ODBC3 para indicar que o aplicativo usará chamadas de função de formato ODBC 3. x.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-107">Call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) with `Attribute` set to SQL_ATTR_ODBC_VERSION and `ValuePtr` set to SQL_OV_ODBC3 to indicate the application will use ODBC 3.x-format function calls.</span></span>  
  
5.  <span data-ttu-id="0bc0a-108">Opcionalmente, chame [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) para definir outras opções de ambiente ou chame [SQLGetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=58403) para obter opções de ambiente.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-108">Optionally, call [SQLSetEnvAttr](../native-client-odbc-api/sqlsetenvattr.md) to set other environment options, or call [SQLGetEnvAttr](https://go.microsoft.com/fwlink/?LinkId=58403) to get environment options.</span></span>  
  
6.  <span data-ttu-id="0bc0a-109">Chame [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) com um `HandleType` de SQL_HANDLE_DBC para alocar um identificador de conexão.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-109">Call [SQLAllocHandle](https://go.microsoft.com/fwlink/?LinkId=58396) with a `HandleType` of SQL_HANDLE_DBC to allocate a connection handle.</span></span>  
  
7.  <span data-ttu-id="0bc0a-110">Opcionalmente, chame [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) para definir opções de conexão ou chame [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) para obter opções de conexão.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-110">Optionally, call [SQLSetConnectAttr](../native-client-odbc-api/sqlsetconnectattr.md) to set connection options, or call [SQLGetConnectAttr](../native-client-odbc-api/sqlgetconnectattr.md) to get connection options.</span></span>  
  
8.  <span data-ttu-id="0bc0a-111">Chame o SQLConnect para usar uma fonte de dados existente para se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0bc0a-111">Call SQLConnect to use an existing data source to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="0bc0a-112">Ou</span><span class="sxs-lookup"><span data-stu-id="0bc0a-112">Or</span></span>  
  
     <span data-ttu-id="0bc0a-113">Chame [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) para usar uma cadeia de conexão para se conectar ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0bc0a-113">Call [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) to use a connection string to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
     <span data-ttu-id="0bc0a-114">Uma cadeia de conexão do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] completa mínima tem uma de duas formas:</span><span class="sxs-lookup"><span data-stu-id="0bc0a-114">A minimum complete [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection string has one of two forms:</span></span>  
  
    ```  
    DSN=dsn_name;Trusted_connection=yes;  
    DRIVER={SQL Server Native Client 10.0};SERVER=server;Trusted_connection=yes;  
    ```  
  
     <span data-ttu-id="0bc0a-115">Se a cadeia de conexão não estiver completa, o `SQLDriverConnect` poderá solicitar as informações necessárias.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-115">If the connection string is not complete, `SQLDriverConnect` can prompt for the required information.</span></span> <span data-ttu-id="0bc0a-116">Isso é controlado pelo valor especificado para o parâmetro *DriverCompletion* .</span><span class="sxs-lookup"><span data-stu-id="0bc0a-116">This is controlled by the value specified for the *DriverCompletion* parameter.</span></span>  
  
     <span data-ttu-id="0bc0a-117">\- ou –</span><span class="sxs-lookup"><span data-stu-id="0bc0a-117">\- or -</span></span>  
  
     <span data-ttu-id="0bc0a-118">Chame [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md) várias vezes de maneira iterativa para criar a cadeia de conexão e conectar-se ao [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="0bc0a-118">Call [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md) multiple times in an iterative fashion to build the connection string and connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
9. <span data-ttu-id="0bc0a-119">Opcionalmente, chame [SQLGetInfo](../native-client-odbc-api/sqlgetinfo.md) para obter atributos de driver e comportamento para a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-119">Optionally, call [SQLGetInfo](../native-client-odbc-api/sqlgetinfo.md) to get driver attributes and behavior for the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] data source.</span></span>  
  
10. <span data-ttu-id="0bc0a-120">Aloque e use instruções.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-120">Allocate and use statements.</span></span>  
  
11. <span data-ttu-id="0bc0a-121">Chame SQLDisconnect para desconectar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e tornar o identificador de conexão disponível para uma nova conexão.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-121">Call SQLDisconnect to disconnect from [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and make the connection handle available for a new connection.</span></span>  
  
12. <span data-ttu-id="0bc0a-122">Chame [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) com um `HandleType` de SQL_HANDLE_DBC para liberar o identificador de conexão.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-122">Call [SQLFreeHandle](../native-client-odbc-api/sqlfreehandle.md) with a `HandleType` of SQL_HANDLE_DBC to free the connection handle.</span></span>  
  
13. <span data-ttu-id="0bc0a-123">Chame `SQLFreeHandle` com um `HandleType` SQL_HANDLE_ENV para liberar o identificador de ambiente.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-123">Call `SQLFreeHandle` with a `HandleType` of SQL_HANDLE_ENV to free the environment handle.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="0bc0a-124">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-124">When possible, use Windows Authentication.</span></span> <span data-ttu-id="0bc0a-125">Se a Autenticação do Windows não estiver disponível, solicite aos usuários que digitem suas credenciais em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-125">If Windows Authentication is not available, prompt users to enter their credentials at run time.</span></span> <span data-ttu-id="0bc0a-126">Evite armazenar as credenciais em um arquivo.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-126">Avoid storing credentials in a file.</span></span> <span data-ttu-id="0bc0a-127">Se for necessário manter as credenciais, criptografe-as com a [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532)(em inglês).</span><span class="sxs-lookup"><span data-stu-id="0bc0a-127">If you must persist credentials, you should encrypt them with the [Win32 crypto API](https://go.microsoft.com/fwlink/?LinkId=64532).</span></span>  
  
## <a name="example"></a><span data-ttu-id="0bc0a-128">Exemplo</span><span class="sxs-lookup"><span data-stu-id="0bc0a-128">Example</span></span>  
 <span data-ttu-id="0bc0a-129">Este exemplo mostra uma chamada de `SQLDriverConnect` para conectar-se a uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] sem exigir uma fonte de dados ODBC existente.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-129">This example shows a call to `SQLDriverConnect` to connect to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] without requiring an existing ODBC data source.</span></span> <span data-ttu-id="0bc0a-130">A passagem de uma cadeia de conexão incompleta a `SQLDriverConnect`, faz o driver ODBC solicitar que o usuário digite as informações ausentes.</span><span class="sxs-lookup"><span data-stu-id="0bc0a-130">By passing an incomplete connection string to `SQLDriverConnect`, it causes the ODBC driver to prompt the user to enter the missing information.</span></span>  
  
```  
#define MAXBUFLEN   255  
  
SQLHENV      henv = SQL_NULL_HENV;  
SQLHDBC      hdbc1 = SQL_NULL_HDBC;  
SQLHSTMT      hstmt1 = SQL_NULL_HSTMT;  
  
SQLCHAR      ConnStrIn[MAXBUFLEN] =  
         "DRIVER={SQL Server Native Client 10.0};SERVER=MyServer";  
  
SQLCHAR      ConnStrOut[MAXBUFLEN];  
SQLSMALLINT   cbConnStrOut = 0;  
  
// Make connection without data source. Ask that driver   
// prompt if insufficient information. Driver returns  
// SQL_ERROR and application prompts user  
// for missing information. Window handle not needed for  
// SQL_DRIVER_NOPROMPT.  
retcode = SQLDriverConnect(hdbc1,      // Connection handle  
                  NULL,         // Window handle  
                  ConnStrIn,      // Input connect string  
                  SQL_NTS,         // Null-terminated string  
                  ConnStrOut,      // Address of output buffer  
                  MAXBUFLEN,      // Size of output buffer  
                  &cbConnStrOut,   // Address of output length  
                  SQL_DRIVER_PROMPT);  
```  
  
  
