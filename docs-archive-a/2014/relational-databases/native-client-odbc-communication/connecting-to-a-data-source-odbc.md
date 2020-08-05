---
title: Conectando-se a uma fonte de dados (ODBC) | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- checking connection states
- ODBC data sources, connections
- data sources [SQL Server Native Client]
- SQLBrowseConnect function
- ODBC applications, connections
- ODBC applications, data sources
- connections [SQL Server Native Client]
- SQLConnect function
- SQLDriveConnect function
- verifying connection states
- SQL Server Native Client ODBC driver, data sources
- SQL Server Native Client ODBC driver, connections
ms.assetid: ae30dd1d-06ae-452b-9618-8fd8cd7ba074
author: rothja
ms.author: jroth
ms.openlocfilehash: 25ce5954e45bb8070b5e99d8ebb7bfa9ad149c3a
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87573948"
---
# <a name="connecting-to-a-data-source-odbc"></a><span data-ttu-id="723f6-102">Conectando-se a uma fonte de dados (ODBC)</span><span class="sxs-lookup"><span data-stu-id="723f6-102">Connecting to a Data Source (ODBC)</span></span>
  <span data-ttu-id="723f6-103">Depois de alocar os identificadores de ambiente e conexão e definir quaisquer atributos de conexão, o aplicativo se conectará à fonte de dados ou driver.</span><span class="sxs-lookup"><span data-stu-id="723f6-103">After allocating environment and connection handles and setting any connection attributes, the application connects to the data source or driver.</span></span> <span data-ttu-id="723f6-104">Há três funções que você pode usar para se conectar:</span><span class="sxs-lookup"><span data-stu-id="723f6-104">There are three functions you can use to connect:</span></span>  
  
-   <span data-ttu-id="723f6-105">**SQLConnect**</span><span class="sxs-lookup"><span data-stu-id="723f6-105">**SQLConnect**</span></span>  
  
-   <span data-ttu-id="723f6-106">**SQLDriverConnect**</span><span class="sxs-lookup"><span data-stu-id="723f6-106">**SQLDriverConnect**</span></span>  
  
-   <span data-ttu-id="723f6-107">**SQLBrowseConnect**</span><span class="sxs-lookup"><span data-stu-id="723f6-107">**SQLBrowseConnect**</span></span>  
  
 <span data-ttu-id="723f6-108">Para obter mais informações sobre como fazer conexões com uma fonte de dados, incluindo as várias opções de cadeia de conexão disponíveis, consulte [usando palavras-chave de cadeia de conexão com SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="723f6-108">For more information about making connections to a data source, including the various connection string options available, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
## <a name="sqlconnect"></a><span data-ttu-id="723f6-109">SQLConnect</span><span class="sxs-lookup"><span data-stu-id="723f6-109">SQLConnect</span></span>  
 <span data-ttu-id="723f6-110">O **SQLConnect** é a função de conexão mais simples.</span><span class="sxs-lookup"><span data-stu-id="723f6-110">**SQLConnect** is the simplest connection function.</span></span> <span data-ttu-id="723f6-111">Ela aceita três parâmetros: um nome da fonte de dados, uma ID de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="723f6-111">It accepts three parameters: a data source name, a user ID, and a password.</span></span> <span data-ttu-id="723f6-112">Use o **SQLConnect** quando esses três parâmetros contiverem todas as informações necessárias para se conectar ao banco de dados.</span><span class="sxs-lookup"><span data-stu-id="723f6-112">Use **SQLConnect** when these three parameters contain all the information needed to connect to the database.</span></span> <span data-ttu-id="723f6-113">Para fazer isso, crie uma lista de fontes de dados usando **Sqlsources**; solicitar ao usuário uma fonte de dados, ID de usuário e senha; e, em seguida, chame o **SQLConnect**.</span><span class="sxs-lookup"><span data-stu-id="723f6-113">To do this, build a list of data sources using **SQLDataSources**; prompt the user for a data source, user ID, and password; and then call **SQLConnect**.</span></span>  
  
 <span data-ttu-id="723f6-114">O **SQLConnect** pressupõe que um nome de fonte de dados, ID de usuário e senha são suficientes para se conectar a uma fonte de dados e que a fonte de dados ODBC contém todas as outras informações que o driver ODBC precisa para fazer a conexão.</span><span class="sxs-lookup"><span data-stu-id="723f6-114">**SQLConnect** assumes that a data source name, user ID, and password are sufficient to connect to a data source and that the ODBC data source contains all other information the ODBC driver needs to make the connection.</span></span> <span data-ttu-id="723f6-115">Ao contrário de [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) e [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md), o **SQLConnect** não usa uma cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="723f6-115">Unlike [SQLDriverConnect](../native-client-odbc-api/sqldriverconnect.md) and [SQLBrowseConnect](../native-client-odbc-api/sqlbrowseconnect.md), **SQLConnect** does not use a connection string.</span></span>  
  
## <a name="sqldriverconnect"></a><span data-ttu-id="723f6-116">SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="723f6-116">SQLDriverConnect</span></span>  
 <span data-ttu-id="723f6-117">**SQLDriverConnect** é usado quando mais informações do que o nome da fonte de dados, a ID de usuário e a senha são necessárias.</span><span class="sxs-lookup"><span data-stu-id="723f6-117">**SQLDriverConnect** is used when more information than the data source name, user ID, and password is required.</span></span> <span data-ttu-id="723f6-118">Um dos parâmetros para **SQLDriverConnect** é uma cadeia de conexão que contém informações específicas do driver.</span><span class="sxs-lookup"><span data-stu-id="723f6-118">One of the parameters to **SQLDriverConnect** is a connection string containing driver-specific information.</span></span> <span data-ttu-id="723f6-119">Você pode usar **SQLDriverConnect** em vez de **SQLConnect** pelos seguintes motivos:</span><span class="sxs-lookup"><span data-stu-id="723f6-119">You might use **SQLDriverConnect** instead of **SQLConnect** for the following reasons:</span></span>  
  
-   <span data-ttu-id="723f6-120">Para especificar informações específicas de driver no tempo de conexão.</span><span class="sxs-lookup"><span data-stu-id="723f6-120">To specify driver-specific information at connect time.</span></span>  
  
-   <span data-ttu-id="723f6-121">Para solicitar que o driver instrua o usuário a fornecer informações de conexão.</span><span class="sxs-lookup"><span data-stu-id="723f6-121">To request that the driver prompt the user for connection information.</span></span>  
  
-   <span data-ttu-id="723f6-122">Para se conectar sem usar uma fonte de dados ODBC.</span><span class="sxs-lookup"><span data-stu-id="723f6-122">To connect without using an ODBC data source.</span></span>  
  
 <span data-ttu-id="723f6-123">A cadeia de conexão **SQLDriverConnect** contém uma série de pares de valor de palavra-chave que especificam todas as informações de conexão suportadas por um driver ODBC.</span><span class="sxs-lookup"><span data-stu-id="723f6-123">The **SQLDriverConnect** connection string contains a series of keyword-value pairs that specify all connection information supported by an ODBC driver.</span></span> <span data-ttu-id="723f6-124">Cada driver suporta as palavras-chave ODBC padrão (DSN, FILEDSN, DRIVER, UID, PWD e SAVEFILE), além das palavras-chave específicas de driver para todas as informações de conexão suportadas pelo driver.</span><span class="sxs-lookup"><span data-stu-id="723f6-124">Each driver supports the standard ODBC keywords (DSN, FILEDSN, DRIVER, UID, PWD, and SAVEFILE) in addition to driver-specific keywords for all connection information supported by the driver.</span></span> <span data-ttu-id="723f6-125">**SQLDriverConnect** pode ser usado para se conectar sem uma fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="723f6-125">**SQLDriverConnect** can be used to connect without a data source.</span></span> <span data-ttu-id="723f6-126">Por exemplo, um aplicativo projetado para fazer uma conexão "sem DSN" com uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] pode chamar **SQLDriverConnect** com uma cadeia de conexão que define a ID de logon, a senha, a biblioteca de rede, o nome do servidor para se conectar e o banco de dados padrão a ser usado.</span><span class="sxs-lookup"><span data-stu-id="723f6-126">For example, an application that is designed to make a "DSN-less" connection to an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] can call **SQLDriverConnect** with a connection string that defines the login ID, password, network library, server name to connect to, and default database to use.</span></span>  
  
 <span data-ttu-id="723f6-127">Ao usar o **SQLDriverConnect**, há duas opções para solicitar ao usuário qualquer informação de conexão necessária:</span><span class="sxs-lookup"><span data-stu-id="723f6-127">When using **SQLDriverConnect**, there are two options for prompting the user for any needed connection information:</span></span>  
  
-   <span data-ttu-id="723f6-128">Caixa de diálogo de aplicativo</span><span class="sxs-lookup"><span data-stu-id="723f6-128">Application dialog box</span></span>  
  
     <span data-ttu-id="723f6-129">Você pode criar uma caixa de diálogo de aplicativo que solicita informações de conexão e, em seguida, chama **SQLDriverConnect** com um identificador de janela nulo e *DriverCompletion* definido como SQL_DRIVER_NOPROMPT.</span><span class="sxs-lookup"><span data-stu-id="723f6-129">You can create an application dialog box that prompts for connection information, and then calls **SQLDriverConnect** with a NULL window handle and *DriverCompletion* set to SQL_DRIVER_NOPROMPT.</span></span> <span data-ttu-id="723f6-130">Essas configurações de parâmetro impedem que o driver ODBC abra sua própria caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="723f6-130">These parameter settings prevent the ODBC driver from opening its own dialog box.</span></span> <span data-ttu-id="723f6-131">Esse método é usado quando é importante controlar a interface do usuário do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="723f6-131">This method is used when it is important to control the user interface of the application.</span></span>  
  
-   <span data-ttu-id="723f6-132">Caixa de diálogo de driver</span><span class="sxs-lookup"><span data-stu-id="723f6-132">Driver dialog box</span></span>  
  
     <span data-ttu-id="723f6-133">Você pode codificar o aplicativo para passar um identificador de janela válido para **SQLDriverConnect** e definir o parâmetro *DriverCompletion* como SQL_DRIVER_COMPLETE, SQL_DRIVER_PROMPT ou SQL_DRIVER_COMPLETE_REQUIRED.</span><span class="sxs-lookup"><span data-stu-id="723f6-133">You can code the application to pass a valid window handle to **SQLDriverConnect** and set the *DriverCompletion* parameter to SQL_DRIVER_COMPLETE, SQL_DRIVER_PROMPT, or SQL_DRIVER_COMPLETE_REQUIRED.</span></span> <span data-ttu-id="723f6-134">O driver gera uma caixa de diálogo para solicitar o usuário a fornecer as informações de conexão.</span><span class="sxs-lookup"><span data-stu-id="723f6-134">The driver then generates a dialog box to prompt the user for connection information.</span></span> <span data-ttu-id="723f6-135">Esse método simplifica o código do aplicativo.</span><span class="sxs-lookup"><span data-stu-id="723f6-135">This method simplifies the application code.</span></span>  
  
## <a name="sqlbrowseconnect"></a><span data-ttu-id="723f6-136">SQLBrowseConnect</span><span class="sxs-lookup"><span data-stu-id="723f6-136">SQLBrowseConnect</span></span>  
 <span data-ttu-id="723f6-137">**SQLBrowseConnect**, como **SQLDriverConnect**, usa uma cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="723f6-137">**SQLBrowseConnect**, like **SQLDriverConnect**, uses a connection string.</span></span> <span data-ttu-id="723f6-138">No entanto, usando **SQLBrowseConnect**, um aplicativo pode construir uma cadeia de conexão completa iterativamente com a fonte de dados em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="723f6-138">However, by using **SQLBrowseConnect**, an application can construct a complete connection string iteratively with the data source at run time.</span></span> <span data-ttu-id="723f6-139">Isso permite que o aplicativo faça duas tarefas:</span><span class="sxs-lookup"><span data-stu-id="723f6-139">This allows the application to do two things:</span></span>  
  
-   <span data-ttu-id="723f6-140">Crie as próprias caixas de diálogo para solicitar essas informações, assim mantendo o controle da interface do usuário.</span><span class="sxs-lookup"><span data-stu-id="723f6-140">Build its own dialog boxes to prompt for this information, thereby retaining control over its user interface.</span></span>  
  
-   <span data-ttu-id="723f6-141">Procure no sistema por fontes de dados que possam ser usadas por um driver específico, possivelmente em várias etapas.</span><span class="sxs-lookup"><span data-stu-id="723f6-141">Browse the system for data sources that can be used by a particular driver, possibly in several steps.</span></span>  
  
     <span data-ttu-id="723f6-142">Por exemplo, primeiro o usuário pode procurar servidores na rede e, depois de escolher um, procurar no servidor pelos bancos de dados acessíveis pelo driver.</span><span class="sxs-lookup"><span data-stu-id="723f6-142">For example, the user might first browse the network for servers and, after choosing a server, browse the server for databases accessible by the driver.</span></span>  
  
 <span data-ttu-id="723f6-143">Quando o **SQLBrowseConnect** conclui uma conexão bem-sucedida, ele retorna uma cadeia de conexão que pode ser usada em chamadas subsequentes para **SQLDriverConnect**.</span><span class="sxs-lookup"><span data-stu-id="723f6-143">When **SQLBrowseConnect** completes a successful connection, it returns a connection string that can be used on subsequent calls to **SQLDriverConnect**.</span></span>  
  
 <span data-ttu-id="723f6-144">O [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client sempre retorna SQL_SUCCESS_WITH_INFO em um **SQLConnect**, **SQLDriverConnect**ou **SQLBrowseConnect**bem-sucedido.</span><span class="sxs-lookup"><span data-stu-id="723f6-144">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver always returns SQL_SUCCESS_WITH_INFO on a successful **SQLConnect**, **SQLDriverConnect**, or **SQLBrowseConnect**.</span></span> <span data-ttu-id="723f6-145">Quando um aplicativo ODBC chama **SQLGetDiagRec** depois de obter SQL_SUCCESS_WITH_INFO, ele pode receber as seguintes mensagens:</span><span class="sxs-lookup"><span data-stu-id="723f6-145">When an ODBC application calls **SQLGetDiagRec** after getting SQL_SUCCESS_WITH_INFO, it can receive the following messages:</span></span>  
  
 <span data-ttu-id="723f6-146">5701</span><span class="sxs-lookup"><span data-stu-id="723f6-146">5701</span></span>  
 <span data-ttu-id="723f6-147">Indica que o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] colocou o contexto do usuário no banco de dados padrão definido na fonte de dados, ou no banco de dados padrão definido para o ID de logon usado na conexão se a fonte de dados não tinha um banco de dados padrão.</span><span class="sxs-lookup"><span data-stu-id="723f6-147">Indicates that [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] put the user's context into the default database defined in the data source, or into the default database defined for the login ID used in the connection if the data source did not have a default database.</span></span>  
  
 <span data-ttu-id="723f6-148">5703</span><span class="sxs-lookup"><span data-stu-id="723f6-148">5703</span></span>  
 <span data-ttu-id="723f6-149">Indica o idioma usado no servidor.</span><span class="sxs-lookup"><span data-stu-id="723f6-149">Indicates the language being used on the server.</span></span>  
  
 <span data-ttu-id="723f6-150">O exemplo a seguir mostra a mensagem retornada em uma conexão bem-sucedida pelo administrador do sistema:</span><span class="sxs-lookup"><span data-stu-id="723f6-150">The following example shows the message returned on a successful connection by the system administrator:</span></span>  
  
```  
szSqlState = "01000", *pfNativeError = 5701,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
       Changed database context to 'pubs'."  
szSqlState = "01000", *pfNativeError = 5703,  
szErrorMsg="[Microsoft][SQL Server Native Client][SQL Server]  
       Changed language setting to 'us_english'."  
```  
  
 <span data-ttu-id="723f6-151">Você pode ignorar as mensagens 5701 e 5703; elas são meramente informativas.</span><span class="sxs-lookup"><span data-stu-id="723f6-151">You can ignore messages 5701 and 5703; they are only informational.</span></span> <span data-ttu-id="723f6-152">Entretanto, você não deve ignorar um código de retorno de SQL_SUCCESS_WITH_INFO porque podem ser retornadas mensagens diferentes de 5701 ou 5703.</span><span class="sxs-lookup"><span data-stu-id="723f6-152">You should not, however, ignore a SQL_SUCCESS_WITH_INFO return code because messages other than 5701 or 5703 may be returned.</span></span> <span data-ttu-id="723f6-153">Por exemplo, se um driver se conectar a um servidor que executa uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com procedimentos armazenados de catálogo desatualizados, um dos erros retornados por meio de **SQLGetDiagRec** após um SQL_SUCCESS_WITH_INFO é:</span><span class="sxs-lookup"><span data-stu-id="723f6-153">For example, if a driver connects to a server running an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with outdated catalog stored procedures, one of the errors returned through **SQLGetDiagRec** after a SQL_SUCCESS_WITH_INFO is:</span></span>  
  
```  
SqlState:   01000  
pfNative:   0  
szErrorMsg: "[Microsoft][SQL Server Native Client]The ODBC  
            catalog stored procedures installed on server  
            my65server are version 06.50.0193; version 07.00.0205  
            or later is required to ensure proper operation.  
            Please contact your system administrator."  
```  
  
 <span data-ttu-id="723f6-154">A função de tratamento de erros de um aplicativo para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] conexões deve chamar **SQLGetDiagRec** até que ela retorne SQL_NO_DATA.</span><span class="sxs-lookup"><span data-stu-id="723f6-154">The error handling function of an application for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connections should call **SQLGetDiagRec** until it returns SQL_NO_DATA.</span></span> <span data-ttu-id="723f6-155">Em seguida, ele deve agir em qualquer mensagem além daquelas com um código *pfNative* de 5701 ou 5703.</span><span class="sxs-lookup"><span data-stu-id="723f6-155">It should then act on any messages other than the ones with a *pfNative* code of 5701 or 5703.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="723f6-156">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="723f6-156">See Also</span></span>  
 [<span data-ttu-id="723f6-157">Comunicando-se com SQL Server &#40;ODBC&#41;</span><span class="sxs-lookup"><span data-stu-id="723f6-157">Communicating with SQL Server &#40;ODBC&#41;</span></span>](communicating-with-sql-server-odbc.md)  
  
  
