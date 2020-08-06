---
title: Estabelecer uma sessão de espelhamento de banco de dados usando a autenticação do Windows (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 05/24/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Windows authentication [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 143c68a5-589f-4e7f-be59-02707e1a430a
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f3088333fbfd4babd209df07f8880c838ce626d2
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570232"
---
# <a name="establish-a-database-mirroring-session-using-windows-authentication-transact-sql"></a><span data-ttu-id="c1fed-102">Estabelecer uma sessão de espelhamento de banco de dados com a Autenticação do Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="c1fed-102">Establish a Database Mirroring Session Using Windows Authentication (Transact-SQL)</span></span>
    
> [!NOTE]  
>  [!INCLUDE[ssNoteDepFutureAvoid](../../includes/ssnotedepfutureavoid-md.md)] <span data-ttu-id="c1fed-103">Em vez disso, use [!INCLUDE[ssHADR](../../includes/sshadr-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1fed-103">Use [!INCLUDE[ssHADR](../../includes/sshadr-md.md)] instead.</span></span>  
  
 <span data-ttu-id="c1fed-104">Depois que o banco de dados espelho estiver preparado (consulte [Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)), você poderá estabelecer uma sessão de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c1fed-104">After the mirror database is prepared (see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)), you can establish a database mirroring session.</span></span> <span data-ttu-id="c1fed-105">As instâncias do servidor principal, espelho e testemunha devem ser instâncias de servidor separadas que deveriam estar em sistemas host separados.</span><span class="sxs-lookup"><span data-stu-id="c1fed-105">The principal, mirror, and witness server instances must be separate server instances, which should be on separate host systems.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="c1fed-106">Recomendamos que você configure um espelhamento de banco de dados em períodos de pouca atividade porque a configuração de espelhamento pode comprometer o desempenho.</span><span class="sxs-lookup"><span data-stu-id="c1fed-106">We recommend that you configure database mirroring during off-peak hours because configuring mirroring can impact performance.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1fed-107">Uma determinada instância do servidor pode participar de várias sessões de espelhamento de banco de dados simultâneas com os mesmos parceiros ou diferentes.</span><span class="sxs-lookup"><span data-stu-id="c1fed-107">A given server instance can participate in multiple concurrent database mirroring sessions with the same or different partners.</span></span> <span data-ttu-id="c1fed-108">Uma instância do servidor pode ser um parceiro em algumas sessões e uma testemunha em outras sessões.</span><span class="sxs-lookup"><span data-stu-id="c1fed-108">A server instance can be a partner in some sessions and a witness in other sessions.</span></span> <span data-ttu-id="c1fed-109">A instância do servidor espelho deve estar executando a mesma edição do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] como a instância do servidor principal.</span><span class="sxs-lookup"><span data-stu-id="c1fed-109">The mirror server instance must be running the same edition of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] as the principal server instance.</span></span> <span data-ttu-id="c1fed-110">O espelhamento de banco de dados não está disponível em todas as edições do [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="c1fed-110">Database mirroring is not available in every edition of [!INCLUDE[msCoName](../../includes/msconame-md.md)][!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="c1fed-111">Para obter uma lista de recursos com suporte nas edições do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], consulte [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-111">For a list of features that are supported by the editions of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Features Supported by the Editions of SQL Server 2014](../../getting-started/features-supported-by-the-editions-of-sql-server-2014.md).</span></span> <span data-ttu-id="c1fed-112">Além disso, é altamente recomendável que elas sejam executadas em sistemas comparáveis que possam controlar cargas de trabalho idênticas.</span><span class="sxs-lookup"><span data-stu-id="c1fed-112">Also, we strongly recommend that they run on comparable systems that can handle identical workloads.</span></span>  
  
### <a name="to-establish-a-database-mirroring-session"></a><span data-ttu-id="c1fed-113">Para estabelecer uma sessão de espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="c1fed-113">To establish a database mirroring session</span></span>  
  
1.  <span data-ttu-id="c1fed-114">Crie o banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="c1fed-114">Create the mirror database.</span></span> <span data-ttu-id="c1fed-115">Para obter mais informações, veja [Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-115">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
2.  <span data-ttu-id="c1fed-116">Defina a segurança em cada instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="c1fed-116">Set up security on each server instance.</span></span>  
  
     <span data-ttu-id="c1fed-117">Cada instância do servidor em uma sessão de espelhamento de banco de dados exige um ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c1fed-117">Each server instance in a database mirroring session requires a database mirroring endpoint.</span></span> <span data-ttu-id="c1fed-118">Se o ponto de extremidade não existir, você deve criá-lo.</span><span class="sxs-lookup"><span data-stu-id="c1fed-118">If the endpoint does not exist, you must create it.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="c1fed-119">A forma de autenticação usada para o espelhamento de banco de dados por uma instância do servidor é uma propriedade do ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c1fed-119">The form of authentication used for database mirroring by a server instance is a property of its database mirroring endpoint.</span></span> <span data-ttu-id="c1fed-120">Dois tipos de segurança de transporte estão disponíveis para o espelhamento de banco de dados: Autenticação do Windows ou autenticação baseada em certificado.</span><span class="sxs-lookup"><span data-stu-id="c1fed-120">Two types of transport security are available for database mirroring: Windows Authentication or certificate-based authentication.</span></span> <span data-ttu-id="c1fed-121">Para obter mais informações, consulte [segurança de transporte para espelhamento de banco de dados e Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-121">For more information, see [Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md).</span></span>  
  
     <span data-ttu-id="c1fed-122">Em cada servidor parceiro, assegure que existe um ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c1fed-122">On each partner server, ensure that an endpoint exists for database mirroring.</span></span> <span data-ttu-id="c1fed-123">Independentemente do número de sessões de espelhamento a dar suporte, a instância do servidor só pode ter um ponto de extremidade de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c1fed-123">Regardless of the number of mirroring sessions to be supported, the server instance can have only one database mirroring endpoint.</span></span> <span data-ttu-id="c1fed-124">Se você pretende usar essa instância do servidor exclusivamente para parceiros em sessões de espelhamento de banco de dados, você poderá atribuir a função de parceiro ao ponto de extremidade (ROLE **=** PARTNER).</span><span class="sxs-lookup"><span data-stu-id="c1fed-124">If you intend to use this server instance exclusively for partners in database mirroring sessions, you can assign the role of partner to the endpoint (ROLE**=** PARTNER).</span></span> <span data-ttu-id="c1fed-125">Se você também pretende usar essa instância do servidor exclusivamente para testemunhas em sessões de espelhamento de banco de dados, você poderá definir o papel de parceiro ao ponto de extremidade como ALL.</span><span class="sxs-lookup"><span data-stu-id="c1fed-125">If you intend also to use this server for the witness in other database mirroring sessions, assign the role of the endpoint as ALL.</span></span>  
  
     <span data-ttu-id="c1fed-126">Para executar uma instrução SET PARTNER, o STATE dos pontos de extremidade de ambos os parceiros deve ser definido como STARTED.</span><span class="sxs-lookup"><span data-stu-id="c1fed-126">To execute a SET PARTNER statement, the STATE of the endpoints of both partners must be set to STARTED.</span></span>  
  
     <span data-ttu-id="c1fed-127">Para saber se uma instância do servidor tem um ponto de extremidade de espelhamento de banco de dados e saber sua função e estado, nessa instância, use a seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="c1fed-127">To learn whether a server instance has a database mirroring endpoint and to learn its role and state, on that instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```  
    SELECT role_desc, state_desc FROM sys.database_mirroring_endpoints  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c1fed-128">Não reconfigure um ponto de extremidade de espelhamento de banco de dados em uso.</span><span class="sxs-lookup"><span data-stu-id="c1fed-128">Do not reconfigure an in-use database mirroring endpoint.</span></span> <span data-ttu-id="c1fed-129">Se um ponto de extremidade do espelhamento de banco de dados já existir e estiver em uso, recomendamos que você use esse ponto de extremidade para cada sessão na instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="c1fed-129">If a database mirroring endpoint exists and is already in use, we recommend that you use that endpoint for every session on the server instance.</span></span> <span data-ttu-id="c1fed-130">Cancelando um ponto de extremidade em uso pode fazer o ponto de extremidade reinicializar, interrompendo as conexões das sessões existentes, que podem aparecer como um erro às outras instâncias do servidor.</span><span class="sxs-lookup"><span data-stu-id="c1fed-130">Dropping an in-use endpoint can cause the endpoint to restart, disrupting the connections of the existing sessions, which can appear to be an error to the other server instances.</span></span> <span data-ttu-id="c1fed-131">Isso é particularmente importante em modo de alta segurança com failover automático no qual a reconfiguração de um ponto de extremidade em um parceiro poderia provocar um failover.</span><span class="sxs-lookup"><span data-stu-id="c1fed-131">This is particularly important in high-safety mode with automatic failover, in which reconfiguring the endpoint on a partner could cause a failover to occur.</span></span> <span data-ttu-id="c1fed-132">Além disso, se uma testemunha foi definida para uma sessão, cancelar o ponto de extremidade de espelhamento de banco de dados poderá fazer com que o servidor principal daquela sessão perca quorum; se isso acontecer, o banco de dados será colocado offline e seus usuários serão desconectados.</span><span class="sxs-lookup"><span data-stu-id="c1fed-132">Also, if a witness has been set for a session, dropping the database mirroring endpoint can cause the principal server of that session to lose quorum; if that occurs, the database is taken offline and its users are disconnected.</span></span> <span data-ttu-id="c1fed-133">Para obter mais informações, confira [Quorum: Como uma testemunha afeta a disponibilidade do banco de dados &#40;Espelhamento de Banco de Dados&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-133">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="c1fed-134">Se o parceiro não tiver um ponto de extremidade, consulte [Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-134">If either partner lacks an endpoint, see [Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md).</span></span>  
  
3.  <span data-ttu-id="c1fed-135">Se as instâncias de servidor estiverem sendo executadas em contas do usuário de domínio diferentes, cada uma exigirá um logon no banco de dados **mestre** dos outros.</span><span class="sxs-lookup"><span data-stu-id="c1fed-135">If server instances are running under different domain user accounts, each requires a login in the **master** database of the others.</span></span> <span data-ttu-id="c1fed-136">Se o logon não existir, você deve criá-lo.</span><span class="sxs-lookup"><span data-stu-id="c1fed-136">If the login does not exist, you must create it.</span></span> <span data-ttu-id="c1fed-137">Para obter mais informações, consulte [Permitir o acesso à rede a um ponto de extremidade de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-137">For more information, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
4.  <span data-ttu-id="c1fed-138">Para definir o servidor principal como parceiro no banco de dados espelho, conecte-se ao servidor espelho e emita a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="c1fed-138">To set the principal server as partner on the mirror database, connect to the mirror server, and issue the following statement:</span></span>  
  
     <span data-ttu-id="c1fed-139">ALTER DATABASE *<database_name>* definir<do parceiro **=** _server_network_address_></span><span class="sxs-lookup"><span data-stu-id="c1fed-139">ALTER DATABASE *<database_name>* SET PARTNER **=**_<server_network_address>_</span></span>  
  
     <span data-ttu-id="c1fed-140">em que *<database_name>* é o nome do banco de dados a ser espelhado (esse nome é o mesmo em ambos os parceiros) e *<server_network_address>* é o endereço de rede de servidor do servidor principal.</span><span class="sxs-lookup"><span data-stu-id="c1fed-140">where *<database_name>* is the name of the database to be mirrored (this name is the same on both partners), and *<server_network_address>* is the server network address of the principal server.</span></span>  
  
     <span data-ttu-id="c1fed-141">A sintaxe para um endereço de rede do servidor é a seguinte:</span><span class="sxs-lookup"><span data-stu-id="c1fed-141">The syntax for a server network address is as follows:</span></span>  
  
     <span data-ttu-id="c1fed-142">TCP<strong>://</strong> \<*system-address> \*<strong>:</strong> \<*port> \*</span><span class="sxs-lookup"><span data-stu-id="c1fed-142">TCP<strong>://</strong>\<*system-address>*<strong>:</strong>\<*port>*</span></span>  
  
     <span data-ttu-id="c1fed-143">em que \<*system-address>\* é uma cadeia de caracteres que identifica sem ambiguidade o sistema de computador de destino e \<*port>\* é o número da porta usado pelo ponto de extremidade de espelhamento da instância do servidor parceiro.</span><span class="sxs-lookup"><span data-stu-id="c1fed-143">where \<*system-address>\* is a string that unambiguously identifies the destination computer system, and \<*port>\* is the port number used by the mirroring endpoint of the partner server instance.</span></span> <span data-ttu-id="c1fed-144">Para obter mais informações, consulte [Especificar um endereço de rede do servidor &#40;Espelhamento de banco de dados&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-144">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
     <span data-ttu-id="c1fed-145">Por exemplo, na instância do servidor espelho, a seguinte instrução ALTER DATABASE define o parceiro como a instância do servidor principal original.</span><span class="sxs-lookup"><span data-stu-id="c1fed-145">For example, on the mirror server instance, the following ALTER DATABASE statement sets the partner as the original principal server instance.</span></span> <span data-ttu-id="c1fed-146">O nome do banco de dados é **AdventureWorks**, o endereço do sistema é DBSERVER1 – o nome de sistema do parceiro – e a porta usada pelo ponto de extremidade de espelhamento de banco de dados do parceiro é 7022:</span><span class="sxs-lookup"><span data-stu-id="c1fed-146">The database name is **AdventureWorks**, the system address is DBSERVER1-the name of the partner's system-and the port used by the partner's database mirroring endpoint is 7022:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
       SET PARTNER = 'TCP://DBSERVER1:7022'  
    ```  
  
     <span data-ttu-id="c1fed-147">Essa instrução prepara o servidor espelho para formar uma sessão quando é contatado pelo servidor principal.</span><span class="sxs-lookup"><span data-stu-id="c1fed-147">This statement prepares the mirror server to form a session when it is contacted by the principal server.</span></span>  
  
5.  <span data-ttu-id="c1fed-148">Para definir o servidor espelho como parceiro no banco de dados principal, conecte-se ao servidor principal e emita a seguinte instrução:</span><span class="sxs-lookup"><span data-stu-id="c1fed-148">To set the mirror server as partner on the principal database, connect to the principal server, and issue the following statement:</span></span>  
  
     <span data-ttu-id="c1fed-149">ALTER DATABASE *<database_name>* definir<do parceiro **=** _server_network_address_></span><span class="sxs-lookup"><span data-stu-id="c1fed-149">ALTER DATABASE *<database_name>* SET PARTNER **=**_<server_network_address>_</span></span>  
  
     <span data-ttu-id="c1fed-150">Para obter mais informações, consulte a etapa 4.</span><span class="sxs-lookup"><span data-stu-id="c1fed-150">For more information, see step 4.</span></span>  
  
     <span data-ttu-id="c1fed-151">Por exemplo, na instância do servidor principal, a seguinte instrução ALTER DATABASE define o parceiro como a instância do servidor espelho original.</span><span class="sxs-lookup"><span data-stu-id="c1fed-151">For example, on the principal server instance, the following ALTER DATABASE statement sets the partner as the original mirror server instance.</span></span> <span data-ttu-id="c1fed-152">O nome do banco de dados é **AdventureWorks**, o endereço do sistema é DBSERVER2 – o nome de sistema do parceiro – e a porta usada pelo ponto de extremidade de espelhamento de banco de dados do parceiro é 7025:</span><span class="sxs-lookup"><span data-stu-id="c1fed-152">The database name is **AdventureWorks**, the system address is DBSERVER2-the name of the partner's system-and the port used by the partner's database mirroring endpoint is 7025:</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks SET PARTNER = 'TCP://DBSERVER2:7022'  
    ```  
  
     <span data-ttu-id="c1fed-153">Inserir essa instrução no servidor principal inicia a sessão de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c1fed-153">Entering this statement on the principal server begins the database mirroring session.</span></span>  
  
6.  <span data-ttu-id="c1fed-154">Por padrão, uma sessão é definida como segurança de transação completa (SAFETY é definido como FULL), que inicia a sessão no modo síncrono de segurança alta, sem failover automático.</span><span class="sxs-lookup"><span data-stu-id="c1fed-154">By default a session is set to full transaction safety (SAFETY is set to FULL), which starts the session in synchronous, high-safety mode without automatic failover.</span></span> <span data-ttu-id="c1fed-155">Você pode reconfigurar a sessão para ser executada em modo de segurança alta com failover automático ou em modo assíncrono de alto desempenho, como se segue:</span><span class="sxs-lookup"><span data-stu-id="c1fed-155">You can reconfigure the session to run in high-safety mode with automatic failover or in asynchronous, high-performance mode, as follows:</span></span>  
  
    -   <span data-ttu-id="c1fed-156">**Modo de segurança alta com failover automático**</span><span class="sxs-lookup"><span data-stu-id="c1fed-156">**High-safety mode with automatic failover**</span></span>  
  
         <span data-ttu-id="c1fed-157">Se você quiser que uma sessão de modo de segurança alta dê suporte a failover automático, acrescente uma instância do servidor testemunha.</span><span class="sxs-lookup"><span data-stu-id="c1fed-157">If you want a high-safety mode session to support automatic failover, add a witness server instance.</span></span> <span data-ttu-id="c1fed-158">Para obter mais informações, consulte [Adicionar uma testemunha de espelhamento de banco de dados usando a Autenticação do Windows &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-158">For more information, see [Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span></span>  
  
    -   <span data-ttu-id="c1fed-159">**Modo de alto desempenho**</span><span class="sxs-lookup"><span data-stu-id="c1fed-159">**High-performance mode**</span></span>  
  
         <span data-ttu-id="c1fed-160">Alternativamente, se você não quiser failover automático e preferir enfatizar o desempenho em vez da disponibilidade, desative a segurança de transação.</span><span class="sxs-lookup"><span data-stu-id="c1fed-160">Alternatively, if you do not want automatic failover and you prefer to emphasize performance over availability, turn off transaction safety.</span></span> <span data-ttu-id="c1fed-161">Para obter mais informações, consulte [Alterar a segurança da transação em uma sessão de espelhamento de banco de dados &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-161">For more information, see [Change Transaction Safety in a Database Mirroring Session &#40;Transact-SQL&#41;](change-transaction-safety-in-a-database-mirroring-session-transact-sql.md).</span></span>  
  
        > [!NOTE]  
        >  <span data-ttu-id="c1fed-162">Em modo de alto desempenho, WITNESS deverá ser definido como OFF.</span><span class="sxs-lookup"><span data-stu-id="c1fed-162">In high-performance mode, WITNESS should be set to OFF.</span></span> <span data-ttu-id="c1fed-163">Para obter mais informações, confira [Quorum: Como uma testemunha afeta a disponibilidade do banco de dados &#40;Espelhamento de Banco de Dados&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-163">For more information, see [Quorum: How a Witness Affects Database Availability &#40;Database Mirroring&#41;](quorum-how-a-witness-affects-database-availability-database-mirroring.md).</span></span>  
  
## <a name="example"></a><span data-ttu-id="c1fed-164">Exemplo</span><span class="sxs-lookup"><span data-stu-id="c1fed-164">Example</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1fed-165">O exemplo seguinte estabelece uma sessão de espelhamento de banco de dados entre parceiros para um banco de dados espelho existente.</span><span class="sxs-lookup"><span data-stu-id="c1fed-165">The following example establishes a database mirroring session between partners for an existing mirror database.</span></span> <span data-ttu-id="c1fed-166">Para obter informações sobre como criar um banco de dados espelho, consulte [Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-166">For information on creating a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md)=.</span></span>  
  
 <span data-ttu-id="c1fed-167">O exemplo mostra as etapas básicas para criar uma sessão de espelhamento de banco de dados sem uma testemunha.</span><span class="sxs-lookup"><span data-stu-id="c1fed-167">The example shows the basic steps for creating a database mirroring session without a witness.</span></span> <span data-ttu-id="c1fed-168">Os dois parceiros são as instâncias de servidor padrão em dois sistemas de computador (PARTNERHOST1 e PARTNERHOST5).</span><span class="sxs-lookup"><span data-stu-id="c1fed-168">The two partners are the default server instances on two computer systems (PARTNERHOST1 and PARTNERHOST5).</span></span> <span data-ttu-id="c1fed-169">As duas instâncias do parceiro executam a mesma conta do usuário no domínio Windows (MYDOMAIN\dbousername).</span><span class="sxs-lookup"><span data-stu-id="c1fed-169">The two partner instances run the same Windows domain user account (MYDOMAIN\dbousername).</span></span>  
  
1.  <span data-ttu-id="c1fed-170">Na instância do servidor principal (instância padrão em PARTNERHOST1), crie um ponto de extremidade dê suporte a todas as funções que usam a porta 7022:</span><span class="sxs-lookup"><span data-stu-id="c1fed-170">On the principal server instance (default instance on PARTNERHOST1), create an endpoint that supports all roles using port 7022:</span></span>  
  
    ```  
    --create an endpoint for this instance  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="c1fed-171">Para encontrar um exemplo de como configurar um logon, consulte [Permitir o acesso à rede a um ponto de extremidade de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-171">For an example of how to setup a login, see [Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md).</span></span>  
  
2.  <span data-ttu-id="c1fed-172">Na instância do servidor espelho (instância padrão em PARTNERHOST5), crie um ponto de extremidade que dê suporte a todas as funções que usam a porta 7022:</span><span class="sxs-lookup"><span data-stu-id="c1fed-172">On the mirror server instance (default instance on PARTNERHOST5), create an endpoint that supports all roles using port 7022:</span></span>  
  
    ```  
    --create an endpoint for this instance  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    ```  
  
3.  <span data-ttu-id="c1fed-173">Na instância do servidor principal (em PARTNERHOST1), faça o backup do banco de dados:</span><span class="sxs-lookup"><span data-stu-id="c1fed-173">On the principal server instance (on PARTNERHOST1), back up the database:</span></span>  
  
    ```  
    BACKUP DATABASE AdventureWorks   
        TO DISK = 'C:\AdvWorks_dbmirror.bak'   
        WITH FORMAT  
    GO  
    ```  
  
4.  <span data-ttu-id="c1fed-174">Na instância do servidor espelho (em `PARTNERHOST5`), restaure o banco de dados:</span><span class="sxs-lookup"><span data-stu-id="c1fed-174">On the mirror server instance (on `PARTNERHOST5`), restore the database:</span></span>  
  
    ```  
    RESTORE DATABASE AdventureWorks   
        FROM DISK = 'Z:\AdvWorks_dbmirror.bak'   
        WITH NORECOVERY  
    GO  
    ```  
  
5.  <span data-ttu-id="c1fed-175">Depois que você criar o backup de banco de dados completo, você deve criar um backup do log no banco de dados principal.</span><span class="sxs-lookup"><span data-stu-id="c1fed-175">After you create the full database backup, you must create a log backup on the principal database.</span></span> <span data-ttu-id="c1fed-176">Por exemplo, a seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] faz o backup do log ao mesmo arquivo usado pelo backup de banco de dados precedente:</span><span class="sxs-lookup"><span data-stu-id="c1fed-176">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement backs up the log to the same file used by the preceding database backup:</span></span>  
  
    ```  
    BACKUP LOG AdventureWorks   
        TO DISK = 'C:\AdventureWorks.bak'   
    GO  
    ```  
  
6.  <span data-ttu-id="c1fed-177">Antes de poder iniciar o espelhamento, é necessário aplicar o backup de log exigido (e qualquer backup de log subsequente).</span><span class="sxs-lookup"><span data-stu-id="c1fed-177">Before you can start mirroring, you must apply the required log backup (and any subsequent log backups).</span></span>  
  
     <span data-ttu-id="c1fed-178">Por exemplo, a seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)] restaura o primeiro log de C:\AdventureWorks.bak:</span><span class="sxs-lookup"><span data-stu-id="c1fed-178">For example, the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement restores the first log from C:\AdventureWorks.bak:</span></span>  
  
    ```  
    RESTORE LOG AdventureWorks   
        FROM DISK = 'C:\ AdventureWorks.bak'   
        WITH FILE=1, NORECOVERY  
    GO  
    ```  
  
7.  <span data-ttu-id="c1fed-179">Na instância do servidor espelho, defina a instância do servidor em PARTNERHOST1 como o parceiro (fazendo dele o servidor principal inicial):</span><span class="sxs-lookup"><span data-stu-id="c1fed-179">On the mirror server instance, set the server instance on PARTNERHOST1 as the partner (making it the initial principal server):</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
        SET PARTNER =   
        'TCP://PARTNERHOST1:7022'  
    GO  
    ```  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="c1fed-180">Por padrão, uma sessão de espelhamento de banco de dados é executada modo síncrono, o que depende de ter uma transação de segurança completa (SAFETY é definido como FULL).</span><span class="sxs-lookup"><span data-stu-id="c1fed-180">default, a database mirroring session runs in synchronous mode, which depends on having full transaction safety (SAFETY is set to FULL).</span></span> <span data-ttu-id="c1fed-181">Para fazer com que uma sessão seja executada em modo assíncrono, de alto desempenho, defina SAFETY como OFF.</span><span class="sxs-lookup"><span data-stu-id="c1fed-181">To cause a session to run in asynchronous, high-performance mode, set SAFETY to OFF.</span></span> <span data-ttu-id="c1fed-182">Para obter mais informações, consulte [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-182">For more information, see [Database Mirroring Operating Modes](database-mirroring-operating-modes.md).</span></span>  
  
8.  <span data-ttu-id="c1fed-183">Na instância do servidor principal, defina a instância do servidor em `PARTNERHOST5` como o parceiro (fazendo dele o servidor espelho inicial):</span><span class="sxs-lookup"><span data-stu-id="c1fed-183">On the principal server instance, set the server instance on `PARTNERHOST5` as the partner (making it the initial mirror server):</span></span>  
  
    ```  
    USE master;  
    GO  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://PARTNERHOST5:7022'  
    GO  
    ```  
  
9. <span data-ttu-id="c1fed-184">Opcionalmente, se você pretender usar modo de segurança alta com failover automático, configure a instância do servidor testemunha.</span><span class="sxs-lookup"><span data-stu-id="c1fed-184">Optionally, if you intend to use high-safety mode with automatic failover, set up the witness server instance.</span></span> <span data-ttu-id="c1fed-185">Para obter mais informações, consulte [Adicionar uma testemunha de espelhamento de banco de dados usando a Autenticação do Windows &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-185">For more information, see [Add a Database Mirroring Witness Using Windows Authentication &#40;Transact-SQL&#41;](add-a-database-mirroring-witness-using-windows-authentication-transact-sql.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="c1fed-186">Para obter um exemplo completo mostrando a configuração da segurança, o preparo do banco de dados espelho, a configuração de parceiros e a adição de uma testemunha, consulte [Configurando o espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="c1fed-186">For a complete example showing security setup, preparing the mirror database, setting up the partners, and adding a witness, see [Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c1fed-187">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c1fed-187">See Also</span></span>  
 <span data-ttu-id="c1fed-188">[Configurando o espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c1fed-188">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="c1fed-189">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="c1fed-189">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="c1fed-190">[Permitir o acesso à rede a um ponto de extremidade de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span><span class="sxs-lookup"><span data-stu-id="c1fed-190">[Allow Network Access to a Database Mirroring Endpoint Using Windows Authentication &#40;SQL Server&#41;](../database-mirroring-allow-network-access-windows-authentication.md) </span></span>  
 <span data-ttu-id="c1fed-191">[Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c1fed-191">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="c1fed-192">[Criar um ponto de extremidade de espelhamento de banco de dados para a Autenticação do Windows &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="c1fed-192">[Create a Database Mirroring Endpoint for Windows Authentication &#40;Transact-SQL&#41;](create-a-database-mirroring-endpoint-for-windows-authentication-transact-sql.md) </span></span>  
 <span data-ttu-id="c1fed-193">[Espelhamento de banco de dados e envio de logs &#40;SQL Server&#41;](database-mirroring-and-log-shipping-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c1fed-193">[Database Mirroring and Log Shipping &#40;SQL Server&#41;](database-mirroring-and-log-shipping-sql-server.md) </span></span>  
 <span data-ttu-id="c1fed-194">[Espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c1fed-194">[Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="c1fed-195">[Espelhamento e replicação de banco de dados &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c1fed-195">[Database Mirroring and Replication &#40;SQL Server&#41;](database-mirroring-and-replication-sql-server.md) </span></span>  
 <span data-ttu-id="c1fed-196">[Configurando o espelhamento de banco de dados &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="c1fed-196">[Setting Up Database Mirroring &#40;SQL Server&#41;](database-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="c1fed-197">[Especificar um endereço de rede do servidor &#40;espelhamento de banco de dados&#41;](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="c1fed-197">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 [<span data-ttu-id="c1fed-198">Modos de operação de espelhamento de banco de dados</span><span class="sxs-lookup"><span data-stu-id="c1fed-198">Database Mirroring Operating Modes</span></span>](database-mirroring-operating-modes.md)  
  
  
