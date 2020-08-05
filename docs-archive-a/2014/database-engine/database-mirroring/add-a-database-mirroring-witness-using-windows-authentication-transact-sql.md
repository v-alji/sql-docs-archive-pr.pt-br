---
title: Adicionar uma testemunha de espelhamento de banco de dados usando a Autenticação do Windows (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- witness [SQL Server], establishing
- Windows authentication [SQL Server]
- database mirroring [SQL Server], witness
ms.assetid: bf5e87df-91a4-49f9-ae88-2a6dcf644510
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 88684c3a1ca12ea579859759ed804ca281647fa5
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87571592"
---
# <a name="add-a-database-mirroring-witness-using-windows-authentication-transact-sql"></a><span data-ttu-id="25f96-102">Adicionar uma testemunha de espelhamento de banco de dados usando a Autenticação do Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="25f96-102">Add a Database Mirroring Witness Using Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="25f96-103">Para definir uma testemunha para um banco de dados, o proprietário do banco de dados nomeia uma instância do Mecanismo de Banco de Dados para a função de servidor testemunha.</span><span class="sxs-lookup"><span data-stu-id="25f96-103">To set up a witness for a database, the database owner assigns a Database Engine instance to the role of witness server.</span></span> <span data-ttu-id="25f96-104">A instância do servidor testemunha pode ser executada no mesmo computador que a instância do servidor principal ou espelho, mas isso reduz a robustez de failover automático substancialmente.</span><span class="sxs-lookup"><span data-stu-id="25f96-104">The witness server instance can run on the same computer as the principal or mirror server instance, but this substantially reduces the robustness of automatic failover.</span></span>  
  
 <span data-ttu-id="25f96-105">A localização da testemunha em um computador separado é altamente recomendável.</span><span class="sxs-lookup"><span data-stu-id="25f96-105">We strongly recommend that the witness reside on a separate computer.</span></span> <span data-ttu-id="25f96-106">Uma determinada instância do servidor pode participar de várias sessões de espelhamento de banco de dados simultâneos com os mesmos ou diferentes parceiros.</span><span class="sxs-lookup"><span data-stu-id="25f96-106">A given server can participate in multiple concurrent database mirroring sessions with the same or different partners.</span></span> <span data-ttu-id="25f96-107">Um determinado servidor pode ser um parceiro em algumas sessões e uma testemunha em outras sessões.</span><span class="sxs-lookup"><span data-stu-id="25f96-107">A given server can be a partner in some sessions and a witness in other sessions.</span></span>  
  
 <span data-ttu-id="25f96-108">A testemunha é planejada exclusivamente para um modo de alta segurança com failover automático.</span><span class="sxs-lookup"><span data-stu-id="25f96-108">The witness is intended exclusively for high-safety mode with automatic failover.</span></span> <span data-ttu-id="25f96-109">Antes de você definir uma testemunha, recomendamos enfaticamente que verifique se a propriedade SAFETY está definida atualmente como FULL.</span><span class="sxs-lookup"><span data-stu-id="25f96-109">Before you set a witness, we strongly recommend that you ensure that the SAFETY property is currently set to FULL.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="25f96-110">É recomendável configurar um espelhamento de banco de dados fora do horário de pico, pois a configuração pode afetar o desempenho.</span><span class="sxs-lookup"><span data-stu-id="25f96-110">We recommend that you configure database mirroring during off-peak hours because configuration can impact performance.</span></span>  
  
### <a name="to-establish-a-witness"></a><span data-ttu-id="25f96-111">Para estabelecer uma testemunha</span><span class="sxs-lookup"><span data-stu-id="25f96-111">To establish a witness</span></span>  
  
1.  <span data-ttu-id="25f96-112">Na instância do servidor testemunha, verifique se existe um ponto de extremidade para espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="25f96-112">On the witness server instance, ensure that an endpoint exists for database mirroring.</span></span> <span data-ttu-id="25f96-113">Independentemente do número de sessões de espelhamento com suporte, a instância do servidor só deve ter um ponto de extremidade do espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="25f96-113">Regardless of the number of mirroring session to be supported, the server instance must have only one database mirroring endpoint.</span></span> <span data-ttu-id="25f96-114">Se você pretende usar essa instância de servidor exclusivamente como uma testemunha em sessões de espelhamento de banco de dados, atribua a função de testemunha ao ponto de extremidade (testemunha de função **=** ).</span><span class="sxs-lookup"><span data-stu-id="25f96-114">If you intend to use this server instance exclusively as a witness in database mirroring sessions, assign the role of witness to the endpoint (ROLE **=** WITNESS).</span></span> <span data-ttu-id="25f96-115">Se você também pretender usar essa instância do servidor como testemunha em uma ou mais sessões de espelhamento de banco de dados, atribua a função do ponto de extremidade como ALL.</span><span class="sxs-lookup"><span data-stu-id="25f96-115">If you intend to use this server instance as a partner in one or more other database mirroring sessions, assign the role of the endpoint as ALL.</span></span>  
  
     <span data-ttu-id="25f96-116">Para executar uma instrução SET WITNESS, a sessão de espelhamento de banco de dados já deve ter começado (entre parceiros), e o STATE do ponto de extremidade da testemunha deve estar definido como STARTED.</span><span class="sxs-lookup"><span data-stu-id="25f96-116">To execute a SET WITNESS statement, the database mirroring session must already be started (between the partners), and the STATE of the endpoint of the witness must be set to STARTED.</span></span>  
  
     <span data-ttu-id="25f96-117">Para saber se uma instância do servidor testemunha tem seu ponto de extremidade do espelhamento de banco de dados e conhecer sua função e estado, nessa instância, use a seguinte instrução Transact-SQL:</span><span class="sxs-lookup"><span data-stu-id="25f96-117">To learn whether the witness server instance has its database mirroring endpoint and to learn its role and state, on that instance, use the following Transact-SQL statement:</span></span>  
  
    ```  
    SELECT role_desc, state_desc FROM sys.database_mirroring_endpoints  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="25f96-118">Se um ponto de extremidade do espelhamento de banco de dados já existir e estiver em uso, recomendamos que você use esse ponto de extremidade para cada sessão na instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="25f96-118">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint for every session on the server instance.</span></span> <span data-ttu-id="25f96-119">Descartando um ponto de extremidade em uso atrapalha o funcionamento das conexões das sessões existentes.</span><span class="sxs-lookup"><span data-stu-id="25f96-119">Dropping an in-use endpoint disrupts the connections of the existing sessions.</span></span> <span data-ttu-id="25f96-120">Se uma testemunha foi definida para uma sessão, descartar o ponto de extremidade do espelhamento de banco de dados poderá fazer com que o servidor principal daquela sessão perca quorum; se isso acontecer, o banco de dados será colocado offline e seus usuários serão desconectados.</span><span class="sxs-lookup"><span data-stu-id="25f96-120">If a witness has been set for a session, dropping the database mirroring endpoint can cause the principal server of that session to lose quorum; if that occurs, the database is taken offline and its users are disconnected.</span></span> <span data-ttu-id="25f96-121">Para obter mais informações, confira [Quorum: Como uma testemunha afeta a disponibilidade do banco de dados &#40;Espelhamento de Banco de Dados&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="25f96-121">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="25f96-122">Se a testemunha não tiver um ponto de extremidade, veja [Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;SQL Server&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="25f96-122">If the witness lacks an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
2.  <span data-ttu-id="25f96-123">Se as instâncias do parceiro estiverem sendo executadas em contas de usuário de domínio diferentes, crie um logon para cada uma das diferentes contas no banco de dados mestre de cada instância.</span><span class="sxs-lookup"><span data-stu-id="25f96-123">If the partner instances are running under different domain user accounts, create a login for the different accounts in the master database of each instance.</span></span> <span data-ttu-id="25f96-124">Para obter mais informações, consulte [Permitir o acesso à rede a um ponto de extremidade de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="25f96-124">For more information, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
3.  <span data-ttu-id="25f96-125">Conecte-se ao servidor principal e emita a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="25f96-125">Connect to the principal server and issue the following statement:</span></span>  
  
     <span data-ttu-id="25f96-126">ALTER DATABASE *<database_name>* definir testemunha **=** _<server_network_address>_</span><span class="sxs-lookup"><span data-stu-id="25f96-126">ALTER DATABASE *<database_name>* SET WITNESS **=** _<server_network_address>_</span></span>  
  
     <span data-ttu-id="25f96-127">em que *<database_name>* é o nome do banco de dados a ser espelhado (esse nome é o mesmo em ambos os parceiros), e *<server_network_address>* é o endereço de rede de servidor da instância de servidor testemunha.</span><span class="sxs-lookup"><span data-stu-id="25f96-127">where *<database_name>* is the name of the database to be mirrored (this name is the same on both partners), and *<server_network_address>* is the server network address of the witness server instance.</span></span>  
  
     <span data-ttu-id="25f96-128">A sintaxe para um endereço de rede do servidor é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="25f96-128">The syntax for a server network address is as follows:</span></span>  
  
     <span data-ttu-id="25f96-129">TCP **://** \<_system-address> _**:**\<*port>\*</span><span class="sxs-lookup"><span data-stu-id="25f96-129">TCP **://**\<_system-address>_**:**\<*port>\*</span></span>  
  
     <span data-ttu-id="25f96-130">em que \<*system-address>\* é uma cadeia de caracteres que identifica sem ambiguidade o sistema de computador de destino e \<*port>\* é o número da porta usado pelo ponto de extremidade de espelhamento da instância do servidor parceiro.</span><span class="sxs-lookup"><span data-stu-id="25f96-130">where \<*system-address>\* is a string that unambiguously identifies the destination computer system, and \<*port>\* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="25f96-131">Para obter mais informações, consulte [Especificar um endereço de rede do servidor &#40;Espelhamento de banco de dados&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="25f96-131">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="25f96-132">Por exemplo, na instância do servidor principal, a seguinte instrução ALTER DATABASE define a testemunha.</span><span class="sxs-lookup"><span data-stu-id="25f96-132">For example, on the principal server instance, the following ALTER DATABASE statement sets the witness.</span></span> <span data-ttu-id="25f96-133">O nome do banco de dados é **AdventureWorks**, o endereço do sistema é DBSERVER3 (o nome do sistema testemunha) e a porta usada pelo ponto de extremidade de espelhamento do banco de dados da testemunha é `7022`:</span><span class="sxs-lookup"><span data-stu-id="25f96-133">The database name is **AdventureWorks**, the system address is DBSERVER3-the name of the witness system, and the port used by the database mirroring endpoint of the witness is `7022`:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
      SET WITNESS = 'TCP://DBSERVER3:7022'  
    ```  
  
## <a name="example"></a><span data-ttu-id="25f96-134">Exemplo</span><span class="sxs-lookup"><span data-stu-id="25f96-134">Example</span></span>  
 <span data-ttu-id="25f96-135">O exemplo a seguir estabelece uma testemunha do espelhamento de dados.</span><span class="sxs-lookup"><span data-stu-id="25f96-135">The following example establishes a data mirroring witness.</span></span> <span data-ttu-id="25f96-136">Na instância do servidor testemunha (instância padrão em `WITNESSHOST4`):</span><span class="sxs-lookup"><span data-stu-id="25f96-136">On the witness server instance (default instance on `WITNESSHOST4`):</span></span>  
  
1.  <span data-ttu-id="25f96-137">Crie um ponto de extremidade para essa instância do servidor para a função WITNESS usando apenas a porta `7022`.</span><span class="sxs-lookup"><span data-stu-id="25f96-137">Create an endpoint for this server instance for the WITNESS role only using port `7022`.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=WITNESS)  
    GO  
    ```  
  
2.  <span data-ttu-id="25f96-138">Crie um logon para conta de usuário de domínio de instâncias de parceiro, se diferente; por exemplo, suponha que a testemunha está sendo executada como `SOMEDOMAIN\witnessuser`, mas os parceiros estão sendo executados como `MYDOMAIN\dbousername`.</span><span class="sxs-lookup"><span data-stu-id="25f96-138">Create a login for domain user account of partner instances, if different; for example, assume that the witness is running as `SOMEDOMAIN\witnessuser`, but the partners are running as `MYDOMAIN\dbousername`.</span></span> <span data-ttu-id="25f96-139">Crie um logon para os parceiros, como segue:</span><span class="sxs-lookup"><span data-stu-id="25f96-139">Create a login for the partners, as follows:</span></span>  
  
    ```  
    --Create a login for the partner server instances,  
    --which are both running as MYDOMAIN\dbousername:  
    USE master ;  
    GO  
    CREATE LOGIN [MYDOMAIN\dbousername] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account   
    --of partners  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [MYDOMAIN\dbousername];  
    GO  
    ```  
  
3.  <span data-ttu-id="25f96-140">Em cada uma das instâncias de servidor de parceiro, crie um logon para a instância do servidor testemunha:</span><span class="sxs-lookup"><span data-stu-id="25f96-140">On each of the partner server instances, create a login for the witness server instance:</span></span>  
  
    ```  
    --Create a login for the witness server instance,  
    --which is running as SOMEDOMAIN\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [SOMEDOMAIN\witnessuser] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account   
    --of partners  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [SOMEDOMAIN\witnessuser];  
    GO  
    ```  
  
4.  <span data-ttu-id="25f96-141">No servidor principal, defina a testemunha (que está em `WITNESSHOST4`):</span><span class="sxs-lookup"><span data-stu-id="25f96-141">On the principal server, set the witness (which is on `WITNESSHOST4`):</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET WITNESS =   
        'TCP://WITNESSHOST4:7022'  
    GO  
    ```  
  
> [!NOTE]  
>  <span data-ttu-id="25f96-142">O endereço de rede do servidor indica a instância do servidor de destino pelo número da porta que mapeia para o ponto de extremidade do espelhamento da instância.</span><span class="sxs-lookup"><span data-stu-id="25f96-142">The server network address indicates the target server instance by the port number, which maps to the mirroring endpoint of the instance.</span></span>  
  
 <span data-ttu-id="25f96-143">Para obter um exemplo completo mostrando a configuração da segurança, o preparo do banco de dados espelho, a configuração de parceiros e a adição de uma testemunha, consulte [Configurando o espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="25f96-143">For a complete example showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="25f96-144">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="25f96-144">See Also</span></span>  
 <span data-ttu-id="25f96-145">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="25f96-145">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="25f96-146">[Permitir o acesso à rede a um ponto de extremidade de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="25f96-146">[Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span></span>  
 <span data-ttu-id="25f96-147">[Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="25f96-147">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="25f96-148">[Estabelecer uma sessão de espelhamento de banco de dados com a Autenticação do Windows &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="25f96-148">[Establish a Database Mirroring Session Using Windows Authentication &#40;Transact-SQL&#41;](database-mirroring-establish-session-windows-authentication.md) </span></span>  
 <span data-ttu-id="25f96-149">[Remover a testemunha de uma sessão de espelhamento de banco de dados &#40;SQL Server&#41;](remove-the-witness-from-a-database-mirroring-session-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="25f96-149">[Remove the Witness from a Database Mirroring Session &#40;SQL Server&#41;](remove-the-witness-from-a-database-mirroring-session-sql-server.md) </span></span>  
 [<span data-ttu-id="25f96-150">Testemunha de espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="25f96-150">Database Mirroring Witness</span></span>](database-mirroring-witness.md)  
  
  
