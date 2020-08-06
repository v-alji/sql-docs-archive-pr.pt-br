---
title: SQLDriverConnect | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLDriverConnect function
ms.assetid: a1e38e2c-3a97-42d1-9c45-a0ca3282ffd1
author: rothja
ms.author: jroth
ms.openlocfilehash: 40691dfb381883b59155607fb56f4933820e3e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683524"
---
# <a name="sqldriverconnect"></a><span data-ttu-id="9efc5-102">SQLDriverConnect</span><span class="sxs-lookup"><span data-stu-id="9efc5-102">SQLDriverConnect</span></span>
  <span data-ttu-id="9efc5-103">O driver ODBC para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client define atributos de conexão que substituem ou aprimoram palavras-chave de cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="9efc5-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver defines connection attributes that either replace or enhance connection-string keywords.</span></span> <span data-ttu-id="9efc5-104">Várias palavras-chave de cadeia de conexão têm valores padrão especificados pelo driver ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client.</span><span class="sxs-lookup"><span data-stu-id="9efc5-104">Several connection-string keywords have default values specified by the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver.</span></span>  
  
 <span data-ttu-id="9efc5-105">Para obter uma lista das palavras-chave disponíveis no [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client, consulte [usando palavras-chave da cadeia de conexão com o SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="9efc5-105">For a list of the keywords available in the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="9efc5-106">Para obter mais informações sobre [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] atributos de conexão e comportamentos padrão de driver, consulte [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="9efc5-106">For more information about [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] connection attributes and driver default behaviors, see [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
 <span data-ttu-id="9efc5-107">Para obter uma discussão sobre palavras-chave da cadeia de conexão que são válidas para o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, consulte [usando palavras-chave da cadeia de conexão com SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="9efc5-107">For a discussion of connection string keywords that are valid for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, see [Using Connection String Keywords with SQL Server Native Client](../native-client/applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="9efc5-108">Quando o `SQLDriverConnect` valor do parâmetro *DriverCompletion* é SQL_DRIVER_PROMPT, SQL_DRIVER_COMPLETE ou SQL_DRIVER_COMPLETE_REQUIRED, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] driver ODBC do Native Client recupera os valores da palavra-chave da caixa de diálogo exibida.</span><span class="sxs-lookup"><span data-stu-id="9efc5-108">When the `SQLDriverConnect`*DriverCompletion* parameter value is SQL_DRIVER_PROMPT, SQL_DRIVER_COMPLETE, or SQL_DRIVER_COMPLETE_REQUIRED, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver retrieves keyword values from the displayed dialog box.</span></span> <span data-ttu-id="9efc5-109">Se o valor de palavra-chave for transmitido na cadeia de caracteres da conexão e o usuário não alterar o valor para a palavra-chave na caixa de diálogo, o driver ODBC [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client usará o valor da cadeia de caracteres da conexão.</span><span class="sxs-lookup"><span data-stu-id="9efc5-109">If the keyword value is passed in the connection string and the user does not alter the value for the keyword in the dialog box, the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver uses the value from the connection string.</span></span> <span data-ttu-id="9efc5-110">Se o valor não for definido na cadeia de caracteres da conexão e o usuário não fizer nenhuma atribuição na caixa de diálogo, o driver usará o padrão.</span><span class="sxs-lookup"><span data-stu-id="9efc5-110">If the value is not set in the connection string and the user makes no assignment in the dialog box, the driver uses the default.</span></span>  
  
 <span data-ttu-id="9efc5-111">`SQLDriverConnect`deve receber um *WindowHandle* válido quando qualquer valor de *DriverCompletion* exigir (ou pode exigir) a exibição da caixa de diálogo de conexão do driver.</span><span class="sxs-lookup"><span data-stu-id="9efc5-111">`SQLDriverConnect` must be given a valid *WindowHandle* when any *DriverCompletion* value requires (or could require) the display of the driver's connection dialog box.</span></span> <span data-ttu-id="9efc5-112">Um identificador inválido retorna SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="9efc5-112">An invalid handle returns SQL_ERROR.</span></span>  
  
 <span data-ttu-id="9efc5-113">Especifique as palavras-chave DRIVER ou DSN.</span><span class="sxs-lookup"><span data-stu-id="9efc5-113">Specify either the DRIVER or DSN keywords.</span></span> <span data-ttu-id="9efc5-114">O ODBC declara que um driver usa a que está mais à esquerda dessas duas palavras-chave e ignora a outra se ambas estão especificadas.</span><span class="sxs-lookup"><span data-stu-id="9efc5-114">ODBC states that a driver uses the leftmost of these two keywords and ignores the other if both are specified.</span></span> <span data-ttu-id="9efc5-115">Se o DRIVER for especificado, ou for o mais à esquerda dos dois, e o `SQLDriverConnect` valor do parâmetro *DriverCompletion* for SQL_DRIVER_NOPROMPT, a palavra-chave do servidor e um valor apropriado serão necessários.</span><span class="sxs-lookup"><span data-stu-id="9efc5-115">If DRIVER is specified, or is the leftmost of the two, and the `SQLDriverConnect`*DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT, the SERVER keyword and an appropriate value are required.</span></span>  
  
 <span data-ttu-id="9efc5-116">Quando SQL_DRIVER_NOPROMPT é especificado, as palavras-chave de autenticação de usuário devem estar presentes com valores.</span><span class="sxs-lookup"><span data-stu-id="9efc5-116">When SQL_DRIVER_NOPROMPT is specified, user authentication keywords must be present with values.</span></span> <span data-ttu-id="9efc5-117">O driver assegura que a cadeia de caracteres "Trusted_Connection=yes" ou as palavras-chave UID e PWD estão presentes.</span><span class="sxs-lookup"><span data-stu-id="9efc5-117">The driver ensures that either the string "Trusted_Connection=yes" or both the UID and PWD keywords are present.</span></span>  
  
 <span data-ttu-id="9efc5-118">Se o valor do parâmetro *DriverCompletion* for SQL_DRIVER_NOPROMPT ou SQL_DRIVER_COMPLETE_REQUIRED e o idioma ou o banco de dados vier da cadeia de conexão e for inválido, o `SQLDriverConnect` retornará SQL_ERROR.</span><span class="sxs-lookup"><span data-stu-id="9efc5-118">If the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT or SQL_DRIVER_COMPLETE_REQUIRED and the language or database comes from the connection string and either is invalid, `SQLDriverConnect` returns SQL_ERROR.</span></span>  
  
 <span data-ttu-id="9efc5-119">Se o valor do parâmetro *DriverCompletion* for SQL_DRIVER_NOPROMPT ou SQL_DRIVER_COMPLETE_REQUIRED e o idioma ou o banco de dados vierem das definições de fonte de dado ODBC e forem inválidos, o `SQLDriverConnect` usará o idioma padrão ou o Database para a ID de usuário especificada e retornará SQL_SUCCESS_WITH_INFO.</span><span class="sxs-lookup"><span data-stu-id="9efc5-119">If the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT or SQL_DRIVER_COMPLETE_REQUIRED and the language or database comes from the ODBC data source definitions and either is invalid, `SQLDriverConnect` uses the default language or database for the specified user ID and returns SQL_SUCCESS_WITH_INFO.</span></span>  
  
 <span data-ttu-id="9efc5-120">Se o valor do parâmetro *DriverCompletion* for SQL_DRIVER_COMPLETE ou SQL_DRIVER_PROMPT e se o idioma ou o banco de dados for inválido, `SQLDriverConnect` o exibirá novamente a caixa de diálogo.</span><span class="sxs-lookup"><span data-stu-id="9efc5-120">If the *DriverCompletion* parameter value is SQL_DRIVER_COMPLETE or SQL_DRIVER_PROMPT and if the language or database is invalid, `SQLDriverConnect` redisplays the dialog box.</span></span>  
  
## <a name="sqldriverconnect-support-for-high-availability-disaster-recovery"></a><span data-ttu-id="9efc5-121">Suporte de SQLDriverConnect à alta disponibilidade e recuperação de desastre</span><span class="sxs-lookup"><span data-stu-id="9efc5-121">SQLDriverConnect Support for High Availability, Disaster Recovery</span></span>  
 <span data-ttu-id="9efc5-122">Para obter mais informações sobre como usar `SQLDriverConnect` o para se conectar a um [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] cluster, consulte [suporte a SQL Server Native Client para alta disponibilidade e recuperação de desastre](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span><span class="sxs-lookup"><span data-stu-id="9efc5-122">For more information about using `SQLDriverConnect` to connect to a [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] cluster, see [SQL Server Native Client Support for High Availability, Disaster Recovery](../native-client/features/sql-server-native-client-support-for-high-availability-disaster-recovery.md).</span></span>  
  
## <a name="sqldriverconnect-support-for-service-principal-names-spns"></a><span data-ttu-id="9efc5-123">Suporte de SQLDriverConnect a SPNs (nomes de entidade de serviço)</span><span class="sxs-lookup"><span data-stu-id="9efc5-123">SQLDriverConnect Support for Service Principal Names (SPNs)</span></span>  
 <span data-ttu-id="9efc5-124">O SQLDDriverConnect usará a caixa de diálogo logon do ODBC boxwhen solicitação está habilitada.</span><span class="sxs-lookup"><span data-stu-id="9efc5-124">SQLDDriverConnect will use the ODBC Login dialog boxwhen prompting is enabled.</span></span> <span data-ttu-id="9efc5-125">Isto permite que os SPNs sejam inseridos no servidor principal e no seu parceiro de failover.</span><span class="sxs-lookup"><span data-stu-id="9efc5-125">This allows SPNs to be entered for both the principal server and its failover partner.</span></span>  
  
 <span data-ttu-id="9efc5-126">O SQLDriverConnect aceitará as novas palavras-chave da cadeia de conexão `ServerSPN` e `FailoverPartnerSPN` reconhecerá os novos atributos de conexão SQL_COPT_SS_SERVER_SPN e SQL_COPT_SS_FAILOVER_PARTNER_SPN.</span><span class="sxs-lookup"><span data-stu-id="9efc5-126">SQLDriverConnect will accept the new connection string keywords `ServerSPN` and `FailoverPartnerSPN`, and will recognize the new connection attributes SQL_COPT_SS_SERVER_SPN and SQL_COPT_SS_FAILOVER_PARTNER_SPN.</span></span>  
  
 <span data-ttu-id="9efc5-127">Quando um valor de atributo de conexão é especificado mais de uma vez, um valor definido programaticamente tem precedência sobre o valor em um DSN e um valor em uma cadeia de caracteres de conexão.</span><span class="sxs-lookup"><span data-stu-id="9efc5-127">When a connection attribute value is specified more than once, a value that is set programmatically takes precedence over the value in a DSN and a value in a connection string.</span></span> <span data-ttu-id="9efc5-128">Um valor em um DSN tem precedência sobre um valor em uma cadeia de caracteres de conexão.</span><span class="sxs-lookup"><span data-stu-id="9efc5-128">A value in a DSN takes precedence over a value in a connection string.</span></span>  
  
 <span data-ttu-id="9efc5-129">Quando uma conexão é aberta, o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client define SQL_COPT_SS_MUTUALLY_AUTHENTICATED e SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD como o método de autenticação usado para abrir a conexão.</span><span class="sxs-lookup"><span data-stu-id="9efc5-129">When a connection is opened, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client sets SQL_COPT_SS_MUTUALLY_AUTHENTICATED and SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD to the authentication method used to open the connection.</span></span>  
  
 <span data-ttu-id="9efc5-130">Para obter mais informações sobre SPNs, consulte [nomes de entidade de serviço &#40;SPNs&#41; em conexões de cliente &#40;&#41;ODBC ](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="9efc5-130">For more information about SPNs, see [Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span></span>  
  
## <a name="examples"></a><span data-ttu-id="9efc5-131">Exemplos</span><span class="sxs-lookup"><span data-stu-id="9efc5-131">Examples</span></span>  
 <span data-ttu-id="9efc5-132">A chamada a seguir ilustra a quantidade mínima de dados necessários para `SQLDriverConnect` :</span><span class="sxs-lookup"><span data-stu-id="9efc5-132">The following call illustrates the least amount of data required for `SQLDriverConnect`:</span></span>  
  
```  
SQLDriverConnect(hdbc, hwnd,  
    (SQLTCHAR*) TEXT("DRIVER={SQL Server Native Client 10};"), SQL_NTS, szOutConn,  
    MAX_CONN_OUT, &cbOutConn, SQL_DRIVER_COMPLETE);  
```  
  
 <span data-ttu-id="9efc5-133">As seguintes cadeias de conexão ilustram os dados mínimos necessários quando o valor do parâmetro *DriverCompletion* é SQL_DRIVER_NOPROMPT:</span><span class="sxs-lookup"><span data-stu-id="9efc5-133">The following connection strings illustrate minimum required data when the *DriverCompletion* parameter value is SQL_DRIVER_NOPROMPT:</span></span>  
  
```  
"DSN=Human Resources;Trusted_Connection=yes"  
  
"FILEDSN=HR_FDSN;Trusted_Connection=yes"  
  
"DRIVER={SQL Server Native Client 10};SERVER=(local);Trusted_Connection=yes"  
```  
  
## <a name="see-also"></a><span data-ttu-id="9efc5-134">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9efc5-134">See Also</span></span>  
 <span data-ttu-id="9efc5-135">[Função SQLDriverConnect](https://go.microsoft.com/fwlink/?LinkId=59340) </span><span class="sxs-lookup"><span data-stu-id="9efc5-135">[SQLDriverConnect Function](https://go.microsoft.com/fwlink/?LinkId=59340) </span></span>  
 <span data-ttu-id="9efc5-136">[Detalhes de implementação da API ODBC](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="9efc5-136">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 <span data-ttu-id="9efc5-137">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9efc5-137">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span></span>  
 <span data-ttu-id="9efc5-138">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="9efc5-138">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span></span>  
 [<span data-ttu-id="9efc5-139">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9efc5-139">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-ansi-warnings-transact-sql)  
  
  
