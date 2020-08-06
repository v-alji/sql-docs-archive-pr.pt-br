---
title: 'Exemplo: Configurando o espelhamento de banco de dados usando a autenticação do Windows (Transact-SQL) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- Windows authentication [SQL Server]
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: 35800769-aede-4aac-b077-0e0e487e302f
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: 95df855e8e41c5937aae02884c71792537eb2bfc
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570201"
---
# <a name="example-setting-up-database-mirroring-using-windows-authentication-transact-sql"></a><span data-ttu-id="3cbd0-102">Exemplo: Configurando o espelhamento de banco de dados usando a Autenticação do Windows (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="3cbd0-102">Example: Setting Up Database Mirroring Using Windows Authentication (Transact-SQL)</span></span>
  <span data-ttu-id="3cbd0-103">Este exemplo mostra todas as fases necessárias para criar uma sessão de espelhamento de banco de dados com uma testemunha, usando a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="3cbd0-103">This example shows all the stages required to create a database mirroring session with a witness using Windows Authentication.</span></span> <span data-ttu-id="3cbd0-104">Os exemplos deste tópico usam o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="3cbd0-104">The examples in this topic use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="3cbd0-105">Note que como uma alternativa para o uso de passos de [!INCLUDE[tsql](../../includes/tsql-md.md)], você pode usar o Assistente para Configurar Segurança de Espelhamento de Banco de Dados para a configuração do espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="3cbd0-105">Note that as an alternative to using [!INCLUDE[tsql](../../includes/tsql-md.md)] steps, you can use the Configure Database Mirroring Security Wizard for database mirroring setup.</span></span> <span data-ttu-id="3cbd0-106">Para obter mais informações, veja [Estabelecer uma sessão de espelhamento de banco de dados usando a Autenticação do Windows &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span><span class="sxs-lookup"><span data-stu-id="3cbd0-106">For more information, see [Establish a Database Mirroring Session Using Windows Authentication &#40;SQL Server Management Studio&#41;](establish-database-mirroring-session-windows-authentication.md).</span></span>  
  
## <a name="prerequisite"></a><span data-ttu-id="3cbd0-107">Pré-requisito</span><span class="sxs-lookup"><span data-stu-id="3cbd0-107">Prerequisite</span></span>  
 <span data-ttu-id="3cbd0-108">O exemplo usa o banco de dados de exemplo do **AdventureWorks** , que, por padrão, usa o modelo de recuperação simples.</span><span class="sxs-lookup"><span data-stu-id="3cbd0-108">The example uses the **AdventureWorks** sample database, which uses the simple recovery model by default.</span></span> <span data-ttu-id="3cbd0-109">Para usar espelhamento de banco de dados com este banco de dados, você deve alterar isso para usar o modelo de recuperação completa.</span><span class="sxs-lookup"><span data-stu-id="3cbd0-109">To use database mirroring with this database, you must alter it to use the full recovery model.</span></span> <span data-ttu-id="3cbd0-110">Para fazer isto em [!INCLUDE[tsql](../../includes/tsql-md.md)], use a instrução ALTER DATABASE, como se segue:</span><span class="sxs-lookup"><span data-stu-id="3cbd0-110">To do this in [!INCLUDE[tsql](../../includes/tsql-md.md)], use the ALTER DATABASE statement, as follows:</span></span>  
  
```  
USE master;  
GO  
ALTER DATABASE AdventureWorks   
SET RECOVERY FULL;  
GO  
```  
  
 <span data-ttu-id="3cbd0-111">Para saber mais sobre como alterar o modelo de recuperação no [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], consulte [Exibir ou alterar o modelo de recuperação de um banco de dados &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3cbd0-111">For information on changing the recovery model in [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], see [View or Change the Recovery Model of a Database &#40;SQL Server&#41;](../../relational-databases/backup-restore/view-or-change-the-recovery-model-of-a-database-sql-server.md).</span></span>  
  
### <a name="permissions"></a><span data-ttu-id="3cbd0-112">Permissões</span><span class="sxs-lookup"><span data-stu-id="3cbd0-112">Permissions</span></span>  
 <span data-ttu-id="3cbd0-113">Exige a permissão ALTER no banco de dados e permissão CREATE ENDPOINT ou associação na função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="3cbd0-113">Requires ALTER permission on the database and CREATE ENDPOINT permission, or membership in the **sysadmin** fixed server role.</span></span>  
  
## <a name="example"></a><span data-ttu-id="3cbd0-114">Exemplo</span><span class="sxs-lookup"><span data-stu-id="3cbd0-114">Example</span></span>  
 <span data-ttu-id="3cbd0-115">Neste exemplo, os dois parceiros e a testemunha são as instâncias de servidor padrão em três sistemas de computador.</span><span class="sxs-lookup"><span data-stu-id="3cbd0-115">In this example, the two partners and the witness are the default server instances on three computer systems.</span></span> <span data-ttu-id="3cbd0-116">As três instâncias de servidor executam o mesmo domínio do Windows, mas a conta do usuário (usada como conta de serviço de inicialização) é diferente para a instância de servidor testemunha do exemplo.</span><span class="sxs-lookup"><span data-stu-id="3cbd0-116">The three server instances run the same Windows domain, but the user account (used as the startup service account) is different for the example's witness server instance.</span></span>  
  
 <span data-ttu-id="3cbd0-117">A tabela a seguir resume os valores usados neste exemplo.</span><span class="sxs-lookup"><span data-stu-id="3cbd0-117">The following table summarizes the values used in this example.</span></span>  
  
|<span data-ttu-id="3cbd0-118">Função de espelhamento inicial</span><span class="sxs-lookup"><span data-stu-id="3cbd0-118">Initial mirroring role</span></span>|<span data-ttu-id="3cbd0-119">Sistema de host</span><span class="sxs-lookup"><span data-stu-id="3cbd0-119">Host system</span></span>|<span data-ttu-id="3cbd0-120">Conta de usuário do domínio</span><span class="sxs-lookup"><span data-stu-id="3cbd0-120">Domain user account</span></span>|  
|----------------------------|-----------------|-------------------------|  
|<span data-ttu-id="3cbd0-121">Principal</span><span class="sxs-lookup"><span data-stu-id="3cbd0-121">Principal</span></span>|<span data-ttu-id="3cbd0-122">PARTNERHOST1</span><span class="sxs-lookup"><span data-stu-id="3cbd0-122">PARTNERHOST1</span></span>|<span data-ttu-id="3cbd0-123">*\<Mydomain>\\<dbousername\>*</span><span class="sxs-lookup"><span data-stu-id="3cbd0-123">*\<Mydomain>\\<dbousername\>*</span></span>|  
|<span data-ttu-id="3cbd0-124">Espelho</span><span class="sxs-lookup"><span data-stu-id="3cbd0-124">Mirror</span></span>|<span data-ttu-id="3cbd0-125">PARTNERHOST5</span><span class="sxs-lookup"><span data-stu-id="3cbd0-125">PARTNERHOST5</span></span>|<span data-ttu-id="3cbd0-126">*\<Mydomain>\\<dbousername\>*</span><span class="sxs-lookup"><span data-stu-id="3cbd0-126">*\<Mydomain>\\<dbousername\>*</span></span>|  
|<span data-ttu-id="3cbd0-127">Witness (testemunha)</span><span class="sxs-lookup"><span data-stu-id="3cbd0-127">Witness</span></span>|<span data-ttu-id="3cbd0-128">WITNESSHOST4</span><span class="sxs-lookup"><span data-stu-id="3cbd0-128">WITNESSHOST4</span></span>|<span data-ttu-id="3cbd0-129">*\<Somedomain>\\<witnessuser\>*</span><span class="sxs-lookup"><span data-stu-id="3cbd0-129">*\<Somedomain>\\<witnessuser\>*</span></span>|  
  
1.  <span data-ttu-id="3cbd0-130">Crie um ponto de extremidade na instância de servidor principal (instância padrão em PARTNERHOST1).</span><span class="sxs-lookup"><span data-stu-id="3cbd0-130">Create an endpoint on the principal server instance (default instance on PARTNERHOST1).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=PARTNER)  
    GO  
    --Partners under same domain user; login already exists in master.  
    --Create a login for the witness server instance,  
    --which is running as Somedomain\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [Somedomain\witnessuser] FROM WINDOWS ;  
    GO  
    -- Grant connect permissions on endpoint to login account of witness.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Somedomain\witnessuser];  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
2.  <span data-ttu-id="3cbd0-131">Crie um ponto de extremidade na instância de servidor espelho (instância padrão em PARTNERHOST5).</span><span class="sxs-lookup"><span data-stu-id="3cbd0-131">Create an endpoint on the mirror server instance (default instance on PARTNERHOST5).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=ALL)  
    GO  
    --Partners under same domain user; login already exists in master.  
    --Create a login for the witness server instance,  
    --which is running as Somedomain\witnessuser:  
    USE master ;  
    GO  
    CREATE LOGIN [Somedomain\witnessuser] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account of witness.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Somedomain\witnessuser];  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
3.  <span data-ttu-id="3cbd0-132">Crie um ponto de extremidade na instância de servidor testemunha (instância padrão em WITNESSHOST4).</span><span class="sxs-lookup"><span data-stu-id="3cbd0-132">Create an endpoint on the witness server instance (default instance on WITNESSHOST4).</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
        STATE=STARTED   
        AS TCP (LISTENER_PORT=7022)   
        FOR DATABASE_MIRRORING (ROLE=WITNESS)  
    GO  
    --Create a login for the partner server instances,  
    --which are both running as Mydomain\dbousername:  
    USE master ;  
    GO  
    CREATE LOGIN [Mydomain\dbousername] FROM WINDOWS ;  
    GO  
    --Grant connect permissions on endpoint to login account of partners.  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [Mydomain\dbousername];  
    GO  
    ```  
  
4.  <span data-ttu-id="3cbd0-133">Crie o banco de dados espelho.</span><span class="sxs-lookup"><span data-stu-id="3cbd0-133">Create the mirror database.</span></span> <span data-ttu-id="3cbd0-134">Para obter mais informações, veja [Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="3cbd0-134">For more information, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
5.  <span data-ttu-id="3cbd0-135">Na instância de servidor espelho em PARTNERHOST5, defina a instância de servidor em PARTNERHOST1 como o parceiro (fazendo dele a instância de servidor principal inicial).</span><span class="sxs-lookup"><span data-stu-id="3cbd0-135">On the mirror server instance on PARTNERHOST5, set the server instance on PARTNERHOST1 as the partner (making it the initial principal server instance).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET PARTNER =   
        'TCP://PARTNERHOST1.COM:7022'  
    GO  
    ```  
  
6.  <span data-ttu-id="3cbd0-136">Na instância do servidor principal em PARTNERHOST1, defina a instância de servidor em PARTNERHOST5 como o parceiro (fazendo dele a instância de servidor espelho inicial).</span><span class="sxs-lookup"><span data-stu-id="3cbd0-136">On the principal server instance on PARTNERHOST1, set the server instance on PARTNERHOST5 as the partner (making it the initial mirror server instance).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://PARTNERHOST5.COM:7022'  
    GO  
    ```  
  
7.  <span data-ttu-id="3cbd0-137">No servidor principal, defina a testemunha (que está em WITNESSHOST4).</span><span class="sxs-lookup"><span data-stu-id="3cbd0-137">On the principal server, set the witness (which is on WITNESSHOST4).</span></span>  
  
    ```  
    ALTER DATABASE AdventureWorks   
        SET WITNESS =   
        'TCP://WITNESSHOST4.COM:7022'  
    GO  
    ```  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="3cbd0-138">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="3cbd0-138">Related Tasks</span></span>  
  
-   [<span data-ttu-id="3cbd0-139">Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="3cbd0-139">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
-   [<span data-ttu-id="3cbd0-140">Iniciar o Assistente para Configurar Segurança de Espelhamento de Banco de Dados &#40;SQL Server Management Studio&#41;</span><span class="sxs-lookup"><span data-stu-id="3cbd0-140">Start the Configuring Database Mirroring Security Wizard &#40;SQL Server Management Studio&#41;</span></span>](start-the-configuring-database-mirroring-security-wizard.md)  
  
-   [<span data-ttu-id="3cbd0-141">Configurar um banco de dados espelho para usar a propriedade confiável &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3cbd0-141">Set Up a Mirror Database to Use the Trustworthy Property &#40;Transact-SQL&#41;</span></span>](set-up-a-mirror-database-to-use-the-trustworthy-property-transact-sql.md)  
  
-   [<span data-ttu-id="3cbd0-142">Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de saída &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3cbd0-142">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
-   [<span data-ttu-id="3cbd0-143">Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de entrada &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3cbd0-143">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="3cbd0-144">Exemplo: Configurar o espelhamento de banco de dados usando certificados &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="3cbd0-144">Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;</span></span>](example-setting-up-database-mirroring-using-certificates-transact-sql.md)  
  
## <a name="see-also"></a><span data-ttu-id="3cbd0-145">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="3cbd0-145">See Also</span></span>  
 <span data-ttu-id="3cbd0-146">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="3cbd0-146">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 <span data-ttu-id="3cbd0-147">[O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="3cbd0-147">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="3cbd0-148">[Segurança de transporte para espelhamento de banco de dados e Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="3cbd0-148">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="3cbd0-149">[Gerenciar metadados ao disponibilizar um banco de dados em outra instância do servidor &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) </span><span class="sxs-lookup"><span data-stu-id="3cbd0-149">[Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) </span></span>  
 [<span data-ttu-id="3cbd0-150">Central de segurança do Mecanismo de Banco de Dados do SQL Server e Banco de Dados SQL do Azure</span><span class="sxs-lookup"><span data-stu-id="3cbd0-150">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
