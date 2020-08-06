---
title: 'Exemplo: configurar o espelhamento de banco de dados usando certificados (Transact-SQL) | Microsoft Docs'
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- database mirroring [SQL Server], deployment
- certificates [SQL Server], database mirroring
- authentication [SQL Server], database mirroring
- database mirroring [SQL Server], security
ms.assetid: df489ecd-deee-465c-a26a-6d1bef6d7b66
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: ea87e2de984107c5a0fda6eb2629ee5cfd197841
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685931"
---
# <a name="example-setting-up-database-mirroring-using-certificates-transact-sql"></a><span data-ttu-id="d2165-102">Exemplo: configurar espelhamento de banco de dados usando certificados (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="d2165-102">Example: Setting Up Database Mirroring Using Certificates (Transact-SQL)</span></span>
  <span data-ttu-id="d2165-103">Este exemplo mostra todos os estágios necessários para criar uma sessão de espelhamento de banco de dados com uma autenticação baseada em certificado.</span><span class="sxs-lookup"><span data-stu-id="d2165-103">This example shows all the stages required to create a database mirroring session using certificate-based authentication.</span></span> <span data-ttu-id="d2165-104">Os exemplos deste tópico usam o [!INCLUDE[tsql](../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="d2165-104">The examples in this topic use [!INCLUDE[tsql](../../includes/tsql-md.md)].</span></span> <span data-ttu-id="d2165-105">A menos que você possa garantir que sua rede está segura, recomendamos o uso de criptografia para conexões de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="d2165-105">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span>  
  
 <span data-ttu-id="d2165-106">Ao copiar um certificado para outro sistema, use um método de cópia seguro.</span><span class="sxs-lookup"><span data-stu-id="d2165-106">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="d2165-107">Seja extremamente cauteloso para manter todos os seus certificados em segurança.</span><span class="sxs-lookup"><span data-stu-id="d2165-107">Be extremely careful to keep all of your certificates secure.</span></span>  
  
##  <a name="example"></a><a name="ExampleH2"></a> <span data-ttu-id="d2165-108">Exemplo</span><span class="sxs-lookup"><span data-stu-id="d2165-108">Example</span></span>  
 <span data-ttu-id="d2165-109">O exemplo a seguir demonstra o que deve ser feito em um parceiro que reside em HOST_A.</span><span class="sxs-lookup"><span data-stu-id="d2165-109">The following example demonstrates what must be done on one partner that resides on HOST_A.</span></span> <span data-ttu-id="d2165-110">Neste exemplo, os dois parceiros são as instâncias de servidor padrão em três sistemas de computador.</span><span class="sxs-lookup"><span data-stu-id="d2165-110">In this example, the two partners are the default server instances on three computer systems.</span></span> <span data-ttu-id="d2165-111">As duas instâncias de servidor são executadas em domínios não confiáveis do Windows, portanto, é necessária autenticação baseada em certificado.</span><span class="sxs-lookup"><span data-stu-id="d2165-111">The two server instances run in nontrusted Windows domains, so certificate-based authentication is required.</span></span>  
  
 <span data-ttu-id="d2165-112">A função principal inicial é assumida pelo HOST_A, e a função de espelho é assumida pelo HOST_B.</span><span class="sxs-lookup"><span data-stu-id="d2165-112">The initial principal role is taken by HOST_A, and the mirror role is taken by HOST_B.</span></span>  
  
 <span data-ttu-id="d2165-113">A configuração do espelhamento de banco de dados usando certificados envolve quatro estágios gerais, dos quais três – 1, 2 e 4 – são demonstrados por este exemplo.</span><span class="sxs-lookup"><span data-stu-id="d2165-113">Setting up database mirroring using certificates involves four general stages, of which three stages-1, 2, and 4-are demonstrated by this example.</span></span> <span data-ttu-id="d2165-114">Esses estágios são os seguintes:</span><span class="sxs-lookup"><span data-stu-id="d2165-114">These stages are as follows:</span></span>  
  
1.  [<span data-ttu-id="d2165-115">Configurando conexões de saída</span><span class="sxs-lookup"><span data-stu-id="d2165-115">Configuring Outbound Connections</span></span>](#ConfiguringOutboundConnections)  
  
     <span data-ttu-id="d2165-116">Este exemplo mostra as etapas para:</span><span class="sxs-lookup"><span data-stu-id="d2165-116">This example shows the steps for:</span></span>  
  
    1.  <span data-ttu-id="d2165-117">Configurar o Host_A para conexões de saída.</span><span class="sxs-lookup"><span data-stu-id="d2165-117">Configuring Host_A for outbound connections.</span></span>  
  
    2.  <span data-ttu-id="d2165-118">Configurar o Host_B para conexões de saída.</span><span class="sxs-lookup"><span data-stu-id="d2165-118">Configuring Host_B for outbound connections.</span></span>  
  
     <span data-ttu-id="d2165-119">Para obter informações sobre esse estágio de configuração do espelhamento de banco de dados, consulte [Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de saída &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="d2165-119">For information about this stage of setting up database mirroring, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
2.  [<span data-ttu-id="d2165-120">Configurando conexões de saída</span><span class="sxs-lookup"><span data-stu-id="d2165-120">Configuring Inbound Connections</span></span>](#ConfigureInboundConnections)  
  
     <span data-ttu-id="d2165-121">Este exemplo mostra as etapas para:</span><span class="sxs-lookup"><span data-stu-id="d2165-121">This example shows the steps for:</span></span>  
  
    1.  <span data-ttu-id="d2165-122">Configurar o Host_A para conexões de entrada.</span><span class="sxs-lookup"><span data-stu-id="d2165-122">Configuring Host_A for inbound connections.</span></span>  
  
    2.  <span data-ttu-id="d2165-123">Configurar o Host_B para conexões de entrada.</span><span class="sxs-lookup"><span data-stu-id="d2165-123">Configuring Host_B for inbound connections.</span></span>  
  
     <span data-ttu-id="d2165-124">Para obter informações sobre esse estágio de configuração do espelhamento de banco de dados, consulte [Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de entrada &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="d2165-124">For information about this stage of setting up database mirroring, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
3.  <span data-ttu-id="d2165-125">Criando o banco de dados espelho</span><span class="sxs-lookup"><span data-stu-id="d2165-125">Creating the Mirror Database</span></span>  
  
     <span data-ttu-id="d2165-126">Para obter informações sobre como criar um banco de dados espelho, consulte [Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d2165-126">For information on how to create a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
4.  [<span data-ttu-id="d2165-127">Configurando os parceiros de espelhamento</span><span class="sxs-lookup"><span data-stu-id="d2165-127">Configuring the Mirroring Partners</span></span>](#ConfigureMirroringPartners)  
  
###  <a name="configuring-outbound-connections"></a><a name="ConfiguringOutboundConnections"></a> <span data-ttu-id="d2165-128">Configurando conexões de saída</span><span class="sxs-lookup"><span data-stu-id="d2165-128">Configuring Outbound Connections</span></span>  
 <span data-ttu-id="d2165-129">**Para configurar Host_A para conexões de saída**</span><span class="sxs-lookup"><span data-stu-id="d2165-129">**To configure Host_A for outbound connections**</span></span>  
  
1.  <span data-ttu-id="d2165-130">No banco de dados mestre, crie a chave mestra de banco de dados, se necessário.</span><span class="sxs-lookup"><span data-stu-id="d2165-130">On the master database, create the database master key, if needed.</span></span>  
  
    ```  
    USE master;  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<1_Strong_Password!>';  
    GO  
    ```  
  
2.  <span data-ttu-id="d2165-131">Faça um certificado para esta instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="d2165-131">Make a certificate for this server instance.</span></span>  
  
    ```  
    USE master;  
    CREATE CERTIFICATE HOST_A_cert   
       WITH SUBJECT = 'HOST_A certificate';  
    GO  
    ```  
  
3.  <span data-ttu-id="d2165-132">Crie um ponto de extremidade de espelhamento para a instância de servidor que usa o certificado.</span><span class="sxs-lookup"><span data-stu-id="d2165-132">Create a mirroring endpoint for server instance using the certificate.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
       STATE = STARTED  
       AS TCP (  
          LISTENER_PORT=7024  
          , LISTENER_IP = ALL  
       )   
       FOR DATABASE_MIRRORING (   
          AUTHENTICATION = CERTIFICATE HOST_A_cert  
          , ENCRYPTION = REQUIRED ALGORITHM AES  
          , ROLE = ALL  
       );  
    GO  
    ```  
  
4.  <span data-ttu-id="d2165-133">Faça backup do certificado de HOST_A e copie-o para outro sistema, HOST_B.</span><span class="sxs-lookup"><span data-stu-id="d2165-133">Back up the HOST_A certificate, and copy it to other system, HOST_B.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_A_cert TO FILE = 'C:\HOST_A_cert.cer';  
    GO  
    ```  
  
5.  <span data-ttu-id="d2165-134">Usando qualquer método de cópia seguro, copie C:\HOST_A_cert.cer para HOST_B.</span><span class="sxs-lookup"><span data-stu-id="d2165-134">Using any secure copy method, copy C:\HOST_A_cert.cer to HOST_B.</span></span>  
  
 <span data-ttu-id="d2165-135">**Para configurar Host_B para conexões de saída**</span><span class="sxs-lookup"><span data-stu-id="d2165-135">**To configure Host_B for outbound connections**</span></span>  
  
1.  <span data-ttu-id="d2165-136">No banco de dados mestre, crie a chave mestra de banco de dados, se necessário.</span><span class="sxs-lookup"><span data-stu-id="d2165-136">On the master database, create the database master key, if needed.</span></span>  
  
    ```  
    USE master;  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<Strong_Password_#2>';  
    GO  
    ```  
  
2.  <span data-ttu-id="d2165-137">Faça um certificado na instância de servidor HOST_B.</span><span class="sxs-lookup"><span data-stu-id="d2165-137">Make a certificate on the HOST_B server instance.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_B_cert   
       WITH SUBJECT = 'HOST_B certificate for database mirroring';  
    GO  
    ```  
  
3.  <span data-ttu-id="d2165-138">Crie um ponto de extremidade de espelhamento para a instância de servidor em HOST_B.</span><span class="sxs-lookup"><span data-stu-id="d2165-138">Create a mirroring endpoint for the server instance on HOST_B.</span></span>  
  
    ```  
    CREATE ENDPOINT Endpoint_Mirroring  
       STATE = STARTED  
       AS TCP (  
          LISTENER_PORT=7024  
          , LISTENER_IP = ALL  
       )   
       FOR DATABASE_MIRRORING (   
          AUTHENTICATION = CERTIFICATE HOST_B_cert  
          , ENCRYPTION = REQUIRED ALGORITHM AES  
          , ROLE = ALL  
       );  
    GO  
    ```  
  
4.  <span data-ttu-id="d2165-139">Faça backup de certificado de HOST_B.</span><span class="sxs-lookup"><span data-stu-id="d2165-139">Back up HOST_B certificate.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_B_cert TO FILE = 'C:\HOST_B_cert.cer';  
    GO   
    ```  
  
5.  <span data-ttu-id="d2165-140">Usando qualquer método de cópia seguro, copie C:\HOST_ B_cert.cer para HOST_A.</span><span class="sxs-lookup"><span data-stu-id="d2165-140">Using any secure copy method, copy C:\HOST_B_cert.cer to HOST_A.</span></span>  
  
 <span data-ttu-id="d2165-141">Para obter mais informações, consulte [Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de saída &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="d2165-141">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
###  <a name="configuring-inbound-connections"></a><a name="ConfigureInboundConnections"></a> <span data-ttu-id="d2165-142">Configurando conexões de saída</span><span class="sxs-lookup"><span data-stu-id="d2165-142">Configuring Inbound Connections</span></span>  
 <span data-ttu-id="d2165-143">**Para configurar Host_A para conexões de entrada**</span><span class="sxs-lookup"><span data-stu-id="d2165-143">**To configure Host_A for inbound connections**</span></span>  
  
1.  <span data-ttu-id="d2165-144">Crie um logon em HOST_A para HOST_B.</span><span class="sxs-lookup"><span data-stu-id="d2165-144">Create a login on HOST_A for HOST_B.</span></span>  
  
    ```  
    USE master;  
    CREATE LOGIN HOST_B_login WITH PASSWORD = '1Sample_Strong_Password!@#';  
    GO  
    ```  
  
2.  <span data-ttu-id="d2165-145">--Crie um usuário para aquele logon.</span><span class="sxs-lookup"><span data-stu-id="d2165-145">--Create a user for that login.</span></span>  
  
    ```  
    CREATE USER HOST_B_user FOR LOGIN HOST_B_login;  
    GO  
    ```  
  
3.  <span data-ttu-id="d2165-146">--Associe o certificado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="d2165-146">--Associate the certificate with the user.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_B_cert  
       AUTHORIZATION HOST_B_user  
       FROM FILE = 'C:\HOST_B_cert.cer'  
    GO  
    ```  
  
4.  <span data-ttu-id="d2165-147">Conceda permissão CONNECT no logon para o ponto de extremidade de espelhamento remoto.</span><span class="sxs-lookup"><span data-stu-id="d2165-147">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_B_login];  
    GO  
    ```  
  
 <span data-ttu-id="d2165-148">**Para configurar Host_B para conexões de entrada**</span><span class="sxs-lookup"><span data-stu-id="d2165-148">**To configure Host_B for inbound connections**</span></span>  
  
1.  <span data-ttu-id="d2165-149">Crie um logon em HOST_B para HOST_A.</span><span class="sxs-lookup"><span data-stu-id="d2165-149">Create a login on HOST_B for HOST_A.</span></span>  
  
    ```  
    USE master;  
    CREATE LOGIN HOST_A_login WITH PASSWORD = '=Sample#2_Strong_Password2';  
    GO  
    ```  
  
2.  <span data-ttu-id="d2165-150">Crie um usuário para aquele logon.</span><span class="sxs-lookup"><span data-stu-id="d2165-150">Create a user for that login.</span></span>  
  
    ```  
    CREATE USER HOST_A_user FOR LOGIN HOST_A_login;  
    GO  
    ```  
  
3.  <span data-ttu-id="d2165-151">--Associe o certificado ao usuário.</span><span class="sxs-lookup"><span data-stu-id="d2165-151">Associate the certificate with the user.</span></span>  
  
    ```  
    CREATE CERTIFICATE HOST_A_cert  
       AUTHORIZATION HOST_A_user  
       FROM FILE = 'C:\HOST_A_cert.cer'  
    GO  
    ```  
  
4.  <span data-ttu-id="d2165-152">Conceda permissão CONNECT no logon para o ponto de extremidade de espelhamento remoto.</span><span class="sxs-lookup"><span data-stu-id="d2165-152">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
    ```  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_A_login];  
    GO  
    ```  
  
> [!IMPORTANT]  
>  <span data-ttu-id="d2165-153">Se tiver a intenção de executar em modo de alta segurança com failover automático, você deve repetir as mesmas etapas de configuração para configurar a testemunha para conexões de saída e de entrada.</span><span class="sxs-lookup"><span data-stu-id="d2165-153">If you intend to run in high-safety mode with automatic failover, you must repeat the same setup steps to configure the witness for outbound and inbound connections.</span></span> <span data-ttu-id="d2165-154">Quando uma testemunha está envolvida, a configuração de conexões de entrada e de saída requer a configuração de logons e usuários para a testemunha nos dois parceiros, e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="d2165-154">Setting up the inbound connections when a witness is involved requires that you set up logins and users for the witness on both of the partners and for both partners on the witness.</span></span>  
  
 <span data-ttu-id="d2165-155">Para obter mais informações, consulte [Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de entrada &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="d2165-155">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
### <a name="creating-the-mirror-database"></a><span data-ttu-id="d2165-156">Criando o banco de dados espelho</span><span class="sxs-lookup"><span data-stu-id="d2165-156">Creating the Mirror Database</span></span>  
 <span data-ttu-id="d2165-157">Para obter informações sobre como criar um banco de dados espelho, consulte [Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="d2165-157">For information on how to create a mirror database, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
###  <a name="configuring-the-mirroring-partners"></a><a name="ConfigureMirroringPartners"></a> <span data-ttu-id="d2165-158">Configurando os parceiros de espelhamento</span><span class="sxs-lookup"><span data-stu-id="d2165-158">Configuring the Mirroring Partners</span></span>  
  
1.  <span data-ttu-id="d2165-159">Na instância de servidor espelho em HOST_B, defina a instância de servidor em HOST_A como o parceiro (fazendo dele a instância de servidor principal inicial).</span><span class="sxs-lookup"><span data-stu-id="d2165-159">On the mirror server instance on HOST_B, set the server instance on HOST_A as the partner (making it the initial principal server instance).</span></span> <span data-ttu-id="d2165-160">Substitua um endereço de rede válido por `TCP://HOST_A.Mydomain.Corp.Adventure-Works``.com:7024`.</span><span class="sxs-lookup"><span data-stu-id="d2165-160">Substitute a valid network address for `TCP://HOST_A.Mydomain.Corp.Adventure-Works``.com:7024`.</span></span> <span data-ttu-id="d2165-161">Para obter mais informações, consulte [Especificar um endereço de rede do servidor &#40;Espelhamento de banco de dados&#41;](specify-a-server-network-address-database-mirroring.md).</span><span class="sxs-lookup"><span data-stu-id="d2165-161">For more information, see [Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md).</span></span>  
  
    ```  
    --At HOST_B, set server instance on HOST_A as partner (principal server):  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://HOST_A.Mydomain.Corp.Adventure-Works.com:7024';  
    GO  
    ```  
  
2.  <span data-ttu-id="d2165-162">Na instância de servidor principal em HOST_A, defina a instância de servidor em HOST_B como o parceiro (fazendo dele a instância de servidor espelho inicial).</span><span class="sxs-lookup"><span data-stu-id="d2165-162">On the principal server instance on HOST_A, set the server instance on HOST_B as the partner (making it the initial mirror server instance).</span></span> <span data-ttu-id="d2165-163">Substitua um endereço de rede válido por `TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024`.</span><span class="sxs-lookup"><span data-stu-id="d2165-163">Substitute a valid network address for `TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024`.</span></span>  
  
    ```  
    --At HOST_A, set server instance on HOST_B as partner (mirror server).  
    ALTER DATABASE AdventureWorks   
        SET PARTNER = 'TCP://HOST_B.Mydomain.Corp.Adventure-Works.com:7024';  
    GO  
    ```  
  
3.  <span data-ttu-id="d2165-164">Esse exemplo assume que a sessão estará sendo executada em modo de alto desempenho.</span><span class="sxs-lookup"><span data-stu-id="d2165-164">This example assumes that the session will be running in high-performance mode.</span></span> <span data-ttu-id="d2165-165">Para configurar esta sessão para modo de alto desempenho, na instância de servidor principal (em HOST_A), defina segurança de transação como OFF.</span><span class="sxs-lookup"><span data-stu-id="d2165-165">To configure this session for high-performance mode, on the principal server instance (on HOST_A), set transaction safety to OFF.</span></span>  
  
    ```  
    --Change to high-performance mode by turning off transacton safety.  
    ALTER DATABASE AdventureWorks   
        SET PARTNER SAFETY OFF  
    GO  
    ```  
  
    > [!NOTE]  
    >  <span data-ttu-id="d2165-166">Se você pretende executar em modo de alta segurança com failover automático, deixe a segurança da transação definida como completa (a configuração padrão) e adicione a testemunha assim que possível após a execução da segunda instrução SET Partner **' *`partner_server`* '** .</span><span class="sxs-lookup"><span data-stu-id="d2165-166">If you intend to run in high-safety mode with automatic failover, leave transaction safety set to FULL (the default setting) and add the witness as soon as possible after executing the second SET PARTNER **'*`partner_server`*'** statement.</span></span> <span data-ttu-id="d2165-167">Observe que a testemunha deve ser configurada primeiro para conexões de saída e de entrada.</span><span class="sxs-lookup"><span data-stu-id="d2165-167">Note that the witness must first be configured for outbound and inbound connections.</span></span>  
  
##  <a name="related-tasks"></a><a name="RelatedTasks"></a> <span data-ttu-id="d2165-168">Tarefas relacionadas</span><span class="sxs-lookup"><span data-stu-id="d2165-168">Related Tasks</span></span>  
  
-   [<span data-ttu-id="d2165-169">Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d2165-169">Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;</span></span>](prepare-a-mirror-database-for-mirroring-sql-server.md)  
  
-   [<span data-ttu-id="d2165-170">Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de entrada &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2165-170">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-inbound-connections.md)  
  
-   [<span data-ttu-id="d2165-171">Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de saída &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="d2165-171">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;</span></span>](database-mirroring-use-certificates-for-outbound-connections.md)  
  
-   [<span data-ttu-id="d2165-172">Gerenciamento de logons e trabalhos após a troca de funções &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d2165-172">Management of Logins and Jobs After Role Switching &#40;SQL Server&#41;</span></span>](../../sql-server/failover-clusters/management-of-logins-and-jobs-after-role-switching-sql-server.md)  
  
-   <span data-ttu-id="d2165-173">[Gerenciar metadados ao disponibilizar um banco de dados em outra instância do servidor &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="d2165-173">[Manage Metadata When Making a Database Available on Another Server Instance &#40;SQL Server&#41;](../../relational-databases/databases/manage-metadata-when-making-a-database-available-on-another-server.md) (SQL Server)</span></span>  
  
-   [<span data-ttu-id="d2165-174">Solução de problemas de configuração de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="d2165-174">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](troubleshoot-database-mirroring-configuration-sql-server.md)  
  
## <a name="see-also"></a><span data-ttu-id="d2165-175">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="d2165-175">See Also</span></span>  
 <span data-ttu-id="d2165-176">[Segurança de transporte para espelhamento de banco de dados e Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="d2165-176">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="d2165-177">[Especificar um endereço de rede do servidor &#40;espelhamento de banco de dados&#41;](specify-a-server-network-address-database-mirroring.md) </span><span class="sxs-lookup"><span data-stu-id="d2165-177">[Specify a Server Network Address &#40;Database Mirroring&#41;](specify-a-server-network-address-database-mirroring.md) </span></span>  
 <span data-ttu-id="d2165-178">[O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="d2165-178">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="d2165-179">[Usar certificados para um ponto de extremidade de espelhamento de banco de dados &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="d2165-179">[Use Certificates for a Database Mirroring Endpoint &#40;Transact-SQL&#41;](use-certificates-for-a-database-mirroring-endpoint-transact-sql.md) </span></span>  
 <span data-ttu-id="d2165-180">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="d2165-180">[ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) </span></span>  
 [<span data-ttu-id="d2165-181">Central de segurança do Mecanismo de Banco de Dados do SQL Server e Banco de Dados SQL do Azure</span><span class="sxs-lookup"><span data-stu-id="d2165-181">Security Center for SQL Server Database Engine and Azure SQL Database</span></span>](../../relational-databases/security/security-center-for-sql-server-database-engine-and-azure-sql-database.md)  
  
  
