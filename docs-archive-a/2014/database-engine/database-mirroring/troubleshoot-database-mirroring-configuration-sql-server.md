---
title: Solução de problemas de configuração de espelhamento de banco de dados (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- endpoints [SQL Server], database mirroring
- database mirroring [SQL Server], troubleshooting
- troubleshooting [SQL Server], database mirroring
ms.assetid: 87d3801b-dc52-419e-9316-8b1f1490946c
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 0dafd98f721bfc2d2d0dd64a9f97689466529407
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87572691"
---
# <a name="troubleshoot-database-mirroring-configuration-sql-server"></a><span data-ttu-id="618a1-102">Solução de problemas de configuração de espelhamento de banco de dados (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="618a1-102">Troubleshoot Database Mirroring Configuration (SQL Server)</span></span>
  <span data-ttu-id="618a1-103">Este tópico fornece informações para ajudá-lo a solucionar problemas ao configurar uma sessão de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="618a1-103">This topic provides information to help you troubleshoot problems in setting up a database mirroring session.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="618a1-104"> Assegure-se de que você está satisfazendo todos os pré-requisitos [para o espelhamento de banco de dados](prerequisites-restrictions-and-recommendations-for-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="618a1-104">Ensure that you are meeting all the [prerequisites for database mirroring](prerequisites-restrictions-and-recommendations-for-database-mirroring.md).</span></span>  
  
|<span data-ttu-id="618a1-105">Problema</span><span class="sxs-lookup"><span data-stu-id="618a1-105">Issue</span></span>|<span data-ttu-id="618a1-106">Resumo</span><span class="sxs-lookup"><span data-stu-id="618a1-106">Summary</span></span>|  
|-----------|-------------|  
|<span data-ttu-id="618a1-107">Mensagem de erro 1418</span><span class="sxs-lookup"><span data-stu-id="618a1-107">Error Message 1418</span></span>|<span data-ttu-id="618a1-108">Essa mensagem do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] indica que o endereço de rede de servidor não pode ser alcançado ou pode não existir, e sugere que você verifique o nome de endereço de rede e emita novamente o comando.</span><span class="sxs-lookup"><span data-stu-id="618a1-108">This [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] message indicates that the server network address cannot be reached or does not exist, and it suggests that you verify the network address name and reissue the command.</span></span> <span data-ttu-id="618a1-109">Para obter mais informações, veja o tópico [MSSQLSERVER_1418](../../relational-databases/errors-events/mssqlserver-1418-database-engine-error.md) .</span><span class="sxs-lookup"><span data-stu-id="618a1-109">For more information, see the [MSSQLSERVER_1418](../../relational-databases/errors-events/mssqlserver-1418-database-engine-error.md) topic.</span></span>|  
|[<span data-ttu-id="618a1-110">Contas</span><span class="sxs-lookup"><span data-stu-id="618a1-110">Accounts</span></span>](#Accounts)|<span data-ttu-id="618a1-111">Discute os requisitos para configurar corretamente as contas nas quais o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] será executado.</span><span class="sxs-lookup"><span data-stu-id="618a1-111">Discusses requirements for correctly configuring the accounts under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running.</span></span>|  
|[<span data-ttu-id="618a1-112">Pontos de extremidade</span><span class="sxs-lookup"><span data-stu-id="618a1-112">Endpoints</span></span>](#Endpoints)|<span data-ttu-id="618a1-113">Discute os requisitos para configurar corretamente o ponto de extremidade do espelhamento de banco de dados de cada instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="618a1-113">Discusses requirements for correctly configuring the database mirroring endpoint of each server instance.</span></span>|  
|[<span data-ttu-id="618a1-114">SystemAddress</span><span class="sxs-lookup"><span data-stu-id="618a1-114">SystemAddress</span></span>](#SystemAddress)|<span data-ttu-id="618a1-115">Resume as alternativas para especificar o nome de sistema de uma instância do servidor em uma configuração de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="618a1-115">Summarizes the alternatives for specifying the system name of a server instance in a database mirroring configuration.</span></span>|  
|[<span data-ttu-id="618a1-116">Acesso de rede</span><span class="sxs-lookup"><span data-stu-id="618a1-116">Network access</span></span>](#NetworkAccess)|<span data-ttu-id="618a1-117">Documenta o requisito de cada instância do servidor para acessar as portas de outra instância do servidor ou instâncias no TCP.</span><span class="sxs-lookup"><span data-stu-id="618a1-117">Documents the requirement that each the server instance be able to access the ports of the other server instance or instances over TCP.</span></span>|  
|[<span data-ttu-id="618a1-118">Preparação do banco de dados espelho</span><span class="sxs-lookup"><span data-stu-id="618a1-118">Mirror database preparation</span></span>](#MirrorDbPrep)|<span data-ttu-id="618a1-119">Resume os requisitos para preparar o banco de dados espelho para habilitar o início do espelhamento.</span><span class="sxs-lookup"><span data-stu-id="618a1-119">Summarizes the requirements for preparing the mirror database to enable mirroring to start.</span></span>|  
|[<span data-ttu-id="618a1-120">Falha na operação para criar arquivo</span><span class="sxs-lookup"><span data-stu-id="618a1-120">Failed create-file operation</span></span>](#FailedCreateFileOp)|<span data-ttu-id="618a1-121">Descreve como responder a uma falha na operação para criar arquivo.</span><span class="sxs-lookup"><span data-stu-id="618a1-121">Describes how to respond to a failed create-file operation.</span></span>|  
|[<span data-ttu-id="618a1-122">Iniciando o espelhamento usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="618a1-122">Starting mirroring by Using Transact-SQL</span></span>](#StartDbm)|<span data-ttu-id="618a1-123">Descreve a ordem exigida para as instruções ALTER DATABASE *nome_banco_dados* SET PARTNER **='***servidor_parceiro***'** .</span><span class="sxs-lookup"><span data-stu-id="618a1-123">Describes the required order for ALTER DATABASE *database_name* SET PARTNER **='***partner_server***'** statements.</span></span>|  
|[<span data-ttu-id="618a1-124">Transações envolvendo todos os bancos de dados</span><span class="sxs-lookup"><span data-stu-id="618a1-124">Cross-Database Transactions</span></span>](#CrossDbTxns)|<span data-ttu-id="618a1-125">Um failover automático pode levar a uma resolução automática e possivelmente incorreta de transações duvidosas.</span><span class="sxs-lookup"><span data-stu-id="618a1-125">An automatic failover could lead to automatic and possibly incorrect resolution of in-doubt transactions.</span></span> <span data-ttu-id="618a1-126">Por esta razão, o espelhamento de banco de dados não dá suporte a transações envolvendo todos os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="618a1-126">For this reason database mirroring does not support cross-database transactions.</span></span>|  
  
##  <a name="accounts"></a><a name="Accounts"></a> <span data-ttu-id="618a1-127">Contas</span><span class="sxs-lookup"><span data-stu-id="618a1-127">Accounts</span></span>  
 <span data-ttu-id="618a1-128">As contas nas quais o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está sendo executado devem ser configuradas corretamente.</span><span class="sxs-lookup"><span data-stu-id="618a1-128">The accounts under which [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running must be correctly configured.</span></span>  
  
1.  <span data-ttu-id="618a1-129">As contas têm as permissões corretas?</span><span class="sxs-lookup"><span data-stu-id="618a1-129">Do the accounts have the correct permissions?</span></span>  
  
    1.  <span data-ttu-id="618a1-130">Se as contas estiverem sendo executadas nas mesmas contas de domínio, as chances de uma configuração incorreta são reduzidas.</span><span class="sxs-lookup"><span data-stu-id="618a1-130">If the accounts are running in the same domain accounts, the chances of misconfiguration are reduced.</span></span>  
  
    2.  <span data-ttu-id="618a1-131">Se as contas estiverem executando em domínios diferentes ou não são contas de domínio, o logon de uma conta deve ser criado em **mestre** no outro computador e esse logon deve ter permissões concedidas em CONNECT no ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="618a1-131">If the accounts are running in different domains or are not domain accounts, the login of one account must be created in **master** on the other computer, and that login must be granted CONNECT permissions on the endpoint.</span></span> <span data-ttu-id="618a1-132">Para obter mais informações, consulte [Gerenciar metadados ao disponibilizar um banco de dados em outra instância do servidor &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span><span class="sxs-lookup"><span data-stu-id="618a1-132">For more information, see [Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md).</span></span> <span data-ttu-id="618a1-133">Isso inclui a conta de Serviço de Rede.</span><span class="sxs-lookup"><span data-stu-id="618a1-133">This includes the Network Service account.</span></span>  
  
2.  <span data-ttu-id="618a1-134">Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] estiver executando como um serviço que está usando a conta Sistema Local, você deve usar certificados para autenticação.</span><span class="sxs-lookup"><span data-stu-id="618a1-134">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] is running as a service that is using the local system account, you must use certificates for authentication.</span></span> <span data-ttu-id="618a1-135">Para obter mais informações, consulte [Usar certificados para um ponto de extremidade de espelhamento de banco de dados &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="618a1-135">For more information, see [Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md).</span></span>  
  
##  <a name="endpoints"></a><a name="Endpoints"></a> <span data-ttu-id="618a1-136">Endpoints</span><span class="sxs-lookup"><span data-stu-id="618a1-136">Endpoints</span></span>  
 <span data-ttu-id="618a1-137">Os pontos de extremidade devem ser configurados corretamente.</span><span class="sxs-lookup"><span data-stu-id="618a1-137">Endpoints must be correctly configured.</span></span>  
  
1.  <span data-ttu-id="618a1-138">Verifique se cada instância do servidor (o servidor principal, servidor espelho e testemunha, se houver) tem um ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="618a1-138">Make sure that each server instance (the principal server, mirror server, and witness, if any) has a database mirroring endpoint.</span></span> <span data-ttu-id="618a1-139">Para obter mais informações, veja [sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) e, dependendo do formato de autenticação, [Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) ou [Usar certificados para um ponto de extremidade de espelhamento de banco de dados &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="618a1-139">For more information, see [sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) and, depending on the form of authentication, either [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) or [Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="618a1-140">Verifique se os números da porta estão corretos.</span><span class="sxs-lookup"><span data-stu-id="618a1-140">Check that the port numbers are correct.</span></span>  
  
     <span data-ttu-id="618a1-141">Para identificar a porta atualmente associada ao ponto de extremidade do espelhamento de banco de dados de uma instância de servidor, use as exibições de catálogo [sys.database_mirroring_endpoints](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) e [sys.tcp_endpoints](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="618a1-141">To identify the port currently associated with database mirroring endpoint of a server instance, use the [sys.database_mirroring_endpoints](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql) and [sys.tcp_endpoints](/sql/relational-databases/system-catalog-views/sys-tcp-endpoints-transact-sql) catalog views.</span></span>  
  
3.  <span data-ttu-id="618a1-142">Para os problemas da configuração de espelhamento de banco de dados que são difíceis de explicar, recomendamos que você inspecione cada instância do servidor para determinar se está escutando nas portas corretas.</span><span class="sxs-lookup"><span data-stu-id="618a1-142">For database mirroring setup issues that are difficult to explain, we recommend that you inspect each server instance to determine whether it is listening on the correct ports.</span></span> <span data-ttu-id="618a1-143">Para obter mais informações sobre como verificar a disponibilidade de porta, veja [MSSQLSERVER_1418](../../relational-databases/errors-events/mssqlserver-1418-database-engine-error.md).</span><span class="sxs-lookup"><span data-stu-id="618a1-143">For information about verifying port availability, see [MSSQLSERVER_1418](../../relational-databases/errors-events/mssqlserver-1418-database-engine-error.md).</span></span>  
  
4.  <span data-ttu-id="618a1-144">Verifique se os pontos de extremidade foram iniciados (STATE=STARTED).</span><span class="sxs-lookup"><span data-stu-id="618a1-144">Make sure that the endpoints are started (STATE=STARTED).</span></span> <span data-ttu-id="618a1-145">Em cada instância do servidor, use a seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="618a1-145">On each server instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
    ```  
    SELECT state_desc FROM sys.database_mirroring_endpoints  
    ```  
  
     <span data-ttu-id="618a1-146">Para obter mais informações sobre a coluna **state_desc**, veja [sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="618a1-146">For more information about the **state_desc** column, see [sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql).</span></span>  
  
     <span data-ttu-id="618a1-147">Para iniciar um ponto de extremidade, use a seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="618a1-147">To start an endpoint, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
    ```  
    ALTER ENDPOINT Endpoint_Mirroring   
    STATE = STARTED   
    AS TCP (LISTENER_PORT = <port_number>)  
    FOR database_mirroring (ROLE = ALL);  
    GO  
    ```  
  
     <span data-ttu-id="618a1-148">Para obter mais informações, consulte [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="618a1-148">For more information, see [ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql).</span></span>  
  
5.  <span data-ttu-id="618a1-149">Verifique se o ROLE está correto.</span><span class="sxs-lookup"><span data-stu-id="618a1-149">Check that the ROLE is correct.</span></span> <span data-ttu-id="618a1-150">Em cada instância do servidor, use a seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="618a1-150">On each server instance use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
    ```  
    SELECT role FROM sys.database_mirroring_endpoints;  
    GO  
    ```  
  
     <span data-ttu-id="618a1-151">Para obter mais informações, veja [sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="618a1-151">For more information, see [sys.database_mirroring_endpoints &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-database-mirroring-endpoints-transact-sql).</span></span>  
  
6.  <span data-ttu-id="618a1-152">O logon para a conta de serviço da outra instância de servidor exige permissão CONNECT.</span><span class="sxs-lookup"><span data-stu-id="618a1-152">The login for the service account from the other server instance requires CONNECT permission.</span></span> <span data-ttu-id="618a1-153">Verifique se o logon do outro servidor tem permissão CONNECT.</span><span class="sxs-lookup"><span data-stu-id="618a1-153">Make sure that the login from the other server has CONNECT permission.</span></span> <span data-ttu-id="618a1-154">Para determinar quem tem permissão CONNECT para um ponto de extremidade, em cada instância do servidor use a instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] seguinte.</span><span class="sxs-lookup"><span data-stu-id="618a1-154">To determine who has CONNECT permission for an endpoint, on each server instance use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement.</span></span>  
  
    ```  
    SELECT 'Metadata Check';  
    SELECT EP.name, SP.STATE,   
       CONVERT(nvarchar(38), suser_name(SP.grantor_principal_id))   
          AS GRANTOR,   
       SP.TYPE AS PERMISSION,  
       CONVERT(nvarchar(46),suser_name(SP.grantee_principal_id))   
          AS GRANTEE   
       FROM sys.server_permissions SP , sys.endpoints EP  
       WHERE SP.major_id = EP.endpoint_id  
       ORDER BY Permission,grantor, grantee;   
    GO  
  
    ```  
  
##  <a name="system-address"></a><a name="SystemAddress"></a> <span data-ttu-id="618a1-155">Endereço de sistema</span><span class="sxs-lookup"><span data-stu-id="618a1-155">System Address</span></span>  
 <span data-ttu-id="618a1-156">Para o nome de sistema de uma instância do servidor em uma configuração de espelhamento de banco de dados, você pode usar qualquer nome que inequivocamente identifique o sistema.</span><span class="sxs-lookup"><span data-stu-id="618a1-156">For the system name of a server instance in a database mirroring configuration, you can use any name that unambiguously identifies the system.</span></span> <span data-ttu-id="618a1-157">O endereço de servidor pode ser um nome de sistema (se os sistemas estiverem no mesmo domínio), um nome de domínio totalmente qualificado ou um endereço de IP (preferivelmente, um endereço de IP estático).</span><span class="sxs-lookup"><span data-stu-id="618a1-157">The server address can be a system name (if the systems are in the same domain), a fully qualified domain name, or an IP address (preferably, a static IP address).</span></span> <span data-ttu-id="618a1-158">Usando o nome de domínio totalmente qualificado o funcionamento é garantido.</span><span class="sxs-lookup"><span data-stu-id="618a1-158">Using the fully qualified domain name is guaranteed to work.</span></span> <span data-ttu-id="618a1-159">Para obter mais informações, consulte [Especificar um endereço de rede do servidor &#40;Espelhamento de banco de dados&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="618a1-159">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
##  <a name="network-access"></a><a name="NetworkAccess"></a> <span data-ttu-id="618a1-160">Network Access</span><span class="sxs-lookup"><span data-stu-id="618a1-160">Network Access</span></span>  
 <span data-ttu-id="618a1-161">Cada instância do servidor deve poder acessar as portas da outra instância do servidor ou instâncias em TCP.</span><span class="sxs-lookup"><span data-stu-id="618a1-161">Each server instance must be able to access the ports of the other server instance or instances over TCP.</span></span> <span data-ttu-id="618a1-162">Isso será especialmente importante se as instâncias do servidor estiverem em domínios diferentes que não confiam um no outro (domínios não confiáveis).</span><span class="sxs-lookup"><span data-stu-id="618a1-162">This is especially important if the server instances are in different domains that do not trust each other (untrusted domains).</span></span> <span data-ttu-id="618a1-163">Isso restringe muito da comunicação entre as instâncias do servidor.</span><span class="sxs-lookup"><span data-stu-id="618a1-163">This restricts much of the communication between the server instances.</span></span>  
  
##  <a name="mirror-database-preparation"></a><a name="MirrorDbPrep"></a> <span data-ttu-id="618a1-164">Mirror Database Preparation</span><span class="sxs-lookup"><span data-stu-id="618a1-164">Mirror Database Preparation</span></span>  
 <span data-ttu-id="618a1-165">Se iniciar o espelhamento pela primeira vez ou iniciá-lo novamente depois do espelhamento ser removido, verifique se o banco de dados espelho está preparado para o espelhamento.</span><span class="sxs-lookup"><span data-stu-id="618a1-165">Whether starting mirroring for the first time or starting it again after mirroring was removed, verify that the mirror database is prepared for mirroring.</span></span>  
  
 <span data-ttu-id="618a1-166">Quando você criar o banco de dados espelho no servidor espelho, certifique-se de restaurar o backup do banco de dados principal especificando o mesmo nome de banco de dados WITH NORECOVERY.</span><span class="sxs-lookup"><span data-stu-id="618a1-166">When you create the mirror database on the mirror server, make sure that you restore the backup of the principal database specifying the same database name WITH NORECOVERY.</span></span> <span data-ttu-id="618a1-167">Além disso, deve-se aplicar também a todos os backups de log, criados depois que esse backup foi feito, WITH NORECOVERY novamente</span><span class="sxs-lookup"><span data-stu-id="618a1-167">Also, all log backups created after that backup was taken must also be applied, again WITH NORECOVERY.</span></span>  
  
 <span data-ttu-id="618a1-168">Também recomendamos que, se possível, o caminho do arquivo (inclusive a letra da unidade) do banco de dados espelho seja idêntico ao caminho do banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="618a1-168">Also, we recommend that, if it is possible, the file path (including the drive letter) of the mirror database be identical to the path of the principal database.</span></span> <span data-ttu-id="618a1-169">Se os caminhos de arquivo precisarem ser diferentes, por exemplo, se o banco de dados principal estiver na unidade 'F': mas o sistema espelho não tiver uma unidade F:, será necessário incluir a opção MOVE na instrução RESTORE.</span><span class="sxs-lookup"><span data-stu-id="618a1-169">If the file paths must differ, for example, if the principal database is on drive 'F:' but the mirror system lacks an F: drive, you must include the MOVE option in the RESTORE statement.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="618a1-170">Se você mover os arquivos de banco de dados quando estiver criando o banco de dados espelho, pode não ser capaz de acrescentar arquivos posteriormente ao banco de dados sem a suspensão do espelhamento.</span><span class="sxs-lookup"><span data-stu-id="618a1-170">If you move the database files when you are creating the mirror database, you might be unable to add files to the database later without mirroring being suspended.</span></span>  
  
 <span data-ttu-id="618a1-171">Se o espelhamento de banco de dados foi interrompido, todos os backups de logs subsequentes do banco de dados principal devem ser aplicados ao banco de dados espelho antes que o espelhamento possa ser reinicializado.</span><span class="sxs-lookup"><span data-stu-id="618a1-171">If database mirroring has been stopped, all subsequent log backups taken on the principal database must be applied to the mirror database before mirroring can be restarted.</span></span>  
  
 <span data-ttu-id="618a1-172">Para obter mais informações, veja [Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="618a1-172">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
##  <a name="failed-create-file-operation"></a><a name="FailedCreateFileOp"></a> <span data-ttu-id="618a1-173">Failed Create-File Operation</span><span class="sxs-lookup"><span data-stu-id="618a1-173">Failed Create-File Operation</span></span>  
 <span data-ttu-id="618a1-174">Para que a inclusão de um arquivo não afete uma sessão de espelhamento, o caminho do arquivo deve existir nos dois servidores.</span><span class="sxs-lookup"><span data-stu-id="618a1-174">Adding a file without impacting a mirroring session requires that the path of the file exist on both servers.</span></span> <span data-ttu-id="618a1-175">Portanto, se você mover os arquivos de banco de dados quando estiver criando o banco de dados espelho, uma operação adicionar arquivo posterior pode não funcionar no banco de dados espelho e causar a suspensão do espelhamento.</span><span class="sxs-lookup"><span data-stu-id="618a1-175">Therefore, if you move the database files when creating the mirror database, a later add-file operation might fail on the mirror database and cause mirroring to be suspended.</span></span>  
  
 <span data-ttu-id="618a1-176">Para corrigir o problema:</span><span class="sxs-lookup"><span data-stu-id="618a1-176">To fix the problem:</span></span>  
  
1.  <span data-ttu-id="618a1-177">O proprietário do banco de dados deve remover a sessão de espelhamento e restaurar o backup completo do grupo de arquivos que contém o arquivo adicionado.</span><span class="sxs-lookup"><span data-stu-id="618a1-177">The database owner must remove the mirroring session and restore a full backup of the filegroup that contains the added file.</span></span>  
  
2.  <span data-ttu-id="618a1-178">O proprietário do banco de dados deve fazer backup do log que contém a operação adicionar arquivo no servidor principal e restaurar manualmente o backup do log no banco de dados espelho usando as opções WITH NORECOVERY e WITH MOVE.</span><span class="sxs-lookup"><span data-stu-id="618a1-178">The owner must then back up the log containing the add-file operation on the principal server and manually restore the log backup on the mirror database using the WITH NORECOVERY and WITH MOVE options.</span></span> <span data-ttu-id="618a1-179">Isso criará o caminho de arquivo especificado no servidor espelho e irá restaurar o novo arquivo nesse local.</span><span class="sxs-lookup"><span data-stu-id="618a1-179">Doing this creates the specified file path on the mirror server and restores the new file to that location.</span></span>  
  
3.  <span data-ttu-id="618a1-180">Para preparar o banco de dados para a nova sessão de espelhamento, o proprietário também deve restaurar usando WITH NORECOVERY todos os backups de log pendentes a partir do servidor principal.</span><span class="sxs-lookup"><span data-stu-id="618a1-180">To prepare the database for a new mirroring session, the owner must also restore WITH NO RECOVERY any other outstanding log backups from the principal server.</span></span>  
  
 <span data-ttu-id="618a1-181">Para obter mais informações, veja [Remover o espelhamento de banco de dados&#40;SQL Server&#41;](database-mirroring-sql-server.md), [Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md), [Estabelecer uma sessão de espelhamento de banco de dados com a Autenticação do Windows &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md), [Usar certificados para um ponto de extremidade do espelhamento de banco de dados &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md) ou [Estabelecer uma sessão de espelhamento de banco de dados com a Autenticação do Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="618a1-181">For more information, see [Removing Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md), [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md), [Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md), [Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md), or [Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span></span>  
  
##  <a name="starting-mirroring-by-using-transact-sql"></a><a name="StartDbm"></a><span data-ttu-id="618a1-182">Iniciando o espelhamento usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="618a1-182">Starting mirroring by Using Transact-SQL</span></span>  
 <span data-ttu-id="618a1-183">A ordem na qual as instruções ALTER DATABASE *nome_banco_dados* SET PARTNER **='***servidor_parceiro***'** são emitidas é muito importante.</span><span class="sxs-lookup"><span data-stu-id="618a1-183">The order in which the ALTER DATABASE *database_name* SET PARTNER **='***partner_server***'** statements are issued is very important.</span></span>  
  
1.  <span data-ttu-id="618a1-184">A primeira instrução deve ser executada no servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="618a1-184">The first statement must be run on the mirror server.</span></span> <span data-ttu-id="618a1-185">Quando essa instrução for emitida, o servidor espelho não tenta contatar qualquer outra instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="618a1-185">When this statement is issued, the mirror server does not try to contact any other server instance.</span></span> <span data-ttu-id="618a1-186">Em vez disso, o servidor espelho instrui seu banco de dados para esperar até que o servidor espelho seja contatado pelo servidor principal.</span><span class="sxs-lookup"><span data-stu-id="618a1-186">Instead, the mirror server instructs its database to wait until the mirror server has been contacted by the principal server.</span></span>  
  
2.  <span data-ttu-id="618a1-187">A segunda instrução ALTER DATABASE deve ser executada no servidor principal.</span><span class="sxs-lookup"><span data-stu-id="618a1-187">The second ALTER DATABASE statement must be run on the principal server.</span></span> <span data-ttu-id="618a1-188">Essa instrução faz o servidor principal tentar se conectar ao servidor espelho.</span><span class="sxs-lookup"><span data-stu-id="618a1-188">This statement causes the principal server to try to connect to the mirror server.</span></span> <span data-ttu-id="618a1-189">Depois que essa conexão é criada, o espelho, então, tenta conectar ao servidor principal em outra conexão.</span><span class="sxs-lookup"><span data-stu-id="618a1-189">After that connection is created, the mirror then tries to connect to the principal server on another connection.</span></span>  
  
 <span data-ttu-id="618a1-190">Para obter mais informações, veja [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="618a1-190">For more information, see [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="618a1-191">Para obter informações sobre como usar o [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] para iniciar o espelhamento, veja [Estabelecer uma sessão de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="618a1-191">For information about using [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] to start mirroring, see [Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span></span>  
  
##  <a name="cross-database-transactions"></a><a name="CrossDbTxns"></a><span data-ttu-id="618a1-192">Transações entre bancos de dados</span><span class="sxs-lookup"><span data-stu-id="618a1-192">Cross-Database Transactions</span></span>  
 <span data-ttu-id="618a1-193">Quando um banco de dados está sendo espelhado no modo de alta-segurança com failover automático, um failover automático pode levar a uma resolução automática e possivelmente incorreta de transações incertas.</span><span class="sxs-lookup"><span data-stu-id="618a1-193">When a database is being mirrored in high-safety mode with automatic failover, an automatic failover could lead to automatic and possibly incorrect resolution of in-doubt transactions.</span></span> <span data-ttu-id="618a1-194">Se um failover automático acontecer em qualquer banco de dados enquanto uma transação envolvendo todos os bancos de dados está sendo confirmada, poderão ocorrer inconsistências lógicas entre os bancos de dados.</span><span class="sxs-lookup"><span data-stu-id="618a1-194">If an automatic failover occurs on either database while a cross-database transaction is being committed, logical inconsistencies can occur between the databases.</span></span>  
  
 <span data-ttu-id="618a1-195">Os tipos de transações envolvendo todos os bancos de dados que podem ser afetadas por um failover automático incluem o seguinte:</span><span class="sxs-lookup"><span data-stu-id="618a1-195">The types of cross-database transactions that can be affected by an automatic failover include the following:</span></span>  
  
-   <span data-ttu-id="618a1-196">Uma transação que está atualizando vários bancos de dados na mesma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="618a1-196">A transaction that is updating multiple databases in the same instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
-   <span data-ttu-id="618a1-197">Transações que usam MS DTC (Coordenador de Transações Distribuídas da [!INCLUDE[msCoName](../../includes/msconame-md.md)] ).</span><span class="sxs-lookup"><span data-stu-id="618a1-197">Transactions that use a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Distributed Transaction Coordinator (MS DTC).</span></span>  
  
 <span data-ttu-id="618a1-198">Para obter mais informações, consulte [Transações envolvendo todos os bancos de dados sem suporte para espelhamento de banco de dados ou Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](../availability-groups/windows/transactions-always-on-availability-and-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="618a1-198">For more information, see [Cross-Database Transactions Not Supported For Database Mirroring or AlwaysOn Availability Groups &#40;SQL Server&#41;](../availability-groups/windows/transactions-always-on-availability-and-database-mirroring.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="618a1-199">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="618a1-199">See Also</span></span>  
 <span data-ttu-id="618a1-200">[Configurando o espelhamento de banco de dados &#40;SQL Server&#41;](setting-up-database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="618a1-200">[Setting Up Database Mirroring &#40;SQL Server&#41;](setting-up-database-mirroring-sql-server.md) </span></span>  
 [<span data-ttu-id="618a1-201">Segurança de transporte para espelhamento de banco de dados e Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="618a1-201">Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](transport-security-database-mirroring-always-on-availability.md)  
  
  