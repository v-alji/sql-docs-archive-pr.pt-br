---
title: Permitir que um ponto de extremidade de espelhamento de banco de dados Use certificados para conexões de entrada (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- certificates [SQL Server], database mirroring
- inbound connections
- database mirroring [SQL Server], security
ms.assetid: 5d48bb98-61f0-4b99-8f1a-b53f831d63d0
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: c05397dfbd1740293c4b154ace1ed5704cec11a9
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570219"
---
# <a name="allow-a-database-mirroring-endpoint-to-use-certificates-for-inbound-connections-transact-sql"></a><span data-ttu-id="f6af4-102">Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de entrada (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="f6af4-102">Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections (Transact-SQL)</span></span>
  <span data-ttu-id="f6af4-103">Esse tópico descreve as etapas para configuração de instâncias de servidor a fim de usar certificados para autenticar conexões de entrada para espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f6af4-103">This topic describes the steps for configuring server instances to use certificates to authenticate inbound connections for database mirroring.</span></span> <span data-ttu-id="f6af4-104">Antes de poder configurar conexões de entrada, devem ser configuradas conexões de saída em cada instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="f6af4-104">Before you can set up inbound connections, you must configure outbound connections on each server instance.</span></span> <span data-ttu-id="f6af4-105">Para obter mais informações, consulte [Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de saída &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="f6af4-105">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
 <span data-ttu-id="f6af4-106">O processo de configuração conexões de entrada envolve as seguintes etapas gerais:</span><span class="sxs-lookup"><span data-stu-id="f6af4-106">The process of configuring inbound connections, involves the following general steps:</span></span>  
  
1.  <span data-ttu-id="f6af4-107">Crie um logon para outro sistema.</span><span class="sxs-lookup"><span data-stu-id="f6af4-107">Create a login for other system.</span></span>  
  
2.  <span data-ttu-id="f6af4-108">Crie um usuário para aquele logon.</span><span class="sxs-lookup"><span data-stu-id="f6af4-108">Create a user for that login.</span></span>  
  
3.  <span data-ttu-id="f6af4-109">Obtenha o certificado para o ponto de extremidade de espelhamento da outra instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="f6af4-109">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
4.  <span data-ttu-id="f6af4-110">Associe o certificado ao usuário criado na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="f6af4-110">Associate the certificate with the user created in step 2.</span></span>  
  
5.  <span data-ttu-id="f6af4-111">Conceda permissão CONNECT no logon para aquele ponto de extremidade de espelhamento.</span><span class="sxs-lookup"><span data-stu-id="f6af4-111">Grant CONNECT permission on the login for that mirroring endpoint.</span></span>  
  
 <span data-ttu-id="f6af4-112">Se houver uma testemunha, deve-se configurar também conexões de entrada para ela.</span><span class="sxs-lookup"><span data-stu-id="f6af4-112">If there is a witness, you must also set up inbound connections for it.</span></span> <span data-ttu-id="f6af4-113">Isso requer configuração de logons, usuários e certificados para a testemunha nos dois parceiros, e vice-versa.</span><span class="sxs-lookup"><span data-stu-id="f6af4-113">This requires setting up logins, users, and certificates for the witness on both of the partners, and vice versa.</span></span>  
  
 <span data-ttu-id="f6af4-114">O procedimento a seguir descreve em detalhes essas etapas.</span><span class="sxs-lookup"><span data-stu-id="f6af4-114">The following procedure describes these steps in detail.</span></span> <span data-ttu-id="f6af4-115">Para cada etapa, o processo fornece um exemplo para configurar a instância do servidor em um sistema chamado de HOST_A.</span><span class="sxs-lookup"><span data-stu-id="f6af4-115">For each step, the procedure provides an example for configuring a server instance on a system named HOST_A.</span></span> <span data-ttu-id="f6af4-116">A seção de exemplo mostra as mesmas etapas para uma outra instância do servidor em um sistema chamado de HOST_B.</span><span class="sxs-lookup"><span data-stu-id="f6af4-116">The accompanying Example section demonstrates the same steps for another server instance on a system named HOST_B.</span></span>  
  
### <a name="to-configure-server-instances-for-inbound-mirroring-connections-on-host_a"></a><span data-ttu-id="f6af4-117">Para configurar instâncias de servidor para conexões de espelhamento de entrada (em HOST_A)</span><span class="sxs-lookup"><span data-stu-id="f6af4-117">To configure server instances for inbound mirroring connections (on HOST_A)</span></span>  
  
1.  <span data-ttu-id="f6af4-118">Crie um logon para o outro sistema.</span><span class="sxs-lookup"><span data-stu-id="f6af4-118">Create a login for the other system.</span></span>  
  
     <span data-ttu-id="f6af4-119">O exemplo a seguir cria um logon para o sistema, HOST_B, no banco de dados **master** da instância do servidor em HOST_A; nesse exemplo, o logon é chamado de `HOST_B_login`.</span><span class="sxs-lookup"><span data-stu-id="f6af4-119">The following example creates a login for the system, HOST_B, in the **master** database of the server instance on HOST_A; in this example, the login is named `HOST_B_login`.</span></span> <span data-ttu-id="f6af4-120">Substitua a senha de exemplo por uma senha de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="f6af4-120">Substitute a password of your own for the sample password.</span></span>  
  
    ```sql  
    USE master;  
    CREATE LOGIN HOST_B_login   
       WITH PASSWORD = '1Sample_Strong_Password!@#';  
    GO  
    ```  
  
     <span data-ttu-id="f6af4-121">Para obter mais informações, veja [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f6af4-121">For more information, see [CREATE LOGIN &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-login-transact-sql).</span></span>  
  
     <span data-ttu-id="f6af4-122">Para exibir os logons nessa instância de servidor, é possível usar a seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f6af4-122">To view the logins on this server instance, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.server_principals;  
    ```  
  
     <span data-ttu-id="f6af4-123">Para obter mais informações, veja [sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f6af4-123">For more information, see [sys.server_principals &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-server-principals-transact-sql).</span></span>  
  
2.  <span data-ttu-id="f6af4-124">Crie um usuário para aquele logon.</span><span class="sxs-lookup"><span data-stu-id="f6af4-124">Create a user for that login.</span></span>  
  
     <span data-ttu-id="f6af4-125">O exemplo a seguir cria um usuário, `HOST_B_user`, para o logon criado na etapa anterior.</span><span class="sxs-lookup"><span data-stu-id="f6af4-125">The following example creates a user, `HOST_B_user`, for the login created in the preceding step.</span></span>  
  
    ```sql  
    USE master;  
    CREATE USER HOST_B_user FOR LOGIN HOST_B_login;  
    GO  
    ```  
  
     <span data-ttu-id="f6af4-126">Para obter mais informações, consulte [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f6af4-126">For more information, see [CREATE USER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-user-transact-sql).</span></span>  
  
     <span data-ttu-id="f6af4-127">Para exibir os usuários nessa instância de servidor é possível usar a seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f6af4-127">To view the users on this server instance, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.sysusers;  
    ```  
  
     <span data-ttu-id="f6af4-128">Para obter mais informações, veja [sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f6af4-128">For more information, see [sys.sysusers &#40;Transact-SQL&#41;](/sql/relational-databases/system-compatibility-views/sys-sysusers-transact-sql).</span></span>  
  
3.  <span data-ttu-id="f6af4-129">Obtenha o certificado para o ponto de extremidade de espelhamento da outra instância do servidor.</span><span class="sxs-lookup"><span data-stu-id="f6af4-129">Obtain the certificate for the mirroring endpoint of the other server instance.</span></span>  
  
     <span data-ttu-id="f6af4-130">Se ainda não tiver feito isso ao configurar as conexões de saída, obtenha uma cópia do certificado para o ponto de extremidade da instância de servidor remoto.</span><span class="sxs-lookup"><span data-stu-id="f6af4-130">If you have not already done so when configuring outbound connections, obtain a copy of the certificate for the mirroring endpoint of the remote server instance.</span></span> <span data-ttu-id="f6af4-131">Para fazer isso, faça backup do certificado na instância de servidor, conforme descrito em [Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de saída &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="f6af4-131">To do this, back up the certificate on that server instance as described in [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span> <span data-ttu-id="f6af4-132">Ao copiar um certificado para outro sistema, use um método de cópia seguro.</span><span class="sxs-lookup"><span data-stu-id="f6af4-132">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="f6af4-133">Seja extremamente cauteloso para manter todos os seus certificados em segurança.</span><span class="sxs-lookup"><span data-stu-id="f6af4-133">Be extremely careful to keep all of your certificates secure.</span></span>  
  
     <span data-ttu-id="f6af4-134">Para obter mais informações, veja [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f6af4-134">For more information, see [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span></span>  
  
4.  <span data-ttu-id="f6af4-135">Associe o certificado ao usuário criado na etapa 2.</span><span class="sxs-lookup"><span data-stu-id="f6af4-135">Associate the certificate with the user created in step 2.</span></span>  
  
     <span data-ttu-id="f6af4-136">O exemplo a seguir associa o certificado de HOST_B a seu usuário em HOST_A.</span><span class="sxs-lookup"><span data-stu-id="f6af4-136">The following example, associates the certificate of HOST_B with its user on HOST_A.</span></span>  
  
    ```sql  
    USE master;  
    CREATE CERTIFICATE HOST_B_cert  
       AUTHORIZATION HOST_B_user  
       FROM FILE = 'C:\HOST_B_cert.cer'  
    GO  
    ```  
  
     <span data-ttu-id="f6af4-137">Para obter mais informações, consulte [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f6af4-137">For more information, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="f6af4-138">Para exibir os certificados nessa instância de servidor, use a seguinte instrução [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f6af4-138">To view the certificates on this server instance, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statement:</span></span>  
  
    ```sql  
    SELECT * FROM sys.certificates;  
    ```  
  
     <span data-ttu-id="f6af4-139">Para obter mais informações, veja [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f6af4-139">For more information, see [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span></span>  
  
5.  <span data-ttu-id="f6af4-140">Conceda permissão CONNECT no logon para o ponto de extremidade de espelhamento remoto.</span><span class="sxs-lookup"><span data-stu-id="f6af4-140">Grant CONNECT permission on the login for the remote mirroring endpoint.</span></span>  
  
     <span data-ttu-id="f6af4-141">Por exemplo, para conceder permissão em HOST_A para a instância de servidor remoto em HOST_B para conexão com seu logon local – ou seja, para conexão com `HOST_B_login`– use as seguintes instruções [!INCLUDE[tsql](../../includes/tsql-md.md)]:</span><span class="sxs-lookup"><span data-stu-id="f6af4-141">For example, to grant permission on HOST_A to the remote server instance on HOST_B to connect to its local login-that is, to connect to `HOST_B_login`-use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```sql  
    USE master;  
    GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO [HOST_B_login];  
    GO  
    ```  
  
     <span data-ttu-id="f6af4-142">Para obter mais informações, consulte [Permissões GRANT do ponto de extremidade &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f6af4-142">For more information, see [GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql).</span></span>  
  
 <span data-ttu-id="f6af4-143">Isso completa a configuração da autenticação de certificado para que HOST_B faça o logon para HOST_A.</span><span class="sxs-lookup"><span data-stu-id="f6af4-143">This completes setting up certificate authentication for HOST_B to log in to HOST_A.</span></span>  
  
 <span data-ttu-id="f6af4-144">Agora é preciso executar as etapas de entrada equivalentes para HOST_A em HOST_B.</span><span class="sxs-lookup"><span data-stu-id="f6af4-144">You now need to perform the equivalent inbound steps for HOST_A on HOST_B.</span></span> <span data-ttu-id="f6af4-145">Essas etapas são ilustradas na porção de entrada do exemplo, na seção Exemplo, abaixo.</span><span class="sxs-lookup"><span data-stu-id="f6af4-145">These steps are illustrated in the inbound portion of the example in the Example section, below.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f6af4-146">Exemplo</span><span class="sxs-lookup"><span data-stu-id="f6af4-146">Example</span></span>  
 <span data-ttu-id="f6af4-147">O exemplo a seguir demonstra como configurar HOST_B para conexões de entrada.</span><span class="sxs-lookup"><span data-stu-id="f6af4-147">The following example demonstrates configuring HOST_B for inbound connections.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="f6af4-148">Este exemplo usa um arquivo de certificado que contém o certificado HOST_A criado por um snippet de código em [Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de saída &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="f6af4-148">This example uses a certificate file containing the HOST_A certificate that is created by a code snippet in [Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-outbound-connections.md).</span></span>  
  
```sql  
USE master;  
--On HOST_B, create a login for HOST_A.  
CREATE LOGIN HOST_A_login WITH PASSWORD = 'AStrongPassword!@#';  
GO  
--Create a user, HOST_A_user, for that login.  
CREATE USER HOST_A_user FOR LOGIN HOST_A_login;  
GO  
--Obtain HOST_A certificate. (See the note   
--   preceding this example.)  
--Asscociate this certificate with the user, HOST_A_user.  
CREATE CERTIFICATE HOST_A_cert  
   AUTHORIZATION HOST_A_user  
   FROM FILE = 'C:\HOST_A_cert.cer';  
GO  
--Grant CONNECT permission for the server instance on HOST_A.  
GRANT CONNECT ON ENDPOINT::Endpoint_Mirroring TO HOST_A_login;  
GO  
```  
  
 <span data-ttu-id="f6af4-149">Se você pretende executar em modo de alta segurança com failover automático, você deve repetir as mesmas etapas de configuração para configurar a testemunha para conexões de saída e de entrada.</span><span class="sxs-lookup"><span data-stu-id="f6af4-149">If you intend to run in high-safety mode with automatic failover, you must repeat the same set up steps to configure the witness for outbound and inbound connections.</span></span>  
  
 <span data-ttu-id="f6af4-150">Para obter informações sobre como criar um banco de dados espelho, incluindo um exemplo de Transact-SQL, veja [Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="f6af4-150">For information on creating a mirror database, including a Transact-SQL example, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="f6af4-151">Para obter um exemplo de Transact-SQL para estabelecer uma sessão de modo de alto desempenho, confira [Exemplo: Configurar o espelhamento de banco de dados usando certificados &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="f6af4-151">For a Transact-SQL example of establishing a high-performance mode session, see [Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="f6af4-152">Segurança do .NET Framework</span><span class="sxs-lookup"><span data-stu-id="f6af4-152">.NET Framework Security</span></span>  
 <span data-ttu-id="f6af4-153">Ao copiar um certificado para outro sistema, use um método de cópia seguro.</span><span class="sxs-lookup"><span data-stu-id="f6af4-153">When copying a certificate to another system, use a secure copy method.</span></span> <span data-ttu-id="f6af4-154">Seja extremamente cauteloso para manter todos os seus certificados em segurança.</span><span class="sxs-lookup"><span data-stu-id="f6af4-154">Be extremely careful to keep all of your certificates secure.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f6af4-155">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f6af4-155">See Also</span></span>  
 <span data-ttu-id="f6af4-156">[Segurança de transporte para espelhamento de banco de dados e Grupos de Disponibilidade AlwaysOn &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span><span class="sxs-lookup"><span data-stu-id="f6af4-156">[Transport Security for Database Mirroring and AlwaysOn Availability Groups &#40;SQL Server&#41;](transport-security-database-mirroring-always-on-availability.md) </span></span>  
 <span data-ttu-id="f6af4-157">[Permissões GRANT do ponto de extremidade &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="f6af4-157">[GRANT Endpoint Permissions &#40;Transact-SQL&#41;](/sql/t-sql/statements/grant-endpoint-permissions-transact-sql) </span></span>  
 <span data-ttu-id="f6af4-158">[Configurar um banco de dados espelho criptografado](set-up-an-encrypted-mirror-database.md) </span><span class="sxs-lookup"><span data-stu-id="f6af4-158">[Set Up an Encrypted Mirror Database](set-up-an-encrypted-mirror-database.md) </span></span>  
 <span data-ttu-id="f6af4-159">[O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="f6af4-159">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 [<span data-ttu-id="f6af4-160">Solução de problemas de configuração de espelhamento de banco de dados &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="f6af4-160">Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;</span></span>](troubleshoot-database-mirroring-configuration-sql-server.md)  
  
  
