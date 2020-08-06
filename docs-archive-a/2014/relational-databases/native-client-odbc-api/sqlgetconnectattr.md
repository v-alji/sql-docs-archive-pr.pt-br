---
title: SQLGetConnectAttr | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
topic_type:
- apiref
helpviewer_keywords:
- SQLGetConnectAttr function
ms.assetid: 26e4e69a-44fd-45e3-b47a-ae39184f041b
author: rothja
ms.author: jroth
ms.openlocfilehash: f82a0fb71103e811b36280f9722c160791023e44
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87568553"
---
# <a name="sqlgetconnectattr"></a><span data-ttu-id="a1d15-102">SQLGetConnectAttr</span><span class="sxs-lookup"><span data-stu-id="a1d15-102">SQLGetConnectAttr</span></span>
  <span data-ttu-id="a1d15-103">O driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client define atributos de conexão específicos de driver.</span><span class="sxs-lookup"><span data-stu-id="a1d15-103">The [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver defines driver-specific connection attributes.</span></span> <span data-ttu-id="a1d15-104">Alguns dos atributos estão disponíveis para `SQLGetConnectAttr` o, e a função é usada para relatar suas configurações atuais.</span><span class="sxs-lookup"><span data-stu-id="a1d15-104">Some of the attributes are available to `SQLGetConnectAttr`, and the function is used to report their current settings.</span></span> <span data-ttu-id="a1d15-105">Os valores informados em relação a esses atributos não são garantidos até que uma conexão seja estabelecida ou o atributo seja definido usando [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="a1d15-105">The values reported for these attributes are not guaranteed until after a connection has been made or the attribute has been set using [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
 <span data-ttu-id="a1d15-106">Este tópico lista os atributos somente leitura.</span><span class="sxs-lookup"><span data-stu-id="a1d15-106">This topic lists the read only attributes.</span></span> <span data-ttu-id="a1d15-107">Para obter informações sobre os outros atributos de conexão específicos de driver ODBC do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client, consulte [SQLSetConnectAttr](sqlsetconnectattr.md).</span><span class="sxs-lookup"><span data-stu-id="a1d15-107">For information about the other [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Native Client ODBC driver-specific connection attributes, see [SQLSetConnectAttr](sqlsetconnectattr.md).</span></span>  
  
## <a name="sql_copt_ss_connection_dead"></a><span data-ttu-id="a1d15-108">SQL_COPT_SS_CONNECTION_DEAD</span><span class="sxs-lookup"><span data-stu-id="a1d15-108">SQL_COPT_SS_CONNECTION_DEAD</span></span>  
 <span data-ttu-id="a1d15-109">O atributo SQL_COPT_SS_CONNECTION_DEAD informa o estado de uma conexão com um servidor.</span><span class="sxs-lookup"><span data-stu-id="a1d15-109">The SQL_COPT_SS_CONNECTION_DEAD attribute reports the state of a connection to a server.</span></span> <span data-ttu-id="a1d15-110">O driver consulta a rede quanto ao estado atual da conexão.</span><span class="sxs-lookup"><span data-stu-id="a1d15-110">The driver queries the network for the current state of the connection.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="a1d15-111">O atributo de conexão ODBC padrão SQL_ATTR_CONNECTION_DEAD retorna o estado mais recente da conexão.</span><span class="sxs-lookup"><span data-stu-id="a1d15-111">The standard ODBC connection attribute SQL_ATTR_CONNECTION_DEAD returns the most recent state of the connection.</span></span> <span data-ttu-id="a1d15-112">Esse talvez não seja o estado da conexão atual.</span><span class="sxs-lookup"><span data-stu-id="a1d15-112">This might not be the current connection state.</span></span>  
  
|<span data-ttu-id="a1d15-113">Valor</span><span class="sxs-lookup"><span data-stu-id="a1d15-113">Value</span></span>|<span data-ttu-id="a1d15-114">Descrição</span><span class="sxs-lookup"><span data-stu-id="a1d15-114">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a1d15-115">SQL_CD_TRUE</span><span class="sxs-lookup"><span data-stu-id="a1d15-115">SQL_CD_TRUE</span></span>|<span data-ttu-id="a1d15-116">A conexão com o servidor foi perdida.</span><span class="sxs-lookup"><span data-stu-id="a1d15-116">The connection to the server has been lost.</span></span>|  
|<span data-ttu-id="a1d15-117">SQL_CD_FALSE</span><span class="sxs-lookup"><span data-stu-id="a1d15-117">SQL_CD_FALSE</span></span>|<span data-ttu-id="a1d15-118">A conexão está aberta e disponível ao processamento de instrução.</span><span class="sxs-lookup"><span data-stu-id="a1d15-118">The connection is open and available for statement processing.</span></span>|  
  
## <a name="sql_copt_ss_client_connection_id"></a><span data-ttu-id="a1d15-119">SQL_COPT_SS_CLIENT_CONNECTION_ID</span><span class="sxs-lookup"><span data-stu-id="a1d15-119">SQL_COPT_SS_CLIENT_CONNECTION_ID</span></span>  
 <span data-ttu-id="a1d15-120">O atributo SQL_COPT_SS_CLIENT_CONNECTION_ID recupera a ID de conexão de cliente, que pode ser usada para localizar:</span><span class="sxs-lookup"><span data-stu-id="a1d15-120">The SQL_COPT_SS_CLIENT_CONNECTION_ID attribute retrieves the client connection ID, which can then be used to locate:</span></span>  
  
-   <span data-ttu-id="a1d15-121">Informações de diagnóstico no log de XEvents, quando habilitado.</span><span class="sxs-lookup"><span data-stu-id="a1d15-121">Diagnostic information in the XEvents log, when enabled.</span></span>  
  
-   <span data-ttu-id="a1d15-122">As informações de erro de conexão no buffer de anéis de conexão.</span><span class="sxs-lookup"><span data-stu-id="a1d15-122">Connection error information in the connection ring buffer.</span></span>  
  
-   <span data-ttu-id="a1d15-123">As informações de diagnóstico nos logs de rastreamento de acesso a dados, quando habilitado.</span><span class="sxs-lookup"><span data-stu-id="a1d15-123">Diagnostic information in the data access tracing logs, when enabled.</span></span>  
  
 <span data-ttu-id="a1d15-124">Para obter mais informações, consulte [Acessando informações de diagnóstico no log de eventos estendidos](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span><span class="sxs-lookup"><span data-stu-id="a1d15-124">For more information, see [Accessing Diagnostic Information in the Extended Events Log](../native-client/features/accessing-diagnostic-information-in-the-extended-events-log.md).</span></span>  
  
|<span data-ttu-id="a1d15-125">Valor</span><span class="sxs-lookup"><span data-stu-id="a1d15-125">Value</span></span>|<span data-ttu-id="a1d15-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="a1d15-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a1d15-127">SQL_ERROR</span><span class="sxs-lookup"><span data-stu-id="a1d15-127">SQL_ERROR</span></span>|<span data-ttu-id="a1d15-128">Falha na conexão.</span><span class="sxs-lookup"><span data-stu-id="a1d15-128">The connection failed.</span></span>|  
|<span data-ttu-id="a1d15-129">SQL_SUCCESS</span><span class="sxs-lookup"><span data-stu-id="a1d15-129">SQL_SUCCESS</span></span>|<span data-ttu-id="a1d15-130">A conexão foi bem-sucedida.</span><span class="sxs-lookup"><span data-stu-id="a1d15-130">The connection succeeded.</span></span> <span data-ttu-id="a1d15-131">A ID de conexão de cliente será localizada no buffer de saída.</span><span class="sxs-lookup"><span data-stu-id="a1d15-131">The client connection ID will be found in the output buffer.</span></span>|  
  
## <a name="sql_copt_ss_perf_data"></a><span data-ttu-id="a1d15-132">SQL_COPT_SS_PERF_DATA</span><span class="sxs-lookup"><span data-stu-id="a1d15-132">SQL_COPT_SS_PERF_DATA</span></span>  
 <span data-ttu-id="a1d15-133">O atributo SQL_COPT_SS_PERF_DATA retorna um ponteiro para uma estrutura SQLPERF que contém as estatísticas de desempenho do driver atuais.</span><span class="sxs-lookup"><span data-stu-id="a1d15-133">The SQL_COPT_SS_PERF_DATA attribute returns a pointer to a SQLPERF structure containing the current driver performance statistics.</span></span> <span data-ttu-id="a1d15-134">`SQLGetConnectAttr`retornará NULL se o log de desempenho não estiver habilitado.</span><span class="sxs-lookup"><span data-stu-id="a1d15-134">`SQLGetConnectAttr` will return NULL if performance logging is not enabled.</span></span> <span data-ttu-id="a1d15-135">As estatísticas na estrutura SQLPERF não são atualizadas dinamicamente pelo driver.</span><span class="sxs-lookup"><span data-stu-id="a1d15-135">The statistics in the SQLPERF structure are not dynamically updated by the driver.</span></span> <span data-ttu-id="a1d15-136">Chame `SQLGetConnectAttr` cada vez que as estatísticas de desempenho precisam ser atualizadas.</span><span class="sxs-lookup"><span data-stu-id="a1d15-136">Call `SQLGetConnectAttr` each time the performance statistics need to be refreshed.</span></span>  
  
|<span data-ttu-id="a1d15-137">Valor</span><span class="sxs-lookup"><span data-stu-id="a1d15-137">Value</span></span>|<span data-ttu-id="a1d15-138">Descrição</span><span class="sxs-lookup"><span data-stu-id="a1d15-138">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a1d15-139">NULO</span><span class="sxs-lookup"><span data-stu-id="a1d15-139">NULL</span></span>|<span data-ttu-id="a1d15-140">O registro em log de desempenho não está habilitado.</span><span class="sxs-lookup"><span data-stu-id="a1d15-140">Performance logging is not enabled.</span></span>|  
|<span data-ttu-id="a1d15-141">Qualquer outro valor</span><span class="sxs-lookup"><span data-stu-id="a1d15-141">Any other value</span></span>|<span data-ttu-id="a1d15-142">Um ponteiro para uma estrutura SQLPERF.</span><span class="sxs-lookup"><span data-stu-id="a1d15-142">A pointer to a SQLPERF structure.</span></span>|  
  
## <a name="sql_copt_ss_perf_query"></a><span data-ttu-id="a1d15-143">SQL_COPT_SS_PERF_QUERY</span><span class="sxs-lookup"><span data-stu-id="a1d15-143">SQL_COPT_SS_PERF_QUERY</span></span>  
 <span data-ttu-id="a1d15-144">O atributo SQL_COPT_SS_PERF_QUERY retorna TRUE caso o registro em log das consultas demoradas em execução esteja habilitado.</span><span class="sxs-lookup"><span data-stu-id="a1d15-144">The SQL_COPT_SS_PERF_QUERY attribute returns TRUE if logging of long running queries is enabled.</span></span> <span data-ttu-id="a1d15-145">A solicitação retorna FALSE caso registro em log da consulta não esteja ativo.</span><span class="sxs-lookup"><span data-stu-id="a1d15-145">The request returns FALSE if query logging is not active.</span></span>  
  
## <a name="sql_copt_ss_user_data"></a><span data-ttu-id="a1d15-146">SQL_COPT_SS_USER_DATA</span><span class="sxs-lookup"><span data-stu-id="a1d15-146">SQL_COPT_SS_USER_DATA</span></span>  
 <span data-ttu-id="a1d15-147">O atributo SQL_COPT_SS_USER_DATA recupera o ponteiro dos dados de usuário.</span><span class="sxs-lookup"><span data-stu-id="a1d15-147">The SQL_COPT_SS_USER_DATA attribute retrieves the user-data pointer.</span></span> <span data-ttu-id="a1d15-148">Os dados de usuário são armazenados na memória do cliente e registrados por conexão.</span><span class="sxs-lookup"><span data-stu-id="a1d15-148">User data is stored in client-owned memory and recorded per connection.</span></span> <span data-ttu-id="a1d15-149">Caso o ponteiro de dados do usuário não seja definido, SQL_UD_NOTSET, um ponteiro NULL, é retornado.</span><span class="sxs-lookup"><span data-stu-id="a1d15-149">If the user-data pointer has not been set, SQL_UD_NOTSET, a NULL pointer, is returned.</span></span>  
  
|<span data-ttu-id="a1d15-150">Valor</span><span class="sxs-lookup"><span data-stu-id="a1d15-150">Value</span></span>|<span data-ttu-id="a1d15-151">Descrição</span><span class="sxs-lookup"><span data-stu-id="a1d15-151">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="a1d15-152">SQL_UD_NOTSET</span><span class="sxs-lookup"><span data-stu-id="a1d15-152">SQL_UD_NOTSET</span></span>|<span data-ttu-id="a1d15-153">Nenhum ponteiro de dados do usuário é definido.</span><span class="sxs-lookup"><span data-stu-id="a1d15-153">No user-data pointer is set.</span></span>|  
|<span data-ttu-id="a1d15-154">Qualquer outro valor</span><span class="sxs-lookup"><span data-stu-id="a1d15-154">Any other value</span></span>|<span data-ttu-id="a1d15-155">Um ponteiro para os dados do usuário.</span><span class="sxs-lookup"><span data-stu-id="a1d15-155">A pointer to the user data.</span></span>|  
  
## <a name="sqlgetconnectattr-support-for-service-principal-names-spns"></a><span data-ttu-id="a1d15-156">Suporte do SQLGetConnectAttr a SPNs (Nomes da Entidade de Serviço)</span><span class="sxs-lookup"><span data-stu-id="a1d15-156">SQLGetConnectAttr Support for Service Principal Names (SPNs)</span></span>  
 <span data-ttu-id="a1d15-157">SQLGetConnectAttr pode ser usado para consultar o valor dos novos atributos de conexão SQL_COPT_SS_SERVER_SPN, SQL_COPT_SS_FAILOVER_PARTNER_SPN, SQL_COPT_SS_MUTUALLY_AUTHENTICATED e SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD.</span><span class="sxs-lookup"><span data-stu-id="a1d15-157">SQLGetConnectAttr can be used to query the value of the new connection attributes SQL_COPT_SS_SERVER_SPN, SQL_COPT_SS_FAILOVER_PARTNER_SPN, SQL_COPT_SS_MUTUALLY_AUTHENTICATED, and SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD.</span></span> <span data-ttu-id="a1d15-158">(SQLGetConnectOption também pode ser usado para consultar esses valores.)</span><span class="sxs-lookup"><span data-stu-id="a1d15-158">(SQLGetConnectOption can also be used to query these values.)</span></span>  
  
 <span data-ttu-id="a1d15-159">SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD só está disponível para conexões abertas que usam a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="a1d15-159">SQL_COPT_SS_INTEGRATED_AUTHENTICATION_METHOD is only available for open connections that use Windows Authentication.</span></span>  
  
 <span data-ttu-id="a1d15-160">Caso SQL_COPT_SS_SERVER_SPN ou SQL_COPT_SS_FAILOVER_PARTNER não tenha sido definido, será retornado o valor padrão (uma cadeia de caracteres vazia).</span><span class="sxs-lookup"><span data-stu-id="a1d15-160">If SQL_COPT_SS_SERVER_SPN or SQL_COPT_SS_FAILOVER_PARTNER has not been set, the default value (an empty string) is returned.</span></span>  
  
 <span data-ttu-id="a1d15-161">Para obter mais informações sobre SPNs, consulte [nomes de entidade de serviço &#40;SPNs&#41; em conexões de cliente &#40;&#41;ODBC ](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span><span class="sxs-lookup"><span data-stu-id="a1d15-161">For more information about SPNs, see [Service Principal Names &#40;SPNs&#41; in Client Connections &#40;ODBC&#41;](../native-client/odbc/service-principal-names-spns-in-client-connections-odbc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="a1d15-162">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="a1d15-162">See Also</span></span>  
 <span data-ttu-id="a1d15-163">[Função SQLGetConnectAttr](https://go.microsoft.com/fwlink/?LinkId=59347) </span><span class="sxs-lookup"><span data-stu-id="a1d15-163">[SQLGetConnectAttr Function](https://go.microsoft.com/fwlink/?LinkId=59347) </span></span>  
 <span data-ttu-id="a1d15-164">[Detalhes de implementação da API ODBC](odbc-api-implementation-details.md) </span><span class="sxs-lookup"><span data-stu-id="a1d15-164">[ODBC API Implementation Details](odbc-api-implementation-details.md) </span></span>  
 <span data-ttu-id="a1d15-165">[DEFINIR QUOTED_IDENTIFIER &#40;&#41;Transact-SQL](/sql/t-sql/statements/set-quoted-identifier-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a1d15-165">[SET QUOTED_IDENTIFIER &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-quoted-identifier-transact-sql) </span></span>  
 <span data-ttu-id="a1d15-166">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a1d15-166">[SET ANSI_NULLS &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-nulls-transact-sql) </span></span>  
 <span data-ttu-id="a1d15-167">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="a1d15-167">[SET ANSI_PADDING &#40;Transact-SQL&#41;](/sql/t-sql/statements/set-ansi-padding-transact-sql) </span></span>  
 [<span data-ttu-id="a1d15-168">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="a1d15-168">SET ANSI_WARNINGS &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/set-ansi-warnings-transact-sql)  
  
  
