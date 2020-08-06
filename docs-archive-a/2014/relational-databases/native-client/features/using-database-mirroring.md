---
title: Usar espelhamento de banco de dados | Microsoft Docs
ms.custom: ''
ms.date: 03/08/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: native-client
ms.topic: reference
helpviewer_keywords:
- database mirroring [SQL Server], interoperability
- SQL Server Native Client, database mirroring
- data access [SQL Server Native Client], database mirroring
- database mirroring [SQL Server], connecting clients to
- SQLNCLI, database mirroring
- SQL Server Native Client ODBC driver, database mirroring
- SQL Server Native Client OLE DB provider, database mirroring
ms.assetid: 71b15712-7972-4465-9274-e0ddc271eedc
author: rothja
ms.author: jroth
ms.openlocfilehash: 389036322137abcc9a40e36c697e8d45e39a7de5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570660"
---
# <a name="using-database-mirroring"></a><span data-ttu-id="9de63-102">Usando o espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="9de63-102">Using Database Mirroring</span></span>
    
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="9de63-103">Em vez disso, use [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9de63-103">Use [!INCLUDE[ssHADR](../../../includes/sshadr-md.md)] instead.</span></span>  
  
 <span data-ttu-id="9de63-104">O espelhamento de banco de dados, apresentado no [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], é uma solução que visa aumentar a disponibilidade do banco de dados e a redundância de dados.</span><span class="sxs-lookup"><span data-stu-id="9de63-104">Database mirroring, introduced in [!INCLUDE[ssVersion2005](../../../includes/ssversion2005-md.md)], is a solution for increasing database availability and data redundancy.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="9de63-105">O Native Client fornece suporte implícito para espelhamento de banco de dados, de modo que o desenvolvedor não precisa escrever nenhum código ou executar qualquer outra ação depois de ter sido configurado para o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9de63-105">Native Client provides implicit support for database mirroring, so the developer does not need to write any code or take any other action once it has been configured for the database.</span></span>  
  
 <span data-ttu-id="9de63-106">O espelhamento de banco de dados, que é implementado para cada banco de dados, mantém uma cópia de um banco de dados de produção do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] em um servidor em espera.</span><span class="sxs-lookup"><span data-stu-id="9de63-106">Database mirroring, which is implemented on a per-database basis, keeps a copy of a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] production database on a standby server.</span></span> <span data-ttu-id="9de63-107">Esse servidor é um servidor em espera ativa ou passiva, dependendo da configuração e do estado da sessão de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9de63-107">This server is either a hot or warm standby server, depending on the configuration and state of the database mirroring session.</span></span> <span data-ttu-id="9de63-108">Um servidor em espera ativa dá suporte ao failover rápido sem perda de transações confirmadas, e um servidor em espera passiva dá suporte ao serviço de imposição (com possível perda de dados).</span><span class="sxs-lookup"><span data-stu-id="9de63-108">A hot standby server supports rapid failover with no loss of committed transactions, and a warm standby server supports forcing service (with possible data loss).</span></span>  
  
 <span data-ttu-id="9de63-109">O banco de dados de produção é chamado de *banco de dados principal*, e a cópia em espera é chamada de *banco de dados espelho*.</span><span class="sxs-lookup"><span data-stu-id="9de63-109">The production database is called the *principal database*, and the standby copy is called the *mirror database*.</span></span> <span data-ttu-id="9de63-110">O banco de dados principal e o banco de dados espelho precisam residir em instâncias separadas do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (instâncias do servidor) e, se possível, em computadores separados.</span><span class="sxs-lookup"><span data-stu-id="9de63-110">The principal database and mirror database must reside on separate instances of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] (server instances), and they should reside on separate computers if possible.</span></span>  
  
 <span data-ttu-id="9de63-111">A instância do servidor de produção, chamado *servidor principal*, se comunica com a instância do servidor em espera, chamado *servidor espelho*.</span><span class="sxs-lookup"><span data-stu-id="9de63-111">The production server instance, called the *principal server*, communicates with the standby server instance, called the *mirror server*.</span></span> <span data-ttu-id="9de63-112">Os servidores principal e espelho atuam como parceiros em uma *sessão*de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9de63-112">The principal and mirror servers act as partners within a database mirroring *session*.</span></span> <span data-ttu-id="9de63-113">Se o servidor principal falhar, o servidor espelho poderá transformar seu banco de dados no banco de dados principal por meio de um processo chamado *failover*.</span><span class="sxs-lookup"><span data-stu-id="9de63-113">If the principal server fails, the mirror server can make its database into the principal database through a process called *failover*.</span></span> <span data-ttu-id="9de63-114">Por exemplo, Parceiro_A e Parceiro_B são dois servidores parceiros, com o banco de dados principal inicialmente no Parceiro_A como servidor principal e o banco de dados espelho residindo no Parceiro_B como o servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="9de63-114">For example, Partner_A and Partner_B are two partner servers, with the principal database initially on Partner_A as principal server, and the mirror database residing on Partner_B as the mirror server.</span></span> <span data-ttu-id="9de63-115">Se o Parceiro_A ficar offline, o banco de dados no Parceiro_B pode fazer failover para se tornar o banco de dados principal atual.</span><span class="sxs-lookup"><span data-stu-id="9de63-115">If Partner_A goes offline, the database on Partner_B can fail over to become the current principal database.</span></span> <span data-ttu-id="9de63-116">Quando o Parceiro_A ingressar novamente na sessão de espelhamento, ele se tornará o servidor espelho e seu banco de dados se tornará o banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="9de63-116">When Partner_A rejoins the mirroring session, it becomes the mirror server and its database becomes the mirror database.</span></span>  
  
 <span data-ttu-id="9de63-117">Configurações alternativas de espelhamento de banco de dados oferecem diferentes níveis de desempenho e segurança de dados, e dão suporte a diversas formas de failover.</span><span class="sxs-lookup"><span data-stu-id="9de63-117">Alternative database mirroring configurations offer different levels of performance and data safety, and support different forms of failover.</span></span> <span data-ttu-id="9de63-118">Para obter mais informações, consulte [Espelhamento de banco de dados &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9de63-118">For more information, see [Database Mirroring &#40;SQL Server&#41;](../../../database-engine/database-mirroring/database-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="9de63-119">É possível usar um alias ao especificar o nome de banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="9de63-119">It is possible to use an alias when specifying the mirror database name.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9de63-120">Para obter informações sobre tentativas de conexão inicial e tentativas de reconexão com um banco de dados espelho, confira [Conectar clientes a uma sessão de espelhamento de banco de dados &#40;SQL Server&#41;](../../../database-engine/database-mirroring/connect-clients-to-a-database-mirroring-session-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9de63-120">For information about initial connection attempts and reconnection attempts to a mirrored database, see [Connect Clients to a Database Mirroring Session &#40;SQL Server&#41;](../../../database-engine/database-mirroring/connect-clients-to-a-database-mirroring-session-sql-server.md).</span></span>  
  
## <a name="programming-considerations"></a><span data-ttu-id="9de63-121">Considerações sobre programação</span><span class="sxs-lookup"><span data-stu-id="9de63-121">Programming Considerations</span></span>  
 <span data-ttu-id="9de63-122">Quando o servidor do banco de dados principal falhar, o aplicativo cliente receberá erros em resposta a chamadas API, o que indica que a conexão com o banco de dados foi interrompida.</span><span class="sxs-lookup"><span data-stu-id="9de63-122">When the principal database server fails, the client application receives errors in response to API calls, which indicate that the connection to the database has been lost.</span></span> <span data-ttu-id="9de63-123">Quando isto acontece, todas as alterações não confirmadas do banco de dados são perdidas e a transação atual é revertida.</span><span class="sxs-lookup"><span data-stu-id="9de63-123">When this happens, any uncommitted changes to the database are lost and the current transaction is rolled back.</span></span> <span data-ttu-id="9de63-124">Se isso ocorrer, o aplicativo deve fechar a conexão (ou liberar o objeto da fonte de dados) e abri-la novamente.</span><span class="sxs-lookup"><span data-stu-id="9de63-124">If this occurs, the application should close the connection (or release the data source object) and re-open it.</span></span> <span data-ttu-id="9de63-125">A conexão é redirecionada de forma transparente para o banco de dados espelho, que agora atua como servidor principal.</span><span class="sxs-lookup"><span data-stu-id="9de63-125">The connection is transparently re-directed to the mirror database, which now acts as the principal server.</span></span>  
  
 <span data-ttu-id="9de63-126">Quando uma conexão é estabelecida, o servidor principal envia a identidade de seu parceiro de failover ao cliente a ser usado quando ocorrer failover.</span><span class="sxs-lookup"><span data-stu-id="9de63-126">When a connection is established, the principal server sends the identity of its failover partner to the client to be used when failover occurs.</span></span> <span data-ttu-id="9de63-127">No caso de um aplicativo tentar estabelecer uma conexão depois que o servidor principal falhou, o cliente não sabe a identidade do parceiro de failover.</span><span class="sxs-lookup"><span data-stu-id="9de63-127">Where an application tried to establish a connection after the principal server failed, the client does not know the identity of the failover partner.</span></span> <span data-ttu-id="9de63-128">Para que os clientes possam lidar com este cenário, uma propriedade de inicialização e uma palavra-chave de cadeia de conexão associada permitem que o próprio cliente especifique a identidade do parceiro de failover.</span><span class="sxs-lookup"><span data-stu-id="9de63-128">To allow clients the opportunity to cope with this scenario, an initialization property and an associated connection string keyword allow the client to specify the identity of the failover partner on its own.</span></span> <span data-ttu-id="9de63-129">O atributo do cliente é usado apenas nesse cenário; se o servidor principal estiver disponível, ele não será usado.</span><span class="sxs-lookup"><span data-stu-id="9de63-129">The client attribute is used only in this scenario; if the principal server is available, it is not used.</span></span> <span data-ttu-id="9de63-130">Se o servidor do parceiro de failover fornecido pelo cliente não se referir a um servidor que está atuando como um parceiro de failover, a conexão será recusada pelo servidor.</span><span class="sxs-lookup"><span data-stu-id="9de63-130">If the failover partner server supplied by the client does not refer to a server acting as a failover partner, the connection is refused by the server.</span></span> <span data-ttu-id="9de63-131">Para que os aplicativos possam se adaptar a alterações de configuração, a identidade do parceiro de failover real pode ser determinada inspecionando o atributo depois que a conexão for estabelecida.</span><span class="sxs-lookup"><span data-stu-id="9de63-131">To allow applications to adapt to configuration changes, the identity of the actual failover partner can be determined by inspecting the attribute after the connection has been established.</span></span> <span data-ttu-id="9de63-132">Considere o armazenamento em cache das informações do parceiro para atualizar a cadeia de conexão ou criar uma estratégia de repetição no caso de falha da primeira tentativa de estabelecer uma conexão.</span><span class="sxs-lookup"><span data-stu-id="9de63-132">You should consider caching the partner information to update the connection string or devise a retry strategy in the event that the first attempt at making a connection fails.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9de63-133">Especifique explicitamente o banco de dados a ser usado por uma conexão, se desejar usar esse recurso em um DSN, uma cadeia de conexão ou uma propriedade/atributo da conexão.</span><span class="sxs-lookup"><span data-stu-id="9de63-133">You must explicitly specify the database to be used by a connection if you want to use this feature in a DSN, connection string, or connection property/attribute.</span></span> <span data-ttu-id="9de63-134">Se isso não for feito, o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client não tentará fazer failover para o banco de dados parceiro.</span><span class="sxs-lookup"><span data-stu-id="9de63-134">[!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client will not attempt to failover to the partner database if this is not done.</span></span>  
>   
>  <span data-ttu-id="9de63-135">O espelhamento é um recurso do banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9de63-135">Mirroring is a feature of the database.</span></span> <span data-ttu-id="9de63-136">Talvez os aplicativos que usam vários bancos de dados não consigam explorar esse recurso.</span><span class="sxs-lookup"><span data-stu-id="9de63-136">Applications that use multiple databases might not be able to exploit this feature.</span></span>  
>   
>  <span data-ttu-id="9de63-137">Além disso, os nomes de servidor não diferenciam maiúsculas de minúsculas, mas os nomes de banco de dados o fazem.</span><span class="sxs-lookup"><span data-stu-id="9de63-137">In addition, server names are case insensitive, but database names are case sensitive.</span></span> <span data-ttu-id="9de63-138">Portanto, certifique-se de usar as mesmas maiúsculas e minúsculas em DSNs e cadeias de conexões.</span><span class="sxs-lookup"><span data-stu-id="9de63-138">You should therefore make sure that you use the same casing in DSNs and connection strings.</span></span>  
  
## <a name="sql-server-native-client-ole-db-provider"></a><span data-ttu-id="9de63-139">Provedor OLE DB do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="9de63-139">SQL Server Native Client OLE DB Provider</span></span>  
 <span data-ttu-id="9de63-140">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo dá suporte ao espelhamento de banco de dados através de atributos de cadeia de conexão e conexão.</span><span class="sxs-lookup"><span data-stu-id="9de63-140">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider supports database mirroring through connection and connection string attributes.</span></span> <span data-ttu-id="9de63-141">A propriedade SSPROP_INIT_FAILOVERPARTNER foi adicionada ao conjunto de propriedades DBPROPSET_SQLSERVERDBINIT e a palavra-chave `FailoverPartner` é um novo atributo de cadeia de conexão para DBPROP_INIT_PROVIDERSTRING.</span><span class="sxs-lookup"><span data-stu-id="9de63-141">The SSPROP_INIT_FAILOVERPARTNER property has been added to the DBPROPSET_SQLSERVERDBINIT property set, and the `FailoverPartner` keyword is a new connection string attribute for DBPROP_INIT_PROVIDERSTRING.</span></span> <span data-ttu-id="9de63-142">Para obter mais informações, consulte [usando palavras-chave da cadeia de conexão com SQL Server Native Client](../applications/using-connection-string-keywords-with-sql-server-native-client.md).</span><span class="sxs-lookup"><span data-stu-id="9de63-142">For more information, see [Using Connection String Keywords with SQL Server Native Client](../applications/using-connection-string-keywords-with-sql-server-native-client.md).</span></span>  
  
 <span data-ttu-id="9de63-143">O cache de failover é mantido, desde que o provedor seja carregado, o que é até que **CoUninitialize** seja chamado ou desde que o aplicativo tenha uma referência a algum objeto gerenciado pelo [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] provedor de OLE DB de cliente nativo, como um objeto de fonte de dados.</span><span class="sxs-lookup"><span data-stu-id="9de63-143">The failover cache is maintained as long as the provider is loaded, which is until **CoUninitialize** is called or as long as the application has a reference to some object managed by the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider such as a data source object.</span></span>  
  
 <span data-ttu-id="9de63-144">Para obter detalhes sobre o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] suporte ao provedor de OLE DB nativo do cliente para espelhamento de banco de dados, consulte [Propriedades de inicialização e autorização](../../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span><span class="sxs-lookup"><span data-stu-id="9de63-144">For details about [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client OLE DB provider support for database mirroring, see [Initialization and Authorization Properties](../../native-client-ole-db-data-source-objects/initialization-and-authorization-properties.md).</span></span>  
  
## <a name="sql-server-native-client-odbc-driver"></a><span data-ttu-id="9de63-145">Driver ODBC do SQL Server Native Client</span><span class="sxs-lookup"><span data-stu-id="9de63-145">SQL Server Native Client ODBC Driver</span></span>  
 <span data-ttu-id="9de63-146">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] driver ODBC do Native Client dá suporte ao espelhamento de banco de dados por meio de atributos de cadeia de conexão e conexão.</span><span class="sxs-lookup"><span data-stu-id="9de63-146">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Native Client ODBC driver supports database mirroring through connection and connection string attributes.</span></span> <span data-ttu-id="9de63-147">Especificamente, o atributo SQL_COPT_SS_FAILOVER_PARTNER foi adicionado para uso com as funções [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) e [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md) ; e a `Failover_Partner` palavra-chave foi adicionada como um novo atributo de cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="9de63-147">Specifically, the SQL_COPT_SS_FAILOVER_PARTNER attribute has been added for use with the [SQLSetConnectAttr](../../native-client-odbc-api/sqlsetconnectattr.md) and [SQLGetConnectAttr](../../native-client-odbc-api/sqlgetconnectattr.md) functions; and the `Failover_Partner` keyword has been added as a new connection string attribute.</span></span>  
  
 <span data-ttu-id="9de63-148">O cache de failover é mantido enquanto o aplicativo tem pelo menos um identificador de ambiente alocado.</span><span class="sxs-lookup"><span data-stu-id="9de63-148">The failover cache is maintained as long as the application has at least one environment handle allocated.</span></span> <span data-ttu-id="9de63-149">Por outro lado, ele é perdido quando o último identificador de ambiente for desalocado.</span><span class="sxs-lookup"><span data-stu-id="9de63-149">Conversely, it is lost when the last environment handle is deallocated.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="9de63-150">O Gerenciador de Driver ODBC foi aprimorado para dar suporte à especificação do nome do servidor de failover.</span><span class="sxs-lookup"><span data-stu-id="9de63-150">The ODBC Driver Manager has been enhanced to support the specification of the failover server name.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="9de63-151">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="9de63-151">See Also</span></span>  
 <span data-ttu-id="9de63-152">[Recursos do SQL Server Native Client](sql-server-native-client-features.md) </span><span class="sxs-lookup"><span data-stu-id="9de63-152">[SQL Server Native Client Features](sql-server-native-client-features.md) </span></span>  
 <span data-ttu-id="9de63-153">[Conectar clientes a uma sessão de espelhamento de banco de dados &#40;SQL Server&#41;](../../../database-engine/database-mirroring/connect-clients-to-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="9de63-153">[Connect Clients to a Database Mirroring Session &#40;SQL Server&#41;](../../../database-engine/database-mirroring/connect-clients-to-a-database-mirroring-session-sql-server.md) </span></span>  
 [<span data-ttu-id="9de63-154">Espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9de63-154">Database Mirroring &#40;SQL Server&#41;</span></span>](../../../database-engine/database-mirroring/database-mirroring-sql-server.md)  
  
  