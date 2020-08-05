---
title: Transparent Data Encryption com o Banco de Dados SQL do Azure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- TDE, SQL Database
- Transparent Data Encryption, SQL Database
- encryption (SQL Database) TDE
ms.assetid: 0bf7e8ff-1416-4923-9c4c-49341e208c62
author: CarlRabeler
ms.author: carlrab
ms.openlocfilehash: 6af7c52741b85a2733b93c2b1ed8c03a14dd6343
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574244"
---
# <a name="transparent-data-encryption-with-azure-sql-database"></a><span data-ttu-id="c6c55-102">Transparent Data Encryption com o Banco de Dados SQL do Azure</span><span class="sxs-lookup"><span data-stu-id="c6c55-102">Transparent Data Encryption with Azure SQL Database</span></span>
  <span data-ttu-id="c6c55-103">A Transparent Data Encryption do [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] (visualização) ajuda a proteger contra a ameaça de atividade mal-intencionada executando criptografia e descriptografia em tempo real do banco de dados, backups associados e arquivos de log de transações em repouso sem exigir alterações no aplicativo.</span><span class="sxs-lookup"><span data-stu-id="c6c55-103">[!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] transparent data encryption (preview) helps protect against the threat of malicious activity by performing real-time encryption and decryption of the database, associated backups, and transaction log files at rest without requiring changes to the application.</span></span>

 <span data-ttu-id="c6c55-104">A TDE criptografa o armazenamento de um banco de dados inteiro usando uma chave simétrica chamada de chave de criptografia de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c6c55-104">TDE encrypts the storage of an entire database by using a symmetric key called the database encryption key.</span></span> <span data-ttu-id="c6c55-105">No [!INCLUDE[ssSDS](../includes/sssds-md.md)] , a chave de criptografia do banco de dados é protegida por um certificado do servidor interno.</span><span class="sxs-lookup"><span data-stu-id="c6c55-105">In [!INCLUDE[ssSDS](../includes/sssds-md.md)] the database encryption key is protected by a built-in server certificate.</span></span> <span data-ttu-id="c6c55-106">O certificado do servidor interno é exclusivo para cada servidor [!INCLUDE[ssSDS](../includes/sssds-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="c6c55-106">The built-in server certificate is unique for each [!INCLUDE[ssSDS](../includes/sssds-md.md)] server.</span></span> <span data-ttu-id="c6c55-107">Se um banco de dados está em uma relação de GeoDR, ele é protegido por uma chave diferente em cada servidor.</span><span class="sxs-lookup"><span data-stu-id="c6c55-107">If a database is in a GeoDR relationship, it is protected by a different key on each server.</span></span> <span data-ttu-id="c6c55-108">Se dois bancos de dados estão conectados ao mesmo servidor, eles compartilham o mesmo certificado interno.</span><span class="sxs-lookup"><span data-stu-id="c6c55-108">If 2 databases are connected to the same server, they share the same built-in certificate.</span></span> [!INCLUDE[msCoName](../includes/msconame-md.md)] <span data-ttu-id="c6c55-109">gira automaticamente esses certificados pelo menos a cada 90 dias.</span><span class="sxs-lookup"><span data-stu-id="c6c55-109">automatically rotates these certificates at least every 90 days.</span></span> <span data-ttu-id="c6c55-110">Para obter uma descrição geral do TDE, consulte [TDE &#40;Transparent Data Encryption&#41;](../relational-databases/security/encryption/transparent-data-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="c6c55-110">For a general description of TDE, see [Transparent Data Encryption &#40;TDE&#41;](../relational-databases/security/encryption/transparent-data-encryption.md).</span></span>

 [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] <span data-ttu-id="c6c55-111">não dá suporte à integração do Cofre da Chave do Azure com TDE.</span><span class="sxs-lookup"><span data-stu-id="c6c55-111">does not support Azure Key Vault integration with TDE.</span></span> [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] <span data-ttu-id="c6c55-112">em execução em uma máquina virtual do Azure pode usar uma chave assimétrica do Cofre da Chave.</span><span class="sxs-lookup"><span data-stu-id="c6c55-112">running on an Azure virtual machine can use an asymmetric key from the Key Vault.</span></span> <span data-ttu-id="c6c55-113">Para obter mais informações, consulte [Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault](../relational-databases/security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md#ExampleA).</span><span class="sxs-lookup"><span data-stu-id="c6c55-113">For more information, see [Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault](../relational-databases/security/encryption/extensible-key-management-using-azure-key-vault-sql-server.md#ExampleA).</span></span>

||
|-|
|<span data-ttu-id="c6c55-114">**Aplica-se a**: [!INCLUDE[sqldbesa](../includes/sqldbesa-md.md)] ([visualização em algumas regiões](https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span><span class="sxs-lookup"><span data-stu-id="c6c55-114">**Applies to**: [!INCLUDE[sqldbesa](../includes/sqldbesa-md.md)] ([Preview in some regions](https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/?WT.mc_id=TSQL_GetItTag)).</span></span>|

> [!IMPORTANT]
>  <span data-ttu-id="c6c55-115">Este é um recurso de visualização.</span><span class="sxs-lookup"><span data-stu-id="c6c55-115">This is currently a preview feature.</span></span> <span data-ttu-id="c6c55-116">Eu reconheço e concordo que a implementação da Transparent Data Encryption do [!INCLUDE[ssSDS](../includes/sssds-md.md)] no meu banco de dados está sujeita aos termos de visualização do contrato de licença (por exemplo, o Enterprise Agreement, Contrato do Microsoft Azure ou o Contrato de Assinatura do Microsoft Online), bem como quaisquer [Termos de Uso Suplementares da Visualização do Microsoft Azure](https://azure.microsoft.com/support/legal/preview-supplemental-terms/)aplicáveis.</span><span class="sxs-lookup"><span data-stu-id="c6c55-116">I acknowledge and agree that implementation of [!INCLUDE[ssSDS](../includes/sssds-md.md)] transparent data encryption in my database(s) is subject to the preview terms in my license agreement (e.g. the Enterprise Agreement, Microsoft Azure Agreement, or Microsoft Online Subscription Agreement), as well as any applicable [Supplemental Terms of Use for Microsoft Azure Preview](https://azure.microsoft.com/support/legal/preview-supplemental-terms/).</span></span>

 <span data-ttu-id="c6c55-117">A visualização do status da TDE aplica-se até mesmo ao subconjunto de regiões geográficas em que versão da família V12 de [!INCLUDE[ssSDS](../includes/sssds-md.md)] é anunciada como apresentando agora status de disponibilidade geral.</span><span class="sxs-lookup"><span data-stu-id="c6c55-117">The preview of status of TDE applies even in the subset of geographic regions where version family V12 of [!INCLUDE[ssSDS](../includes/sssds-md.md)] is announced as now being in general availability status.</span></span> <span data-ttu-id="c6c55-118">A TDE para [!INCLUDE[ssSDS](../includes/sssds-md.md)] não se destina para uso em bancos de dados de produção até o [!INCLUDE[msCoName](../includes/msconame-md.md)] anunciar a promoção da TDE, de visualização para GA.</span><span class="sxs-lookup"><span data-stu-id="c6c55-118">TDE for [!INCLUDE[ssSDS](../includes/sssds-md.md)] is not intended for use in production databases until [!INCLUDE[msCoName](../includes/msconame-md.md)] announces that TDE is promoted from preview to GA.</span></span> <span data-ttu-id="c6c55-119">Para obter mais informações sobre [!INCLUDE[ssSDS](../includes/sssds-md.md)] V12, consulte [Novidades no Banco de Dados SQL do Azure](https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/).</span><span class="sxs-lookup"><span data-stu-id="c6c55-119">For more information about [!INCLUDE[ssSDS](../includes/sssds-md.md)] V12, see [What's new in Azure SQL Database](https://azure.microsoft.com/documentation/articles/sql-database-preview-whats-new/).</span></span>

##  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="c6c55-120">Permissões</span><span class="sxs-lookup"><span data-stu-id="c6c55-120">Permissions</span></span>
 <span data-ttu-id="c6c55-121">Para inscrever-se para a visualizar e configurar TDE por meio do portal do Azure, usando a API REST ou usando o PowerShell, você deve estar conectado como o proprietário do Azure, Colaborador ou Gerenciador de segurança do SQL.</span><span class="sxs-lookup"><span data-stu-id="c6c55-121">To sign up for the preview and to configure TDE through the Azure portal, by using the REST API, or by using PowerShell, you must be connected as the Azure Owner, Contributor, or SQL Security Manager.</span></span>

 <span data-ttu-id="c6c55-122">Para configurar a TDE usando [!INCLUDE[tsql](../includes/tsql-md.md)] , é requerido o seguinte:</span><span class="sxs-lookup"><span data-stu-id="c6c55-122">To configure TDE by using [!INCLUDE[tsql](../includes/tsql-md.md)] requires the following:</span></span>

-   <span data-ttu-id="c6c55-123">Você já deve estar inscrito para a visualização da TDE.</span><span class="sxs-lookup"><span data-stu-id="c6c55-123">You must be already signed up for the TDE preview.</span></span>

-   <span data-ttu-id="c6c55-124">Para criar uma chave de criptografia você deve ser um administrador do [!INCLUDE[ssSDS](../includes/sssds-md.md)] ou um membro da função **dbmanager** no banco de dados mestre e ter a permissão **CONTROL** no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c6c55-124">To create the database encryption key you must be a [!INCLUDE[ssSDS](../includes/sssds-md.md)] administrator or you must be a member of the **dbmanager** role in the master database and have the **CONTROL** permission on the database.</span></span>

-   <span data-ttu-id="c6c55-125">Para executar a instrução ALTER DATABASE com a opção SET só requer a associação na função **dbmanager** .</span><span class="sxs-lookup"><span data-stu-id="c6c55-125">To execute the ALTER DATABASE statement with the SET option only requires membership in the **dbmanager** role.</span></span>

##  <a name="sign-up-for-the-preview-of-tde-and-enable-tde-on-a-database"></a><a name="Preview"></a><span data-ttu-id="c6c55-126">Inscreva-se para a visualização do TDE e habilite o TDE em um banco de dados</span><span class="sxs-lookup"><span data-stu-id="c6c55-126">Sign Up for the Preview of TDE and Enable TDE on a Database</span></span>

1.  <span data-ttu-id="c6c55-127">Visite o portal do Azure em [https://portal.azure.com](https://portal.azure.com) e entre com sua conta de administrador ou colaborador do Azure.</span><span class="sxs-lookup"><span data-stu-id="c6c55-127">Visit the Azure Portal at [https://portal.azure.com](https://portal.azure.com) and sign-in with your Azure Administrator or Contributor account.</span></span>

2.  <span data-ttu-id="c6c55-128">Na faixa esquerda, clique em **PROCURAR** e em **Bancos de dados SQL**.</span><span class="sxs-lookup"><span data-stu-id="c6c55-128">On the left banner, click to **BROWSE**, and then click **SQL databases**.</span></span>

3.  <span data-ttu-id="c6c55-129">Com **Bancos de dados SQL** selecionado no painel esquerdo, clique em seu banco de dados de usuário.</span><span class="sxs-lookup"><span data-stu-id="c6c55-129">With **SQL databases** selected in the left pane, click your user database.</span></span>

4.  <span data-ttu-id="c6c55-130">Na folha do banco de dados, clique em **Todas as configurações**.</span><span class="sxs-lookup"><span data-stu-id="c6c55-130">In the database blade, click **All settings**.</span></span>

5.  <span data-ttu-id="c6c55-131">Na folha **Configurações** , clique na parte **Transparent Data Encryption (visualização)** para abrir a folha **VISUALIZAÇÃO da Transparent Data Encryption** .</span><span class="sxs-lookup"><span data-stu-id="c6c55-131">In the **Settings** blade, click **Transparent data encryption (preview)** part to open the **Transparent data encryption PREVIEW** blade.</span></span> <span data-ttu-id="c6c55-132">Se você ainda não estiver inscrito para a visualização de TDE, as configurações de criptografia de dados serão desabilitadas até que você conclua a inscrição.</span><span class="sxs-lookup"><span data-stu-id="c6c55-132">If you have not already signed up for the TDE preview, the data encryption settings will be disabled until you complete signup.</span></span>

6.  <span data-ttu-id="c6c55-133">Clique em **TERMOS DE VISUALIZAÇÃO**.</span><span class="sxs-lookup"><span data-stu-id="c6c55-133">Click **PREVIEW TERMS**.</span></span>

7.  <span data-ttu-id="c6c55-134">Leia os termos da visualização e, se você concordar com os termos, marque a caixa de seleção **termos de encryptionPreview de dados transparentes** e clique em **OK** na parte inferior da página.</span><span class="sxs-lookup"><span data-stu-id="c6c55-134">Read the terms of the preview, and if you agree to the terms, select the **Transparent Data encryptionPreview terms** check box, and then click **OK** near the bottom of the page.</span></span> <span data-ttu-id="c6c55-135">Retornando para a folha **Data encryptionPREVIEW** , em que o botão de **criptografia de dados** agora deve estar habilitado.</span><span class="sxs-lookup"><span data-stu-id="c6c55-135">Returning to the **Data encryptionPREVIEW** blade, where the **Data encryption** button should now be enabled.</span></span>

8.  <span data-ttu-id="c6c55-136">Na folha **VISUALIZAÇÃO da criptografia de dados** , mova o botão **Criptografia de dados** para **Ligado**, e, em seguida, clique em **Salvar** (na parte superior da página) para aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="c6c55-136">In the **Data encryption PREVIEW** blade, move the **Data encryption** button to **On**, and then click **Save** (at the top of the page) to apply the setting.</span></span> <span data-ttu-id="c6c55-137">O **Status de criptografia** aproximará o progresso da Transparent Data Encryption.</span><span class="sxs-lookup"><span data-stu-id="c6c55-137">The **Encryption status** will approximate the progress of the transparent data encryption.</span></span>

     <span data-ttu-id="c6c55-138">![SQLDB_TDE_TermsNewUI](../../2014/database-engine/media/sqldb-tde-termsnewui.png "SQLDB_TDE_TermsNewUI")</span><span class="sxs-lookup"><span data-stu-id="c6c55-138">![SQLDB_TDE_TermsNewUI](../../2014/database-engine/media/sqldb-tde-termsnewui.png "SQLDB_TDE_TermsNewUI")</span></span>

     <span data-ttu-id="c6c55-139">Você também pode monitorar o progresso da criptografia conectando [!INCLUDE[ssSDS](../includes/sssds-md.md)] usando uma ferramenta de consulta como [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] como um usuário de banco de dados com a permissão **EXIBIR ESTADO DO BANCO DE DADOS** .</span><span class="sxs-lookup"><span data-stu-id="c6c55-139">You can also monitor the progress of encryption by connecting to [!INCLUDE[ssSDS](../includes/sssds-md.md)] using a query tool such as [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)] as a database user with the **VIEW DATABASE STATE** permission.</span></span> <span data-ttu-id="c6c55-140">Consulte a `encryption_state` coluna da exibição [sys. dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="c6c55-140">Query the `encryption_state` column of the [sys.dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) view.</span></span>

##  <a name="enabling-tde-on-sssds-by-using-transact-sql"></a><a name="Encrypt"></a><span data-ttu-id="c6c55-141">Habilitando TDE no [!INCLUDE[ssSDS](../includes/sssds-md.md)] usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6c55-141">Enabling TDE on [!INCLUDE[ssSDS](../includes/sssds-md.md)] by Using Transact-SQL</span></span>
 <span data-ttu-id="c6c55-142">Nas etapas a seguir, suponha que você já se inscreveu para a visualização.</span><span class="sxs-lookup"><span data-stu-id="c6c55-142">The following steps, assume you have already signed up for the preview.</span></span>

###  <a name="TsqlProcedure"></a>

1.  <span data-ttu-id="c6c55-143">Conecte-se ao banco de dados usando um logon que seja um administrador ou um membro da função **dbmanager** no banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="c6c55-143">Connect to the database using a login that is an administrator or a member of the **dbmanager** role in the master database.</span></span>

2.  <span data-ttu-id="c6c55-144">Execute as seguintes instruções para criar uma chave de criptografia do banco de dados e criptografar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c6c55-144">Execute the following statements to create a database encryption key and encrypt the database.</span></span>

    ```sql
    -- Create the database encryption key that will be used for TDE.
    CREATE DATABASE ENCRYPTION KEY 
    WITH ALGORITHM = AES_256 
    ENCRYPTION BY SERVER CERTIFICATE ##MS_TdeCertificate##;

    -- Enable encryption
    ALTER DATABASE [AdventureWorks] SET ENCRYPTION ON;
    GO
    ```

3.  <span data-ttu-id="c6c55-145">Para monitorar o progresso da criptografia no [!INCLUDE[ssSDS](../includes/sssds-md.md)] , os usuários de banco de dados com a permissão **View Database State** podem consultar a `encryption_state` coluna da exibição [Sys. dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="c6c55-145">To monitor the progress of encryption on [!INCLUDE[ssSDS](../includes/sssds-md.md)], database users with the **VIEW DATABASE STATE** permission can query the `encryption_state` column of the [sys.dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) view.</span></span>

## <a name="enabling-tde-on-sql-database-by-using-powershell"></a><span data-ttu-id="c6c55-146">Habilitando a TDE no banco de dados SQL usando PowerShell</span><span class="sxs-lookup"><span data-stu-id="c6c55-146">Enabling TDE on SQL Database by Using PowerShell</span></span>
 <span data-ttu-id="c6c55-147">Usando o Azure PowerShell, você pode executar o seguinte comando para ligar/desligar a TDE.</span><span class="sxs-lookup"><span data-stu-id="c6c55-147">Using the Azure PowerShell you can run the following command to turn TDE on/off.</span></span> <span data-ttu-id="c6c55-148">Você precisa se conectar a sua conta na janela de PS antes de executar o comando.</span><span class="sxs-lookup"><span data-stu-id="c6c55-148">You do have to connect your account to the PS window before running the command.</span></span> <span data-ttu-id="c6c55-149">Nas etapas a seguir, suponha que você já se inscreveu para a visualização.</span><span class="sxs-lookup"><span data-stu-id="c6c55-149">The following steps, assume you have already signed up for the preview.</span></span> <span data-ttu-id="c6c55-150">Para obter informações adicionais sobre o PowerShell, consulte [Como instalar e configurar o Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span><span class="sxs-lookup"><span data-stu-id="c6c55-150">For additional information about PowerShell, see [How to install and configure Azure PowerShell](https://azure.microsoft.com/documentation/articles/powershell-install-configure/).</span></span>

1.  <span data-ttu-id="c6c55-151">Para habilitar a TDE, retorne o status de TDE e exiba a atividade de criptografia.</span><span class="sxs-lookup"><span data-stu-id="c6c55-151">To enable TDE, return the TDE status, and view the encryption activity.</span></span>

    ```powershell
    Switch-AzureMode -Name AzureResourceManager
    Set-AzureSqlDatabaseTransparentDataEncryption -ServerName "myserver" -ResourceGroupName "Default-SQL-WestUS" -DatabaseName "database1" -State "Enabled"

    Get-AzureSqlDatabaseTransparentDataEncryption -ServerName "myserver" -ResourceGroupName "Default-SQL-WestUS" -DatabaseName "database1"
    Get-AzureSqlDatabaseTransparentDataEncryptionActivity -ServerName "myserver" -ResourceGroupName "Default-SQL-WestUS" -DatabaseName "database1"
    ```

2.  <span data-ttu-id="c6c55-152">Para desabilitar a TDE:</span><span class="sxs-lookup"><span data-stu-id="c6c55-152">To disable TDE:</span></span>

    ```powershell
    Set-AzureSqlDatabaseTransparentDataEncryption -ServerName "myserver" -ResourceGroupName "Default-SQL-WestUS" -DatabaseName "database1" -State "Disabled"
    Switch-AzureMode -Name AzureServiceManagement
    ```

##  <a name="decrypting-a-tde-protected-database-on-sssds"></a><a name="Decrypt"></a><span data-ttu-id="c6c55-153">Descriptografando um banco de dados protegido por TDE no[!INCLUDE[ssSDS](../includes/sssds-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6c55-153">Decrypting a TDE Protected Database on [!INCLUDE[ssSDS](../includes/sssds-md.md)]</span></span>

#### <a name="to-disable-tde-by-using-the-azure-portal"></a><span data-ttu-id="c6c55-154">Para desabilitar a TDE usando o Portal do Azure</span><span class="sxs-lookup"><span data-stu-id="c6c55-154">To Disable TDE by Using the Azure Portal</span></span>

1.  <span data-ttu-id="c6c55-155">Visite o portal do Azure em [https://portal.azure.com](https://portal.azure.com) e entre com sua conta de administrador ou colaborador do Azure.</span><span class="sxs-lookup"><span data-stu-id="c6c55-155">Visit the Azure Portal at [https://portal.azure.com](https://portal.azure.com) and sign-in with your Azure Administrator or Contributor account.</span></span>

2.  <span data-ttu-id="c6c55-156">Na faixa esquerda, clique em **PROCURAR** e em **Bancos de dados SQL**.</span><span class="sxs-lookup"><span data-stu-id="c6c55-156">On the left banner, click to **BROWSE**, and then click **SQL databases**.</span></span>

3.  <span data-ttu-id="c6c55-157">Com **Bancos de dados SQL** selecionado no painel esquerdo, clique em seu banco de dados de usuário.</span><span class="sxs-lookup"><span data-stu-id="c6c55-157">With **SQL databases** selected in the left pane, click your user database.</span></span>

4.  <span data-ttu-id="c6c55-158">Na folha do banco de dados, clique em **Todas as configurações**.</span><span class="sxs-lookup"><span data-stu-id="c6c55-158">In the database blade, click **All settings**.</span></span>

5.  <span data-ttu-id="c6c55-159">Na folha **Configurações** , clique na parte **Transparent Data Encryption (visualização)** para abrir a folha **VISUALIZAÇÃO da Transparent Data Encryption** .</span><span class="sxs-lookup"><span data-stu-id="c6c55-159">In the **Settings** blade, click **Transparent data encryption (preview)** part to open the **Transparent data encryption PREVIEW** blade.</span></span>

6.  <span data-ttu-id="c6c55-160">Na folha **VISUALIZAÇÃO da Transparent Data Encryption** , mova o botão **Criptografia de dados** para **Desligado**e, em seguida, clique em **Salvar** (na parte superior da página) para aplicar a configuração.</span><span class="sxs-lookup"><span data-stu-id="c6c55-160">In the **Transparent data encryption PREVIEW** blade, move the **Data encryption** button to **Off**, and then click **Save** (at the top of the page) to apply the setting.</span></span> <span data-ttu-id="c6c55-161">O **Status de criptografia** aproximará o progresso de descriptografia de dados transparente.</span><span class="sxs-lookup"><span data-stu-id="c6c55-161">The **Encryption status** will approximate the progress of the transparent data decryption.</span></span>

     <span data-ttu-id="c6c55-162">Você também pode monitorar o progresso da descriptografia conectando-se ao [!INCLUDE[ssSDS](../includes/sssds-md.md)] usando uma ferramenta de consulta como [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] como um usuário de banco de dados com a permissão **EXIBIR ESTADO DE BANCO DE DADOS** .</span><span class="sxs-lookup"><span data-stu-id="c6c55-162">You can also monitor the progress of decryption by connecting to [!INCLUDE[ssSDS](../includes/sssds-md.md)] using a query tool such as [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)] as a database user with the **VIEW DATABASE STATE** permission.</span></span> <span data-ttu-id="c6c55-163">Consulte a `encryption_state` coluna da exibição [sys. dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="c6c55-163">Query the `encryption_state` column of the [sys.dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql)view.</span></span>

#### <a name="to-disable-tde-by-using-transact-sql"></a><span data-ttu-id="c6c55-164">Para desabilitar a TDE usando Transact-SQL</span><span class="sxs-lookup"><span data-stu-id="c6c55-164">To Disable TDE by Using Transact-SQL</span></span>

1.  <span data-ttu-id="c6c55-165">Conecte-se ao banco de dados usando um logon que seja um administrador ou um membro da função **dbmanager** no banco de dados mestre.</span><span class="sxs-lookup"><span data-stu-id="c6c55-165">Connect to the database using a login that is an administrator or a member of the **dbmanager** role in the master database.</span></span>

2.  <span data-ttu-id="c6c55-166">Execute as seguintes instruções para descriptografar o banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c6c55-166">Execute the following statements to decrypt the database.</span></span>

    ```sql
    -- Enable encryption
    ALTER DATABASE [AdventureWorks] SET ENCRYPTION OFF;
    GO
    ```

3.  <span data-ttu-id="c6c55-167">Para monitorar o progresso da criptografia no [!INCLUDE[ssSDS](../includes/sssds-md.md)] , os usuários de banco de dados com a permissão **View Database State** podem consultar a `encryption_state` coluna da exibição [Sys. dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) .</span><span class="sxs-lookup"><span data-stu-id="c6c55-167">To monitor the progress of encryption on [!INCLUDE[ssSDS](../includes/sssds-md.md)], database users with the **VIEW DATABASE STATE** permission can query the `encryption_state` column of the [sys.dm_database_encryption_keys](/sql/relational-databases/system-dynamic-management-views/sys-dm-database-encryption-keys-transact-sql) view.</span></span>

##  <a name="working-with-tde-protected-databases-on-sssds"></a><a name="Working"></a><span data-ttu-id="c6c55-168">Trabalhando com bancos de dados protegidos por TDE em[!INCLUDE[ssSDS](../includes/sssds-md.md)]</span><span class="sxs-lookup"><span data-stu-id="c6c55-168">Working with TDE Protected Databases on [!INCLUDE[ssSDS](../includes/sssds-md.md)]</span></span>
 <span data-ttu-id="c6c55-169">Não é necessário descriptografar bancos de dados para operações no Azure.</span><span class="sxs-lookup"><span data-stu-id="c6c55-169">You do not need to decrypt databases for operations within Azure.</span></span> <span data-ttu-id="c6c55-170">As configurações de TDE no banco de dados de origem ou banco de dados primário são herdadas de forma transparente no destino.</span><span class="sxs-lookup"><span data-stu-id="c6c55-170">The TDE settings on the source database or primary database are transparently inherited on the target.</span></span> <span data-ttu-id="c6c55-171">Isso inclui operações envolvendo:</span><span class="sxs-lookup"><span data-stu-id="c6c55-171">This includes operations involving:</span></span>

-   <span data-ttu-id="c6c55-172">Restauração Geográfica</span><span class="sxs-lookup"><span data-stu-id="c6c55-172">Geo-Restore</span></span>

-   <span data-ttu-id="c6c55-173">Recuperação Pontual de Autoatendimento</span><span class="sxs-lookup"><span data-stu-id="c6c55-173">Self-Service Point in Time Restore</span></span>

-   <span data-ttu-id="c6c55-174">Restaurar um Banco de Dados Excluído</span><span class="sxs-lookup"><span data-stu-id="c6c55-174">Restore a Deleted Database</span></span>

-   <span data-ttu-id="c6c55-175">Replicação Geográfica Ativa</span><span class="sxs-lookup"><span data-stu-id="c6c55-175">Active Geo_Replication</span></span>

-   <span data-ttu-id="c6c55-176">Criar uma Cópia do Banco de Dados</span><span class="sxs-lookup"><span data-stu-id="c6c55-176">Creating a Database Copy</span></span>

##  <a name="moving-a-tde-protected-database-on-using-bacpac-files"></a><a name="Moving"></a><span data-ttu-id="c6c55-177">Movendo um banco de dados protegido por TDE no usando. Arquivos Bacpac</span><span class="sxs-lookup"><span data-stu-id="c6c55-177">Moving a TDE Protected Database on using .Bacpac Files</span></span>
 <span data-ttu-id="c6c55-178">Quando exportar um banco de dados protegido por TDE usando a função Exportar banco de dados no Portal do [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] ou no Assistente de Importação e Exportação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)], o conteúdo do banco de dados não está criptografado.</span><span class="sxs-lookup"><span data-stu-id="c6c55-178">When exporting a TDE protected database using the Export Database function in the [!INCLUDE[ssSDSfull](../includes/sssdsfull-md.md)] Portal or the [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Import and Export Wizard, the content of the database is not encrypted.</span></span> <span data-ttu-id="c6c55-179">O conteúdo é armazenado em arquivos. bacpac que não estão criptografados.</span><span class="sxs-lookup"><span data-stu-id="c6c55-179">The content is stored in .bacpac files which are not encrypted.</span></span>  <span data-ttu-id="c6c55-180">Certifique-se de proteger os arquivos. bacpac adequadamente e habilitar a TDE após a conclusão da importação do novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="c6c55-180">Be sure to protect the .bacpac files appropriately and enable TDE once import of the new database is completed.</span></span>

## <a name="related-sql-server-topic"></a><span data-ttu-id="c6c55-181">Tópico do SQL Server relacionado</span><span class="sxs-lookup"><span data-stu-id="c6c55-181">Related SQL Server Topic</span></span>
 [<span data-ttu-id="c6c55-182">Habilitar TDE usando EKM</span><span class="sxs-lookup"><span data-stu-id="c6c55-182">Enable TDE Using EKM</span></span>](../relational-databases/security/encryption/enable-tde-on-sql-server-using-ekm.md)

## <a name="see-also"></a><span data-ttu-id="c6c55-183">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="c6c55-183">See Also</span></span>
 <span data-ttu-id="c6c55-184">[Transparent Data Encryption &#40;TDE&#41;](../relational-databases/security/encryption/transparent-data-encryption.md) [criar credencial &#40;transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [criar chave assimétrica &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [criar chave de criptografia de banco de dados &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-encryption-key-transact-sql) [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) [Opções ALTER DATABASE SET &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)</span><span class="sxs-lookup"><span data-stu-id="c6c55-184">[Transparent Data Encryption &#40;TDE&#41;](../relational-databases/security/encryption/transparent-data-encryption.md) [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-database-encryption-key-transact-sql) [ALTER DATABASE &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql) [ALTER DATABASE SET Options &#40;Transact-SQL&#41;](/sql/t-sql/statements/alter-database-transact-sql-set-options)</span></span>
