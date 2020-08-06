---
title: Permitir que um ponto de extremidade de espelhamento de banco de dados Use certificados para conexões de saída (Transact-SQL) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: high-availability
ms.topic: conceptual
helpviewer_keywords:
- certificates [SQL Server], database mirroring
- outbound connections [SQL Server]
- database mirroring [SQL Server], security
ms.assetid: 464c9096-10d6-4c5e-8bb1-19acba27ad9e
author: MikeRayMSFT
ms.author: mikeray
ms.openlocfilehash: f380f268f8d0f8d033db9c28f83d066d3f134571
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87570218"
---
# <a name="allow-a-database-mirroring-endpoint-to-use-certificates-for-outbound-connections-transact-sql"></a><span data-ttu-id="eb1b5-102">Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de saída (Transact-SQL)</span><span class="sxs-lookup"><span data-stu-id="eb1b5-102">Allow a Database Mirroring Endpoint to Use Certificates for Outbound Connections (Transact-SQL)</span></span>
  <span data-ttu-id="eb1b5-103">Este tópico descreve os passos para configurar instâncias de servidor para usar certificados para autenticar conexões de saída para espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-103">This topic describes the steps for configuring server instances to use certificates to authenticate outbound connections for database mirroring.</span></span> <span data-ttu-id="eb1b5-104">A configuração de conexão de saída deve ser feita antes que você possa configurar conexões de entrada.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-104">Outbound connection configuration must be done before you can set up inbound connections.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb1b5-105">Todas as conexões de espelhamento em uma instância do servidor usam um único ponto de extremidade de espelhamento do banco de dados e você deve especificar o método de autenticação da instância do servidor quando criar o ponto de extremidade.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-105">All mirroring connections on a server instance use a single database mirroring endpoint, and you must specify the authentication method of the server instance when you create the endpoint.</span></span>  
  
 <span data-ttu-id="eb1b5-106">O processo de configurar conexões de saída envolve os seguintes passos gerais:</span><span class="sxs-lookup"><span data-stu-id="eb1b5-106">The process of configuring outbound connections, involves the following general steps:</span></span>  
  
1.  <span data-ttu-id="eb1b5-107">No banco de dados **mestre** , crie um banco de dados chave mestre.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-107">In the **master** database, create a database Master Key.</span></span>  
  
2.  <span data-ttu-id="eb1b5-108">No banco de dados **mestre** , crie um certificado criptografado na instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-108">In the **master** database, create an encrypted certificate on the server instance.</span></span>  
  
3.  <span data-ttu-id="eb1b5-109">Crie um ponto de extremidade para a instância do servidor que usa seu certificado.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-109">Create an endpoint for the server instance using its certificate.</span></span>  
  
4.  <span data-ttu-id="eb1b5-110">Faça o backup do certificado em um arquivo e o copie-o com segurança para outro sistema ou sistemas.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-110">Back up the certificate to a file and securely copy it to the other system or systems.</span></span>  
  
 <span data-ttu-id="eb1b5-111">Você deve completar essas etapas para cada parceiro e para a testemunha, se houver.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-111">You must complete these steps for each partner and the witness, if there is one.</span></span>  
  
 <span data-ttu-id="eb1b5-112">O procedimento a seguir descreve em detalhes essas etapas.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-112">The following procedure describes these steps in detail.</span></span> <span data-ttu-id="eb1b5-113">Para cada etapa, o processo fornece um exemplo para configurar a instância do servidor em um sistema chamado de HOST_A.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-113">For each step, the procedure provides an example for configuring a server instance on a system named HOST_A.</span></span> <span data-ttu-id="eb1b5-114">A seção de exemplo mostra as mesmas etapas para uma outra instância do servidor em um sistema chamado de HOST_B.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-114">The accompanying Example section demonstrates the same steps for another server instance on a system named HOST_B.</span></span>  
  
## <a name="procedure"></a><span data-ttu-id="eb1b5-115">Procedimento</span><span class="sxs-lookup"><span data-stu-id="eb1b5-115">Procedure</span></span>  
  
#### <a name="to-configure-server-instances-for-outbound-mirroring-connections-on-host_a"></a><span data-ttu-id="eb1b5-116">Para configurar as instâncias de servidor para espelhamento de conexões de saída (No HOST_A)</span><span class="sxs-lookup"><span data-stu-id="eb1b5-116">To configure server instances for outbound mirroring connections (On HOST_A)</span></span>  
  
1.  <span data-ttu-id="eb1b5-117">No banco de dados **mestre** , crie o banco de dados chave mestre, se nenhum existir.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-117">On the **master** database, create the database Master Key, if none exists.</span></span> <span data-ttu-id="eb1b5-118">Para exibir as chaves existentes para um banco de dados, use a exibição do catálogo [sys.symmetric_keys](/sql/relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="eb1b5-118">To view the existing keys for a database, use the [sys.symmetric_keys](/sql/relational-databases/system-catalog-views/sys-symmetric-keys-transact-sql) catalog view.</span></span>  
  
     <span data-ttu-id="eb1b5-119">Para criar o banco de dados chave mestre, use o seguinte comando [!INCLUDE[tsql](../../includes/tsql-md.md)] :</span><span class="sxs-lookup"><span data-stu-id="eb1b5-119">To create the database Master Key, use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] command:</span></span>  
  
    ```  
    CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<1_Strong_Password!>';  
    GO  
    ```  
  
     <span data-ttu-id="eb1b5-120">Use uma senha exclusiva forte e a registre em um lugar seguro.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-120">Use a unique, strong password, and record it in a safe place.</span></span>  
  
     <span data-ttu-id="eb1b5-121">Para obter mais informações, veja [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) e [Criar uma chave mestra de banco de dados](../../relational-databases/security/encryption/create-a-database-master-key.md).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-121">For more information, see [CREATE MASTER KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-master-key-transact-sql) and [Create a Database Master Key](../../relational-databases/security/encryption/create-a-database-master-key.md).</span></span>  
  
2.  <span data-ttu-id="eb1b5-122">No banco de dados **master** , crie um certificado criptografado na instância de servidor a ser usado nas suas conexões de saída para espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-122">In the **master** database, create an encrypted certificate on the server instance to use for its outbound connections for database mirroring.</span></span>  
  
     <span data-ttu-id="eb1b5-123">Por exemplo, para criar um certificado para o sistema HOST_A.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-123">For example, to create a certificate for the HOST_A system.</span></span>  
  
    > [!IMPORTANT]  
    >  <span data-ttu-id="eb1b5-124">Se você pretende usar o certificado por mais de um ano, especifique a data de expiração em hora UTC usando a opção EXPIRY_DATE em sua instrução CREATE CERTIFICATE.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-124">If you intend to use the certificate for more than one year, specify the expiry date in UTC time by using the EXPIRY_DATE option in your CREATE CERTIFICATE statement.</span></span> <span data-ttu-id="eb1b5-125">Além disso, é recomendável que você use o SQL Server Management Studio para criar uma regra de gerenciamento baseado em políticas para alertá-lo quando seus certificados estiverem expirando.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-125">Also, we recommend that you use SQL Server Management Studio to create a Policy-Based Management rule to alert you when your certificates are expiring.</span></span> <span data-ttu-id="eb1b5-126">Usando a caixa de diálogo **Criar Nova Condição** do Gerenciamento de Política, crie essa regra no campo **@ExpirationDate** da faceta **Certificado** .</span><span class="sxs-lookup"><span data-stu-id="eb1b5-126">Using the Policy Management **Create New Condition** dialog box, create this rule on the **@ExpirationDate** field of the **Certificate** facet.</span></span> <span data-ttu-id="eb1b5-127">Para obter mais informações, veja [Administrar servidores usando o gerenciamento baseado em políticas](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md) e [Protegendo o SQL Server](../../relational-databases/security/securing-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-127">For more information, see [Administer Servers by Using Policy-Based Management](../../relational-databases/policy-based-management/administer-servers-by-using-policy-based-management.md) and [Securing SQL Server](../../relational-databases/security/securing-sql-server.md).</span></span>  
  
    ```  
    USE master;  
    CREATE CERTIFICATE HOST_A_cert   
       WITH SUBJECT = 'HOST_A certificate for database mirroring',   
       EXPIRY_DATE = '11/30/2013';  
    GO  
    ```  
  
     <span data-ttu-id="eb1b5-128">Para obter mais informações, consulte [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-128">For more information, see [CREATE CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="eb1b5-129">Para exibir os certificados no banco de dados **mestre** , você pode usar as instruções [!INCLUDE[tsql](../../includes/tsql-md.md)] seguintes:</span><span class="sxs-lookup"><span data-stu-id="eb1b5-129">To view the certificates in the **master** database, you can use the following [!INCLUDE[tsql](../../includes/tsql-md.md)] statements:</span></span>  
  
    ```  
    USE master;  
    SELECT * FROM sys.certificates;  
    ```  
  
     <span data-ttu-id="eb1b5-130">Para obter mais informações, veja [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-130">For more information, see [sys.certificates &#40;Transact-SQL&#41;](/sql/relational-databases/system-catalog-views/sys-certificates-transact-sql).</span></span>  
  
3.  <span data-ttu-id="eb1b5-131">Assegure que o ponto de extremidade do espelhamento de banco de dados exista em cada uma das instâncias de servidor.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-131">Ensure that the database mirroring endpoint exist on each of the server instances.</span></span>  
  
     <span data-ttu-id="eb1b5-132">Se um ponto de extremidade do espelhamento de banco de dados já existir para a instância de servidor, você deveria usar de novo aquele ponto de extremidade para qualquer outra sessão que você estabeleça na instância de servidor.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-132">If a database mirroring endpoint already exists for the server instance, you should reuse that endpoint for any other sessions you establish on the server instance.</span></span> <span data-ttu-id="eb1b5-133">Para determinar se um ponto de extremidade do espelhamento de banco de dados existe em uma instância de servidor e exibir sua configuração, use a instrução seguinte:</span><span class="sxs-lookup"><span data-stu-id="eb1b5-133">To determine whether a database mirroring endpoint exists on a server instance and to view its configuration, use the following statement:</span></span>  
  
    ```  
    SELECT name, role_desc, state_desc, connection_auth_desc, encryption_algorithm_desc   
       FROM sys.database_mirroring_endpoints;  
    ```  
  
     <span data-ttu-id="eb1b5-134">Se nenhum ponto de extremidade existir, crie um ponto de extremidade que usa este certificado para conexões de saída e que usa as credenciais do certificado para verificação no outro sistema.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-134">If no endpoint exists, create an endpoint that uses this certificate for outbound connections and that uses the certificate's credentials for verification on the other system.</span></span> <span data-ttu-id="eb1b5-135">Este é um ponto de extremidade em todo servidor que é usado por todas as sessões de espelhamento nas quais a instância de servidor participa.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-135">This is a server-wide endpoint that is used by all mirroring sessions in which the server instance participates.</span></span>  
  
     <span data-ttu-id="eb1b5-136">Por exemplo, para criar um espelhamento de ponto de extremidade para a instância de servidor de exemplo em HOST_A.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-136">For example, to create a mirroring endpoint for the example server instance on HOST_A.</span></span>  
  
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
  
     <span data-ttu-id="eb1b5-137">Para obter mais informações, veja [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-137">For more information, see [CREATE ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-endpoint-transact-sql).</span></span>  
  
4.  <span data-ttu-id="eb1b5-138">Faça o backup do certificado e o copie ao outro sistema ou sistemas.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-138">Back up the certificate and copy it to the other system or systems.</span></span> <span data-ttu-id="eb1b5-139">Isto é necessário para configurar as conexões de entrada no outro sistema.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-139">This is necessary in order to configure inbound connections on the other system.</span></span>  
  
    ```  
    BACKUP CERTIFICATE HOST_A_cert TO FILE = 'C:\HOST_A_cert.cer';  
    GO  
    ```  
  
     <span data-ttu-id="eb1b5-140">Para obter mais informações, veja [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-140">For more information, see [BACKUP CERTIFICATE &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-certificate-transact-sql).</span></span>  
  
     <span data-ttu-id="eb1b5-141">Copie este certificado usando qualquer método seguro de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-141">Copy this certificate using any secure method you choose.</span></span> <span data-ttu-id="eb1b5-142">Seja extremamente cauteloso para manter todos os seus certificados em segurança.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-142">Be extremely careful to keep all of your certificates secure.</span></span>  
  
 <span data-ttu-id="eb1b5-143">O código de exemplo nos passos precedentes configura conexões de saída no HOST_A.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-143">The example code in the preceding steps configure outbound connections on HOST_A.</span></span>  
  
 <span data-ttu-id="eb1b5-144">Você precisa realizar os passos de saída equivalentes para o HOST_B.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-144">You now need to perform the equivalent outbound steps for HOST_B.</span></span> <span data-ttu-id="eb1b5-145">Esses passos estão ilustrados na seguinte seção de exemplo.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-145">These steps are illustrated in the following Example section.</span></span>  
  
## <a name="example"></a><span data-ttu-id="eb1b5-146">Exemplo</span><span class="sxs-lookup"><span data-stu-id="eb1b5-146">Example</span></span>  
 <span data-ttu-id="eb1b5-147">O exemplo seguinte demonstra como configurar o HOST_B para conexões de saída.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-147">The following example demonstrates configuring HOST_B for outbound connections.</span></span>  
  
```  
USE master;  
--Create the database Master Key, if needed.  
CREATE MASTER KEY ENCRYPTION BY PASSWORD = '<Strong_Password_#2>';  
GO  
-- Make a certifcate on HOST_B server instance.  
CREATE CERTIFICATE HOST_B_cert   
   WITH SUBJECT = 'HOST_B certificate for database mirroring',   
   EXPIRY_DATE = '11/30/2013';  
GO  
--Create a mirroring endpoint for the server instance on HOST_B.  
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
--Backup HOST_B certificate.  
BACKUP CERTIFICATE HOST_B_cert TO FILE = 'C:\HOST_B_cert.cer';  
GO   
--Using any secure copy method, copy C:\HOST_B_cert.cer to HOST_A.  
```  
  
 <span data-ttu-id="eb1b5-148">Copie o certificado ao outro sistema usando qualquer método seguro de sua escolha.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-148">Copy the certificate to the other system using any secure method you choose.</span></span> <span data-ttu-id="eb1b5-149">Seja extremamente cauteloso para manter todos os seus certificados em segurança.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-149">Be extremely careful to keep all of your certificates secure.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="eb1b5-150">Depois que você tiver configurado as conexões de saída, você deve configurar as conexões de entrada em cada instância de servidor para a outra instância ou instâncias de servidor.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-150">After you set up outbound connections, you must configure inbound connections on each server instance for the other server instance or instances.</span></span> <span data-ttu-id="eb1b5-151">Para obter mais informações, consulte [Permitir que um ponto de extremidade de espelhamento de banco de dados use certificados para conexões de entrada &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-151">For more information, see [Allow a Database Mirroring Endpoint to Use Certificates for Inbound Connections &#40;Transact-SQL&#41;](database-mirroring-use-certificates-for-inbound-connections.md).</span></span>  
  
 <span data-ttu-id="eb1b5-152">Para obter informações sobre como criar um banco de dados espelho, incluindo um exemplo de Transact-SQL, veja [Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-152">For information on creating a mirror database, including a Transact-SQL example, see [Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md).</span></span>  
  
 <span data-ttu-id="eb1b5-153">Para obter um exemplo de Transact-SQL para estabelecer uma sessão de modo de alto desempenho, confira [Exemplo: Configurar o espelhamento de banco de dados usando certificados &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span><span class="sxs-lookup"><span data-stu-id="eb1b5-153">For a Transact-SQL example of establishing a high-performance mode session, see [Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md).</span></span>  
  
## <a name="net-framework-security"></a><span data-ttu-id="eb1b5-154">Segurança do .NET Framework</span><span class="sxs-lookup"><span data-stu-id="eb1b5-154">.NET Framework Security</span></span>  
 <span data-ttu-id="eb1b5-155">A menos que você possa garantir que sua rede está segura, recomendamos o uso de criptografia para conexões de espelhamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-155">Unless you can guarantee that your network is secure, we recommend that you use encryption for database mirroring connections.</span></span>  
  
 <span data-ttu-id="eb1b5-156">Ao copiar um certificado para outro sistema, use um método de cópia seguro.</span><span class="sxs-lookup"><span data-stu-id="eb1b5-156">When copying a certificate to another system, use a secure copy method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb1b5-157">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eb1b5-157">See Also</span></span>  
 <span data-ttu-id="eb1b5-158">[Escolher um algoritmo de criptografia](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span><span class="sxs-lookup"><span data-stu-id="eb1b5-158">[Choose an Encryption Algorithm](../../relational-databases/security/encryption/choose-an-encryption-algorithm.md) </span></span>  
 <span data-ttu-id="eb1b5-159">[Preparar um banco de dados espelho para espelhamento &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eb1b5-159">[Prepare a Mirror Database for Mirroring &#40;SQL Server&#41;](prepare-a-mirror-database-for-mirroring-sql-server.md) </span></span>  
 <span data-ttu-id="eb1b5-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span><span class="sxs-lookup"><span data-stu-id="eb1b5-160">[ALTER ENDPOINT &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-endpoint-transact-sql) </span></span>  
 <span data-ttu-id="eb1b5-161">[Exemplo: Configurar o espelhamento de banco de dados usando certificados &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md) </span><span class="sxs-lookup"><span data-stu-id="eb1b5-161">[Example: Setting Up Database Mirroring Using Certificates &#40;Transact-SQL&#41;](example-setting-up-database-mirroring-using-certificates-transact-sql.md) </span></span>  
 <span data-ttu-id="eb1b5-162">[O ponto de extremidade de espelhamento de banco de dados &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eb1b5-162">[The Database Mirroring Endpoint &#40;SQL Server&#41;](the-database-mirroring-endpoint-sql-server.md) </span></span>  
 <span data-ttu-id="eb1b5-163">[Solução de problemas de configuração de espelhamento de banco de dados &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="eb1b5-163">[Troubleshoot Database Mirroring Configuration &#40;SQL Server&#41;](troubleshoot-database-mirroring-configuration-sql-server.md) </span></span>  
 [<span data-ttu-id="eb1b5-164">Configurar um banco de dados espelho criptografado</span><span class="sxs-lookup"><span data-stu-id="eb1b5-164">Set Up an Encrypted Mirror Database</span></span>](set-up-an-encrypted-mirror-database.md)  
  
  
