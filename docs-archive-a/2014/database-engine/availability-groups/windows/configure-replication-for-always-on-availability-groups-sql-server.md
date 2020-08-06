---
title: Configurar a replicação para Grupos de Disponibilidade AlwaysOn (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/14/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- Availability Groups [SQL Server], interoperability
- replication [SQL Server], AlwaysOn Availability Groups
ms.assetid: 4e001426-5ae0-4876-85ef-088d6e3fb61c
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: 916458d2d6b8fbba81940257ee85ffe014d1f12e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679531"
---
# <a name="configure-replication-for-always-on-availability-groups-sql-server"></a><span data-ttu-id="7e4bf-102">Configurar a replicação para Grupos de Disponibilidade AlwaysOn (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="7e4bf-102">Configure Replication for Always On Availability Groups (SQL Server)</span></span>
  <span data-ttu-id="7e4bf-103">A configuração dos grupos de disponibilidade AlwaysOn e da replicação do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] envolve sete etapas.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-103">Configuring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] replication and AlwaysOn availability groups involves seven steps.</span></span> <span data-ttu-id="7e4bf-104">Cada etapa está descrita com mais detalhes nas seções a seguir.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-104">Each step is described in more detail in the following sections.</span></span>  

##  <a name="1-configure-the-database-publications-and-subscriptions"></a><a name="step1"></a> <span data-ttu-id="7e4bf-105">1. Configurar as publicações de banco de dados e assinaturas</span><span class="sxs-lookup"><span data-stu-id="7e4bf-105">1. Configure the Database Publications and Subscriptions</span></span>  

### <a name="configure-the-distributor"></a><span data-ttu-id="7e4bf-106">Configurar o distribuidor</span><span class="sxs-lookup"><span data-stu-id="7e4bf-106">Configure the distributor</span></span>
  
 <span data-ttu-id="7e4bf-107">O distribuidor não deve ser um host para as réplicas atuais (ou planejadas) do grupo de disponibilidade do qual o banco de dados de publicação é (ou se tornará) membro.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-107">The distributor should not be a host for any of the current (or intended) replicas of the availability group that the publishing database is (or will become) a member of.</span></span>  
  
1.  <span data-ttu-id="7e4bf-108">Configurar a distribuição no distribuidor.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-108">Configure distribution at the distributor.</span></span> <span data-ttu-id="7e4bf-109">Se estiverem sendo usados procedimentos armazenados para a configuração, execute `sp_adddistributor`.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-109">If stored procedures are being used for configuration, run `sp_adddistributor`.</span></span> <span data-ttu-id="7e4bf-110">Use o *@password* parâmetro para identificar a senha que será usada quando um Publicador remoto se conectar ao distribuidor.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-110">Use the *@password* parameter to identify the password that will be used when a remote publisher connects to the distributor.</span></span> <span data-ttu-id="7e4bf-111">A senha também será necessária em cada publicador remoto quando o distribuidor remoto for instalado.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-111">The password will also be needed at each remote publisher when the remote distributor is set up.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_adddistributor  
        @distributor = 'MyDistributor',  
        @password = '**Strong password for distributor**';  
    ```  
  
2.  <span data-ttu-id="7e4bf-112">Criar o banco de dados de distribuição no distribuidor.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-112">Create the distribution database at the distributor.</span></span> <span data-ttu-id="7e4bf-113">Se estiverem sendo usados procedimentos armazenados para a configuração, execute `sp_adddistributiondb`.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-113">If stored procedures are being used for configuration, run `sp_adddistributiondb`.</span></span>  
  
    ```  
    USE master;  
    GO  
    EXEC sys.sp_adddistributiondb  
        @database = 'distribution',  
        @security_mode = 1;  
    ```  
  
3.  <span data-ttu-id="7e4bf-114">Configurar o publicador remoto.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-114">Configure the remote publisher.</span></span> <span data-ttu-id="7e4bf-115">Se estiverem sendo usados procedimentos armazenados para configurar o distribuidor, execute `sp_adddistpublisher`.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-115">If stored procedures are being used to configure the distributor, run `sp_adddistpublisher`.</span></span> <span data-ttu-id="7e4bf-116">O *@security_mode* parâmetro é usado para determinar como o procedimento armazenado de validação do Publicador executado a partir dos agentes de replicação, conecta-se ao primário atual.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-116">The *@security_mode* parameter is used to determine how the publisher validation stored procedure that is run from the replication agents, connects to the current primary.</span></span> <span data-ttu-id="7e4bf-117">Se a autenticação do Windows definida como 1 for usada na conexão à primária atual.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-117">If set to 1 Windows authentication is used to connect to the current primary.</span></span> <span data-ttu-id="7e4bf-118">Se definido como 0, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a autenticação será usada com os *@login* valores e especificados *@password* .</span><span class="sxs-lookup"><span data-stu-id="7e4bf-118">If set to 0, [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] authentication is used with the specified *@login* and *@password* values.</span></span> <span data-ttu-id="7e4bf-119">O logon e a senha especificada devem ser válidos em cada réplica secundária para o procedimento armazenado de validação se conectar com êxito a essa réplica.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-119">The login and password specified must be valid at each secondary replica for the validation stored procedure to successfully connect to that replica.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="7e4bf-120">Se qualquer agente de replicação modificado for executado em um computador que não seja o distribuidor, o uso da autenticação do Windows para a conexão à réplica primária exigirá a configuração da autenticação Kerberos para a comunicação entre os computadores host da réplica.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-120">If any modified replication agents run on a computer other than the distributor, use of Windows authentication for the connection to the primary will require Kerberos authentication to be configured for the communication between the replica host computers.</span></span> <span data-ttu-id="7e4bf-121">O uso de um logon do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para a conexão à réplica primária atual não requer a autenticação Kerberos.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-121">Use of a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login for the connection to the current primary will not require Kerberos authentication.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_adddistpublisher  
        @publisher = 'AGPrimaryReplicaHost',  
        @distribution_db = 'distribution',  
        @working_directory = '\\MyReplShare\WorkingDir',  
        @login = 'MyPubLogin',  
        @password = '**Strong password for publisher**';  
    ```  
  
 <span data-ttu-id="7e4bf-122">Para obter mais informações, consulte [sp_adddistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistpublisher-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="7e4bf-122">For more information, see [sp_adddistpublisher &#40;Transact-SQL&#41;](/sql/relational-databases/system-stored-procedures/sp-adddistpublisher-transact-sql).</span></span>  
  
### <a name="configure-the-publisher-at-the-original-publisher"></a><span data-ttu-id="7e4bf-123">Configurar o publicador no publicador original</span><span class="sxs-lookup"><span data-stu-id="7e4bf-123">Configure the publisher at the original publisher</span></span>
  
1.  <span data-ttu-id="7e4bf-124">Configurar um distribuidor remoto.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-124">Configure remote distribution.</span></span> <span data-ttu-id="7e4bf-125">Se estiverem sendo usados procedimentos armazenados para configurar o publicador, execute `sp_adddistributor`.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-125">If stored procedures are being used to configure the publisher, run `sp_adddistributor`.</span></span> <span data-ttu-id="7e4bf-126">Especifique o mesmo valor para o *@password* que foi usado quando `sp_adddistrbutor` foi executado no distribuidor para configurar a distribuição.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-126">Specify the same value for *@password* as that used when `sp_adddistrbutor` was run at the distributor to set up distribution.</span></span>  
  
    ```sql
    exec sys.sp_adddistributor  
        @distributor = 'MyDistributor',  
        @password = 'MyDistPass'  
    ```  
  
2.  <span data-ttu-id="7e4bf-127">Habilitar o banco de dados para replicação.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-127">Enable the database for replication.</span></span> <span data-ttu-id="7e4bf-128">Se estiverem sendo usados procedimentos armazenados para configurar o publicador, execute `sp_replicationdboption`.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-128">If stored procedures are being used to configure the publisher, run `sp_replicationdboption`.</span></span> <span data-ttu-id="7e4bf-129">Se as replicações transacional e de mesclagem forem configurada para o banco de dados, cada uma deverá ser habilitada.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-129">If both transactional and merge replication are to be configured for the database, each must be enabled.</span></span>  
  
    ```sql
    USE master;  
    GO  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'publish',  
        @value = 'true';  
  
    EXEC sys.sp_replicationdboption  
        @dbname = 'MyDBName',  
        @optname = 'merge publish',  
        @value = 'true';  
    ```  
  
3.  <span data-ttu-id="7e4bf-130">Criar publicações, artigos e assinaturas da replicação.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-130">Create the replication publication, articles, and subscriptions.</span></span> <span data-ttu-id="7e4bf-131">Para obter mais informações sobre como configurar a replicação consulte os objetos Publishing Data e Database.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-131">For more information about how to configure replication, see Publishing Data and Database objects.</span></span>  
  
##  <a name="2-configure-the-alwayson-availability-group"></a><a name="step2"></a><span data-ttu-id="7e4bf-132">2. configurar o grupo de disponibilidade AlwaysOn</span><span class="sxs-lookup"><span data-stu-id="7e4bf-132">2. Configure the AlwaysOn Availability Group</span></span>  
 <span data-ttu-id="7e4bf-133">Na réplica primária pretendida, crie o grupo de disponibilidade com o banco de dados publicado (ou a ser publicado) como um banco de dados membro.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-133">At the intended primary, create the availability group with the published (or to be published) database as a member database.</span></span> <span data-ttu-id="7e4bf-134">Se estiver usando o Assistente de Grupo de Disponibilidade, você poderá permitir que o assistente sincronize os bancos de dados de réplica secundária inicialmente ou poderá executar a inicialização manualmente usando backup e restauração.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-134">If using the Availability Group Wizard, you can either allow the wizard to initially synchronize the secondary replica databases or you can perform the initialization manually by using backup and restore.</span></span>  
  
 <span data-ttu-id="7e4bf-135">Crie um ouvinte de DNS para o grupo de disponibilidade que será usado pelos agentes de replicação para conectar à replicação primária atual.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-135">Create a DNS listener for the availability group that will be used by the replication agents to connect to the current primary.</span></span> <span data-ttu-id="7e4bf-136">O nome de ouvinte que é especificado será usado como o destino de redirecionamento para o par publicador original/banco de dados publicado.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-136">The listener name that is specified will be used as the target of redirection for the original publisher/published database pair.</span></span> <span data-ttu-id="7e4bf-137">Por exemplo, se você estiver usando o DDL para configurar o grupo de disponibilidade, o seguinte exemplo de código poderá ser usado para especificar um ouvinte de grupo de disponibilidade para um grupo de disponibilidade existente chamado `MyAG`:</span><span class="sxs-lookup"><span data-stu-id="7e4bf-137">For example, if you are using DDL to configure the availability group, the following code example can be used to specify an availability group listener for an existing availability group named `MyAG`:</span></span>  
  
```sql
ALTER AVAILABILITY GROUP 'MyAG'   
    ADD LISTENER 'MyAGListenerName' (WITH IP (('10.120.19.155', '255.255.254.0')));  
```  
  
 <span data-ttu-id="7e4bf-138">Para obter mais informações, consulte [Criação e configuração de Grupos de Disponibilidade &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="7e4bf-138">For more information, see [Creation and Configuration of Availability Groups &#40;SQL Server&#41;](creation-and-configuration-of-availability-groups-sql-server.md).</span></span>  
  
##  <a name="3-insure-that-all-of-the-secondary-replica-hosts-are-configured-for-replication"></a><a name="step3"></a><span data-ttu-id="7e4bf-139">3. Verifique se todos os hosts de réplica secundária estão configurados para replicação</span><span class="sxs-lookup"><span data-stu-id="7e4bf-139">3. Insure that all of the Secondary Replica Hosts are Configured for Replication</span></span>  
 <span data-ttu-id="7e4bf-140">Em cada host de réplica secundária, verifique se o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] foi configurado para oferecer suporte à replicação.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-140">At each secondary replica host, verify that [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] has been configured to support replication.</span></span> <span data-ttu-id="7e4bf-141">A seguinte consulta pode ser executada em cada host de réplica secundária para determinar se a replicação é instalada:</span><span class="sxs-lookup"><span data-stu-id="7e4bf-141">The following query can be run at each secondary replica host to determine whether replication is installed:</span></span>  
  
```sql
USE master;  
GO  
DECLARE @installed int;  
EXEC @installed = sys.sp_MS_replication_installed;  
SELECT @installed;  
```  
  
 <span data-ttu-id="7e4bf-142">Se *@installed* for 0, a replicação deverá ser adicionada à [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] instalação.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-142">If *@installed* is 0, replication must be added to the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installation.</span></span>  
  
##  <a name="4-configure-the-secondary-replica-hosts-as-replication-publishers"></a><a name="step4"></a> <span data-ttu-id="7e4bf-143">4. Configurar os hosts de réplica secundária como publicadores de replicação</span><span class="sxs-lookup"><span data-stu-id="7e4bf-143">4. Configure the Secondary Replica Hosts as Replication Publishers</span></span>  
 <span data-ttu-id="7e4bf-144">Uma réplica secundária não pode agir como um publicador de replicação ou republicador, mas a replicação deve ser configurada de forma que a secundária possa assumir o comando depois de um failover.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-144">A secondary replica cannot act as a replication publisher or republisher but replication must be configured so that the secondary can take over after a failover.</span></span> <span data-ttu-id="7e4bf-145">No distribuidor, configure a distribuição para cada host de réplica secundária.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-145">At the distributor, configure distribution for each secondary replica host.</span></span> <span data-ttu-id="7e4bf-146">Especifique o mesmo banco de dados de distribuição e diretório de trabalho que foram especificados quando o publicador original foi adicionado ao distribuidor.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-146">Specify the same distribution database and working directory as was specified when the original publisher was added to the distributor.</span></span> <span data-ttu-id="7e4bf-147">Se você estiver usando procedimentos armazenados para configurar a distribuição, use `sp_adddistpublisher` para associar os publicadores remotos ao distribuidor.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-147">If you are using stored procedures to configure distribution, use `sp_adddistpublisher` to associate the remote publishers with the distributor.</span></span> <span data-ttu-id="7e4bf-148">Se *@login* e *@password* foram usados para o Publicador original, especifique os mesmos valores para cada um quando adicionar os hosts de réplica secundária como Publicadores.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-148">If *@login* and *@password* were used for the original publisher, specify the same values for each when you add the secondary replica hosts as publishers.</span></span>  
  
```sql
EXEC sys.sp_adddistpublisher  
    @publisher = 'AGSecondaryReplicaHost',  
    @distribution_db = 'distribution',  
    @working_directory = '\\MyReplShare\WorkingDir',  
    @login = 'MyPubLogin',  
    @password = '**Strong password for publisher**';  
```  
  
 <span data-ttu-id="7e4bf-149">Em cada host de réplica secundária, configure a distribuição.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-149">At each secondary replica host, configure distribution.</span></span> <span data-ttu-id="7e4bf-150">Identifique o distribuidor do publicador original como o distribuidor remoto.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-150">Identify the distributor of the original publisher as the remote distributor.</span></span> <span data-ttu-id="7e4bf-151">Use a mesma senha que foi usada na execução original do `sp_adddistributor` no distribuidor.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-151">Use the same password as that used when `sp_adddistributor` was run originally at the distributor.</span></span> <span data-ttu-id="7e4bf-152">Se procedimentos armazenados estiverem sendo usados para configurar a distribuição, o *@password* parâmetro de `sp_adddistributor` será usado para especificar a senha.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-152">If stored procedures are being used to configure distribution, the *@password* parameter of `sp_adddistributor` is used to specify the password.</span></span>  
  
```sql
EXEC sp_adddistributor   
    @distributor = 'MyDistributor',  
    @password = '**Strong password for distributor**';  
```  
  
 <span data-ttu-id="7e4bf-153">Em cada host de réplica secundária, verifique se os assinantes push das publicações de banco de dados aparecem como servidores vinculados.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-153">At each secondary replica host, make sure that the push subscribers of the database publications appear as linked servers.</span></span> <span data-ttu-id="7e4bf-154">Se estiverem sendo usados procedimentos armazenados para configurar os publicadores remotos, use `sp_addlinkedserver` para adicionar os assinantes (caso ainda não estejam presentes) como servidores vinculados aos publicadores.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-154">If stored procedures are being used to configure the remote publishers, use `sp_addlinkedserver` to add the subscribers (if not already present) as linked servers to the publishers.</span></span>  
  
```sql
EXEC sys.sp_addlinkedserver   
    @server = 'MySubscriber';  
```  
  
##  <a name="5-redirect-the-original-publisher-to-the-ag-listener-name"></a><a name="step5"></a> <span data-ttu-id="7e4bf-155">5. Redirecionar o publicador original para o nome do ouvinte do AG</span><span class="sxs-lookup"><span data-stu-id="7e4bf-155">5. Redirect the Original Publisher to the AG Listener Name</span></span>  
 <span data-ttu-id="7e4bf-156">No distribuidor, no banco de dados de distribuição, execute o procedimento armazenado `sp_redirect_publisher` para associar o publicador original e o banco de dados publicado com o nome do ouvinte de grupo de disponibilidade do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-156">At the distributor, in the distribution database, run the stored procedure `sp_redirect_publisher` to associate the original publisher and the published database with the availability group listener name of the availability group.</span></span>  
  
```sql
USE distribution;  
GO  
EXEC sys.sp_redirect_publisher   
@original_publisher = 'MyPublisher',  
    @publisher_db = 'MyPublishedDB',  
    @redirected_publisher = 'MyAGListenerName';  
```  
  
##  <a name="6-run-the-replication-validation-stored-procedure-to-verify-the-configuration"></a><a name="step6"></a> <span data-ttu-id="7e4bf-157">6. Executar o procedimento armazenado de validação de replicação para verificar a configuração</span><span class="sxs-lookup"><span data-stu-id="7e4bf-157">6. Run the Replication Validation Stored Procedure to Verify the Configuration</span></span>  
 <span data-ttu-id="7e4bf-158">No distribuidor, no banco de dados de distribuição, execute o `sp_validate_replica_hosts_as_publishers` de procedimento armazenado para verificar se todos os hosts de réplica estão configurados para servir como publicadores para o banco de dados publicado.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-158">At the distributor, in the distribution database, run the stored procedure `sp_validate_replica_hosts_as_publishers` to verify that all replica hosts are now configured to serve as publishers for the published database.</span></span>  
  
```sql
USE distribution;  
GO  
DECLARE @redirected_publisher sysname;  
EXEC sys.sp_validate_replica_hosts_as_publishers  
    @original_publisher = 'MyPublisher',  
    @publisher_db = 'MyPublishedDB',  
    @redirected_publisher = @redirected_publisher output;  
```  
  
 <span data-ttu-id="7e4bf-159">O `sp_validate_replica_hosts_as_publishers` de procedimento armazenado deve ser executado de um logon com autorização suficiente em cada host de réplica de grupo de disponibilidade para consultar informações sobre o grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-159">The stored procedure `sp_validate_replica_hosts_as_publishers` should be run from a login with sufficient authorization at each availability group replica host to query for information about the availability group.</span></span> <span data-ttu-id="7e4bf-160">Ao contrário de `sp_validate_redirected_publisher` , ele usa as credenciais do chamador e não usa o logon retido em msdb. dbo. MSdistpublishers para se conectar às réplicas do grupo de disponibilidade.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-160">Unlike `sp_validate_redirected_publisher`, it uses the credentials of the caller and does not use the login retained in msdb.dbo.MSdistpublishers to connect to the availability group replicas.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="7e4bf-161">O `sp_validate_replica_hosts_as_publishers` falhará com o erro a seguir na validação de hosts de réplica secundária que não permitem acesso de leitura, ou exigem a especificação da intenção de leitura.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-161">`sp_validate_replica_hosts_as_publishers` will fail with the following error when validating secondary replica hosts that do not allow read access, or require read intent to be specified.</span></span>  
>   
>  <span data-ttu-id="7e4bf-162">Mensagem 21899, Nível 11, Estado 1, Procedimento `sp_hadr_verify_subscribers_at_publisher`, Linha 109</span><span class="sxs-lookup"><span data-stu-id="7e4bf-162">Msg 21899, Level 11, State 1, Procedure `sp_hadr_verify_subscribers_at_publisher`, Line 109</span></span>  
>   
>  <span data-ttu-id="7e4bf-163">A consulta no publicador redirecionado 'MyReplicaHostName' para determinar se havia entradas de sysserver para os assinantes do publicador original 'MyOriginalPublisher' falhou com o erro '976', mensagem de erro ' Erro 976, Nível 14, Estado 1, Mensagem: O banco de dados de destino, 'MyPublishedDB', está participando de um grupo de disponibilidade e atualmente não está acessível para consultas.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-163">The query at the redirected publisher 'MyReplicaHostName' to determine whether there were sysserver entries for the subscribers of the original publisher 'MyOriginalPublisher' failed with error '976', error message 'Error 976, Level 14, State 1, Message: The target database, 'MyPublishedDB', is participating in an availability group and is currently not accessible for queries.</span></span> <span data-ttu-id="7e4bf-164">Qualquer movimento de dados é suspenso ou a réplica de disponibilidade não é habilitada para acesso de leitura.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-164">Either data movement is suspended or the availability replica is not enabled for read access.</span></span> <span data-ttu-id="7e4bf-165">Para permitir o acesso somente leitura a esse banco de dados e a outros no grupo de disponibilidade, habilite o acesso de leitura para uma ou mais réplicas de disponibilidade secundárias no grupo.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-165">To allow read-only access to this and other databases in the availability group, enable read access to one or more secondary availability replicas in the group.</span></span>  <span data-ttu-id="7e4bf-166">Para obter mais informações, consulte a instrução `ALTER AVAILABILITY GROUP` nos Manuais Online do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="7e4bf-166">For more information, see the `ALTER AVAILABILITY GROUP` statement in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Books Online.'.</span></span>  
>   
>  <span data-ttu-id="7e4bf-167">Foram encontrados um ou mais erros de validação de publicador para o host de réplica 'MyReplicaHostName'.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-167">One or more publisher validation errors were encountered for replica host 'MyReplicaHostName'.</span></span>  
  
 <span data-ttu-id="7e4bf-168">Este comportamento é esperado.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-168">This is expected behavior.</span></span> <span data-ttu-id="7e4bf-169">Você deve verificar a presença das entradas de servidor de assinante nesses hosts de réplica secundária, consultando as entradas de sysserver diretamente no host.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-169">You must verify the presence of the subscriber server entries at these secondary replica hosts by querying for the sysserver entries directly at the host.</span></span>  
  
##  <a name="7-add-the-original-publisher-to-replication-monitor"></a><a name="step7"></a> <span data-ttu-id="7e4bf-170">7. Adicionar o publicador original ao Replication Monitor</span><span class="sxs-lookup"><span data-stu-id="7e4bf-170">7. Add the Original Publisher to Replication Monitor</span></span>  
 <span data-ttu-id="7e4bf-171">Em cada réplica de grupo de disponibilidade, adicione o publicador original ao Replication Monitor.</span><span class="sxs-lookup"><span data-stu-id="7e4bf-171">At each availability group replica, add the original publisher to Replication Monitor.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="7e4bf-172">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="7e4bf-172">Related Tasks</span></span>  
 <span data-ttu-id="7e4bf-173">**Replicação**</span><span class="sxs-lookup"><span data-stu-id="7e4bf-173">**Replication**</span></span>  
  
-   [<span data-ttu-id="7e4bf-174">Mantendo um banco de dados de publicação AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7e4bf-174">Maintaining an AlwaysOn Publication Database &#40;SQL Server&#41;</span></span>](maintaining-an-always-on-publication-database-sql-server.md)  
  
-   [<span data-ttu-id="7e4bf-175">Replicação, Controle de Alterações, captura de dados de alteração e Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7e4bf-175">Replication, Change Tracking, Change Data Capture, and AlwaysOn Availability Groups &#40;SQL Server&#41;</span></span>](replicate-track-change-data-capture-always-on-availability.md)  
  
-   [<span data-ttu-id="7e4bf-176">Perguntas Frequentes sobre Administração de Replicação</span><span class="sxs-lookup"><span data-stu-id="7e4bf-176">Replication Administration FAQ</span></span>](../../../relational-databases/replication/administration/frequently-asked-questions-for-replication-administrators.md)  
  
 <span data-ttu-id="7e4bf-177">**Para criar e configurar um grupo de disponibilidade**</span><span class="sxs-lookup"><span data-stu-id="7e4bf-177">**To create and configure an availability group**</span></span>  
  
-   [<span data-ttu-id="7e4bf-178">Usar o Assistente de Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7e4bf-178">Use the Availability Group Wizard &#40;SQL Server Management Studio&#41;</span></span>](use-the-availability-group-wizard-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="7e4bf-179">Usar a caixa de diálogo Novo Grupo de Disponibilidade &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="7e4bf-179">Use the New Availability Group Dialog Box &#40;SQL Server Management Studio&#41;</span></span>](use-the-new-availability-group-dialog-box-sql-server-management-studio.md)  
  
-   [<span data-ttu-id="7e4bf-180">Criar um grupo de disponibilidade &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="7e4bf-180">Create an Availability Group &#40;Transact-SQL&#41;</span></span>](create-an-availability-group-transact-sql.md)  
  
-   [<span data-ttu-id="7e4bf-181">Criar um grupo de disponibilidade &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="7e4bf-181">Create an Availability Group &#40;SQL Server PowerShell&#41;</span></span>](../../../powershell/sql-server-powershell.md)  
  
-   [<span data-ttu-id="7e4bf-182">Especificar a URL do ponto de extremidade ao adicionar ou modificar uma réplica de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7e4bf-182">Specify the Endpoint URL When Adding or Modifying an Availability Replica &#40;SQL Server&#41;</span></span>](specify-endpoint-url-adding-or-modifying-availability-replica.md)  
  
-   [<span data-ttu-id="7e4bf-183">Criar um ponto de extremidade de espelhamento de banco de dados para Grupos de Disponibilidade AlwaysOn &#40;SQL Server PowerShell&#41;</span><span class="sxs-lookup"><span data-stu-id="7e4bf-183">Create a Database Mirroring Endpoint for AlwaysOn Availability Groups &#40;SQL Server PowerShell&#41;</span></span>](database-mirroring-always-on-availability-groups-powershell.md)  
  
-   [<span data-ttu-id="7e4bf-184">Unir uma réplica secundária a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7e4bf-184">Join a Secondary Replica to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-replica-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="7e4bf-185">Preparar um banco de dados secundário manualmente para um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7e4bf-185">Manually Prepare a Secondary Database for an Availability Group &#40;SQL Server&#41;</span></span>](manually-prepare-a-secondary-database-for-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="7e4bf-186">Unir um banco de dados secundário a um grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7e4bf-186">Join a Secondary Database to an Availability Group &#40;SQL Server&#41;</span></span>](join-a-secondary-database-to-an-availability-group-sql-server.md)  
  
-   [<span data-ttu-id="7e4bf-187">Criar ou configurar um ouvinte do grupo de disponibilidade &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="7e4bf-187">Create or Configure an Availability Group Listener &#40;SQL Server&#41;</span></span>](create-or-configure-an-availability-group-listener-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="7e4bf-188">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="7e4bf-188">See Also</span></span>  
 <span data-ttu-id="7e4bf-189">[Pré-requisitos, restrições e recomendações para Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="7e4bf-189">[Prerequisites, Restrictions, and Recommendations for AlwaysOn Availability Groups &#40;SQL Server&#41;](prereqs-restrictions-recommendations-always-on-availability.md) </span></span>  
 <span data-ttu-id="7e4bf-190">[Visão geral do Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7e4bf-190">[Overview of AlwaysOn Availability Groups &#40;SQL Server&#41;](overview-of-always-on-availability-groups-sql-server.md) </span></span>  
 <span data-ttu-id="7e4bf-191">[Grupos de Disponibilidade AlwaysOn: interoperabilidade (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="7e4bf-191">[AlwaysOn Availability Groups: Interoperability (SQL Server)](always-on-availability-groups-interoperability-sql-server.md) </span></span>  
 [<span data-ttu-id="7e4bf-192">Replicação do SQL Server</span><span class="sxs-lookup"><span data-stu-id="7e4bf-192">SQL Server Replication</span></span>](../../../relational-databases/replication/sql-server-replication.md)  
