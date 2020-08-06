---
title: Habilitar TDE usando EKM | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- encryption [SQL Server], TDE using an EKM
- TDE, EKM how to
- EKM, TDE how to
- Transparent Data Encryption, using EKM
ms.assetid: b892e7a7-95bd-4903-bf54-55ce08e225af
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: e659c5ff0245fdb17192b845eafc60badf5e295e
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87685501"
---
# <a name="enable-tde-using-ekm"></a><span data-ttu-id="9a454-102">Habilitar a TDE usando EKM</span><span class="sxs-lookup"><span data-stu-id="9a454-102">Enable TDE Using EKM</span></span>
  <span data-ttu-id="9a454-103">Este tópico descreve como habilitar TDE (criptografia de dados transparente) no [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] para proteger uma chave de criptografia de banco de dados usando uma chave assimétrica armazenada em um módulo EKM (gerenciamento de chave extensível) com [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a454-103">This topic describes how to enable transparent data encryption (TDE) in [!INCLUDE[ssCurrent](../../../includes/sscurrent-md.md)] to protect a database encryption key by using an asymmetric key stored in an extensible key management (EKM) module with [!INCLUDE[tsql](../../../includes/tsql-md.md)].</span></span>  
  
 <span data-ttu-id="9a454-104">A TDE criptografa o armazenamento de um banco de dados inteiro usando uma chave simétrica chamada de chave de criptografia de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9a454-104">TDE encrypts the storage of an entire database by using a symmetric key called the database encryption key.</span></span> <span data-ttu-id="9a454-105">Também é possível proteger a chave de criptografia do banco de dados através do uso de um certificado protegido pela chave mestra do banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="9a454-105">The database encryption key can also be protected using a certificate which is protected by the database master key of the master database.</span></span> <span data-ttu-id="9a454-106">Para obter mais informações sobre como proteger a chave de criptografia do banco de dados usando a chave mestra de banco de dados, veja [TDE &#40;Transparent Data Encryption&#41;](transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="9a454-106">For more information about protecting the database encryption key by using the database master key, see [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md).</span></span> <span data-ttu-id="9a454-107">Para obter informações sobre como configurar a TDE quando o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] está em execução em uma VM do Azure, veja [Gerenciamento extensível de chaves usando o Cofre de Chaves do Azure &#40;SQL Server&#41;](extensible-key-management-using-azure-key-vault-sql-server.md).</span><span class="sxs-lookup"><span data-stu-id="9a454-107">For information about configuring TDE when [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] is running on an Azure VM, see [Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;](extensible-key-management-using-azure-key-vault-sql-server.md).</span></span>  
  
 <span data-ttu-id="9a454-108">**Neste tópico**</span><span class="sxs-lookup"><span data-stu-id="9a454-108">**In This Topic**</span></span>  
  
-   <span data-ttu-id="9a454-109">**Antes de começar:**</span><span class="sxs-lookup"><span data-stu-id="9a454-109">**Before you begin:**</span></span>  
  
     [<span data-ttu-id="9a454-110">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="9a454-110">Limitations and Restrictions</span></span>](#Restrictions)  
  
     [<span data-ttu-id="9a454-111">Segurança</span><span class="sxs-lookup"><span data-stu-id="9a454-111">Security</span></span>](#Security)  
  
-   [<span data-ttu-id="9a454-112">Para habilitar TDE usando EKM, usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9a454-112">To enable TDE using EKM, using Transact-SQL</span></span>](#TsqlProcedure)  
  
##  <a name="before-you-begin"></a><a name="BeforeYouBegin"></a> <span data-ttu-id="9a454-113">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="9a454-113">Before You Begin</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="Restrictions"></a> <span data-ttu-id="9a454-114">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="9a454-114">Limitations and Restrictions</span></span>  
  
-   <span data-ttu-id="9a454-115">Você deve ser um usuário com altos privilégios (como um administrador do sistema) para criar uma chave de criptografia de banco de dados e criptografar um banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9a454-115">You must be a high privileged user (such as a system administrator) to create a database encryption key and encrypt a database.</span></span> <span data-ttu-id="9a454-116">É necessário que esse usuário possa ser autenticado pelo módulo EKM.</span><span class="sxs-lookup"><span data-stu-id="9a454-116">That user must be able to be authenticated by the EKM module.</span></span>  
  
-   <span data-ttu-id="9a454-117">Ao iniciar, o [!INCLUDE[ssDE](../../../includes/ssde-md.md)] precisa abrir o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="9a454-117">Upon start up the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] must open the database.</span></span> <span data-ttu-id="9a454-118">Para fazer isso, você deverá criar uma credencial que será autenticada pelo EKM, que adicioná-la ao logon baseado em uma chave assimétrica.</span><span class="sxs-lookup"><span data-stu-id="9a454-118">To do this, you should create a credential that will be authenticated by the EKM, and add it to a login that is based on an asymmetric key.</span></span> <span data-ttu-id="9a454-119">Os usuários não podem efetuar logon com esse logon, mas o [!INCLUDE[ssDE](../../../includes/ssde-md.md)] poderá se autenticar com o dispositivo de EKM.</span><span class="sxs-lookup"><span data-stu-id="9a454-119">Users cannot login using that login, but the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] will be able to authenticate itself with the EKM device.</span></span>  
  
-   <span data-ttu-id="9a454-120">Se a chave assimétrica armazenada no módulo EKM for perdida, não será possível abrir o banco de dados no [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a454-120">If the asymmetric key stored in the EKM module is lost, the database will not be able to be opened by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="9a454-121">Se o provedor de EKM permitir o backup da chave assimétrica, você deverá criar o backup e armazená-lo em um local seguro.</span><span class="sxs-lookup"><span data-stu-id="9a454-121">If the EKM provider lets you back up the asymmetric key, you should create a back up and store it in a secure location.</span></span>  
  
-   <span data-ttu-id="9a454-122">As opções e os parâmetros exigidos por seu provedor de EKM podem diferir do que é fornecido no exemplo de código abaixo.</span><span class="sxs-lookup"><span data-stu-id="9a454-122">The options and parameters required by your EKM provider can differ from what is provided in the code example below.</span></span> <span data-ttu-id="9a454-123">Para obter mais informações, consulte seu provedor de EKM.</span><span class="sxs-lookup"><span data-stu-id="9a454-123">For more information, see your EKM provider.</span></span>  
  
###  <a name="security"></a><a name="Security"></a> <span data-ttu-id="9a454-124">Segurança</span><span class="sxs-lookup"><span data-stu-id="9a454-124">Security</span></span>  
  
####  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="9a454-125">Permissões</span><span class="sxs-lookup"><span data-stu-id="9a454-125">Permissions</span></span>  
 <span data-ttu-id="9a454-126">Este tópico usa as seguintes permissões:</span><span class="sxs-lookup"><span data-stu-id="9a454-126">This topic uses the following permissions:</span></span>  
  
-   <span data-ttu-id="9a454-127">Para alterar uma opção de configuração e executar a instrução RECONFIGURE, você deve ter a permissão em nível de servidor ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="9a454-127">To change a configuration option and run the RECONFIGURE statement, you must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="9a454-128">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="9a454-128">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>  
  
-   <span data-ttu-id="9a454-129">Requer a permissão ALTER ANY CREDENTIAL.</span><span class="sxs-lookup"><span data-stu-id="9a454-129">Requires ALTER ANY CREDENTIAL permission.</span></span>  
  
-   <span data-ttu-id="9a454-130">Requer a permissão ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="9a454-130">Requires ALTER ANY LOGIN permission.</span></span>  
  
-   <span data-ttu-id="9a454-131">Requer a permissão CREATE ASYMMETRIC KEY.</span><span class="sxs-lookup"><span data-stu-id="9a454-131">Requires CREATE ASYMMETRIC KEY permission.</span></span>  
  
-   <span data-ttu-id="9a454-132">Requer a permissão CONTROL no banco de dados para criptografá-lo.</span><span class="sxs-lookup"><span data-stu-id="9a454-132">Requires CONTROL permission on the database to encrypt the database.</span></span>  
  
##  <a name="using-transact-sql"></a><a name="TsqlProcedure"></a> <span data-ttu-id="9a454-133">Usando o Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="9a454-133">Using Transact-SQL</span></span>  
  
#### <a name="to-enable-tde-using-ekm"></a><span data-ttu-id="9a454-134">Para habilitar a TDE usando EKM</span><span class="sxs-lookup"><span data-stu-id="9a454-134">To enable TDE using EKM</span></span>  
  
1.  <span data-ttu-id="9a454-135">Copie os arquivos fornecidos pelo provedor de EKM em um local apropriado no computador com o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="9a454-135">Copy the files supplied by the EKM provider to an appropriate location on the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="9a454-136">Neste exemplo, usamos a pasta **C:\EKM** .</span><span class="sxs-lookup"><span data-stu-id="9a454-136">In this example, we use the **C:\EKM** folder.</span></span>  
  
2.  <span data-ttu-id="9a454-137">Instale os certificados no computador, como requerido pelo provedor de EKM.</span><span class="sxs-lookup"><span data-stu-id="9a454-137">Install certificates to the computer as required by your EKM provider.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] <span data-ttu-id="9a454-138">não fornece um provedor de EKM.</span><span class="sxs-lookup"><span data-stu-id="9a454-138">does not supply an EKM provider.</span></span> <span data-ttu-id="9a454-139">Cada provedor de EKM pode ter procedimentos diferentes para instalar, configurar e autorizar os usuários.</span><span class="sxs-lookup"><span data-stu-id="9a454-139">Each EKM provider can have different procedures for installing, configuring and authorizing users.</span></span>  <span data-ttu-id="9a454-140">Consulte a documentação do provedor de EKM para completar esta etapa.</span><span class="sxs-lookup"><span data-stu-id="9a454-140">Consult your EKM provider documentation to complete this step.</span></span>  
  
3.  <span data-ttu-id="9a454-141">No **Pesquisador de Objetos**, conecte-se a uma instância do [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span><span class="sxs-lookup"><span data-stu-id="9a454-141">In **Object Explorer**, connect to an instance of [!INCLUDE[ssDE](../../../includes/ssde-md.md)].</span></span>  
  
4.  <span data-ttu-id="9a454-142">Na barra Padrão, clique em **Nova Consulta**.</span><span class="sxs-lookup"><span data-stu-id="9a454-142">On the Standard bar, click **New Query**.</span></span>  
  
5.  <span data-ttu-id="9a454-143">Copie e cole o exemplo a seguir na janela de consulta e clique em **Executar**.</span><span class="sxs-lookup"><span data-stu-id="9a454-143">Copy and paste the following example into the query window and click **Execute**.</span></span>  
  
    ```  
    -- Enable advanced options.  
    sp_configure 'show advanced options', 1 ;  
    GO  
    RECONFIGURE ;  
    GO  
    -- Enable EKM provider  
    sp_configure 'EKM provider enabled', 1 ;  
    GO  
    RECONFIGURE ;  
    GO  
    -- Create a cryptographic provider, which we have chosen to call "EKM_Prov," based on an EKM provider  
  
    CREATE CRYPTOGRAPHIC PROVIDER EKM_Prov   
    FROM FILE = 'C:\EKM_Files\KeyProvFile.dll' ;  
    GO  
  
    -- Create a credential that will be used by system administrators.  
    CREATE CREDENTIAL sa_ekm_tde_cred   
    WITH IDENTITY = 'Identity1',   
    SECRET = 'q*gtev$0u#D1v'   
    FOR CRYPTOGRAPHIC PROVIDER EKM_Prov ;  
    GO  
  
    -- Add the credential to a high privileged user such as your   
    -- own domain login in the format [DOMAIN\login].  
    ALTER LOGIN Contoso\Mary  
    ADD CREDENTIAL sa_ekm_tde_cred ;  
    GO  
    -- create an asymmetric key stored inside the EKM provider  
    USE master ;  
    GO  
    CREATE ASYMMETRIC KEY ekm_login_key   
    FROM PROVIDER [EKM_Prov]  
    WITH ALGORITHM = RSA_512,  
    PROVIDER_KEY_NAME = 'SQL_Server_Key' ;  
    GO  
  
    -- Create a credential that will be used by the Database Engine.  
    CREATE CREDENTIAL ekm_tde_cred   
    WITH IDENTITY = 'Identity2'   
    , SECRET = 'jeksi84&sLksi01@s'   
    FOR CRYPTOGRAPHIC PROVIDER EKM_Prov ;  
  
    -- Add a login used by TDE, and add the new credential to the login.  
    CREATE LOGIN EKM_Login   
    FROM ASYMMETRIC KEY ekm_login_key ;  
    GO  
    ALTER LOGIN EKM_Login   
    ADD CREDENTIAL ekm_tde_cred ;  
    GO  
  
    -- Create the database encryption key that will be used for TDE.  
    USE AdventureWorks2012 ;  
    GO  
    CREATE DATABASE ENCRYPTION KEY  
    WITH ALGORITHM  = AES_128  
    ENCRYPTION BY SERVER ASYMMETRIC KEY ekm_login_key ;  
    GO  
  
    -- Alter the database to enable transparent data encryption.  
    ALTER DATABASE AdventureWorks2012   
    SET ENCRYPTION ON ;  
    GO  
    ```  
  
 <span data-ttu-id="9a454-144">Para saber mais, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="9a454-144">For more information, see the following:</span></span>  
  
-   [<span data-ttu-id="9a454-145">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a454-145">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)  
  
-   [<span data-ttu-id="9a454-146">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a454-146">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-cryptographic-provider-transact-sql)  
  
-   [<span data-ttu-id="9a454-147">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a454-147">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)  
  
-   [<span data-ttu-id="9a454-148">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a454-148">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)  
  
-   [<span data-ttu-id="9a454-149">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a454-149">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)  
  
-   [<span data-ttu-id="9a454-150">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a454-150">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)  
  
-   [<span data-ttu-id="9a454-151">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a454-151">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)  
  
-   [<span data-ttu-id="9a454-152">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="9a454-152">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)  
  
-   [<span data-ttu-id="9a454-153">Gerenciamento extensível de chaves usando o Cofre de Chaves do Azure &#40;SQL Server&#41;</span><span class="sxs-lookup"><span data-stu-id="9a454-153">Extensible Key Management Using Azure Key Vault &#40;SQL Server&#41;</span></span>](extensible-key-management-using-azure-key-vault-sql-server.md)  
  
-   [<span data-ttu-id="9a454-154">Transparent Data Encryption com o Banco de Dados SQL do Azure</span><span class="sxs-lookup"><span data-stu-id="9a454-154">Transparent Data Encryption with Azure SQL Database</span></span>](../../../database-engine/transparent-data-encryption-with-azure-sql-database.md)  
  
  
