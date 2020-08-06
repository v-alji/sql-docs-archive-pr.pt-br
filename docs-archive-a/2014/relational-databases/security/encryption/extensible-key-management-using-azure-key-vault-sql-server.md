---
title: Gerenciamento extensível de chaves usando o Azure Key Vault (SQL Server) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: security
ms.topic: conceptual
helpviewer_keywords:
- EKM, with key vault
- TDE, EKM and key vault
- Extensible Key Management with key vault
- Key Management with key vault
- Transparent Data Encryption, using EKM and key vault
ms.assetid: 3efdc48a-8064-4ea6-a828-3fbf758ef97c
author: jaszymas
ms.author: jaszymas
ms.openlocfilehash: 0e4bbc4f0c371c927988e6b91fdbf47307ad9d3f
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87686232"
---
# <a name="extensible-key-management-using-azure-key-vault-sql-server"></a><span data-ttu-id="f36ee-102">Gerenciamento extensível de chaves usando o Azure Key Vault (SQL Server)</span><span class="sxs-lookup"><span data-stu-id="f36ee-102">Extensible Key Management Using Azure Key Vault (SQL Server)</span></span>
  <span data-ttu-id="f36ee-103">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] conector para [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Key Vault permite que a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] criptografia Aproveite o serviço de Azure Key Vault como um [gerenciamento extensível de chaves &#40;](extensible-key-management-ekm.md) provedor de&#41;do EKM para proteger suas chaves de criptografia.</span><span class="sxs-lookup"><span data-stu-id="f36ee-103">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector for [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Key Vault enables [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption to leverage the Azure Key Vault service as an [Extensible Key Management &#40;EKM&#41;](extensible-key-management-ekm.md) provider to protect its encryption keys.</span></span>

 <span data-ttu-id="f36ee-104">Incluso neste tópico:</span><span class="sxs-lookup"><span data-stu-id="f36ee-104">Included in this topic:</span></span>

-   [<span data-ttu-id="f36ee-105">Usos de EKM</span><span class="sxs-lookup"><span data-stu-id="f36ee-105">Uses of EKM</span></span>](#Uses)

-   [<span data-ttu-id="f36ee-106">Etapa 1: Configuração do Key Vault para uso pelo SQL Server</span><span class="sxs-lookup"><span data-stu-id="f36ee-106">Step 1: Setting up the Key Vault for use by SQL Server</span></span>](#Step1)

-   [<span data-ttu-id="f36ee-107">Etapa 2: Instalação do SQL Server Connector</span><span class="sxs-lookup"><span data-stu-id="f36ee-107">Step 2: Installing the SQL Server Connector</span></span>](#Step2)

-   [<span data-ttu-id="f36ee-108">Etapa 3: Configurar o SQL Server para usar um provedor EKM para o Key Vault</span><span class="sxs-lookup"><span data-stu-id="f36ee-108">Step 3: Configure SQL Server to use an EKM provider for the Key Vault</span></span>](#Step3)

-   [<span data-ttu-id="f36ee-109">Exemplo A: Criptografia transparente de dados usando uma chave assimétrica do Key Vault</span><span class="sxs-lookup"><span data-stu-id="f36ee-109">Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleA)

-   [<span data-ttu-id="f36ee-110">Exemplo B: Criptografia de backups usando uma chave assimétrica do Key Vault</span><span class="sxs-lookup"><span data-stu-id="f36ee-110">Example B: Encrypting Backups by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleB)

-   [<span data-ttu-id="f36ee-111">Exemplo C: Criptografia de nível de coluna usando uma chave assimétrica do Key Vault</span><span class="sxs-lookup"><span data-stu-id="f36ee-111">Example C: Column Level Encryption by Using an Asymmetric Key from the Key Vault</span></span>](#ExampleC)

##  <a name="uses-of-ekm"></a><a name="Uses"></a><span data-ttu-id="f36ee-112">Usos de EKM</span><span class="sxs-lookup"><span data-stu-id="f36ee-112">Uses of EKM</span></span>
 <span data-ttu-id="f36ee-113">Uma organização pode usar criptografia [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para proteger dados confidenciais.</span><span class="sxs-lookup"><span data-stu-id="f36ee-113">An organization can use [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption to protect sensitive data.</span></span> [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)]<span data-ttu-id="f36ee-114">a criptografia inclui [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md), [criptografia de nível de coluna](/sql/t-sql/functions/cryptographic-functions-transact-sql) (cle) e criptografia de [backup](../../backup-restore/backup-encryption.md).</span><span class="sxs-lookup"><span data-stu-id="f36ee-114">encryption includes [Transparent Data Encryption &#40;TDE&#41;](transparent-data-encryption.md), [Column Level Encryption](/sql/t-sql/functions/cryptographic-functions-transact-sql) (CLE), and [Backup Encryption](../../backup-restore/backup-encryption.md).</span></span> <span data-ttu-id="f36ee-115">Em todos esses casos, os dados são criptografados usando uma chave de criptografia simétrica de dados.</span><span class="sxs-lookup"><span data-stu-id="f36ee-115">In all of these cases the data is encrypted using a symmetric data encryption key.</span></span> <span data-ttu-id="f36ee-116">A chave de criptografia simétrica de dados é ainda mais protegida ao criptografar com uma hierarquia de chaves armazenadas em [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f36ee-116">The symmetric data encryption key is further protected by encrypting it with a hierarchy of keys stored in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f36ee-117">Como alternativa, a arquitetura de provedor EKM permite que [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] proteja as chaves de criptografia de dados usando uma chave assimétrica armazenada fora do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] em um provedor de criptografia externo.</span><span class="sxs-lookup"><span data-stu-id="f36ee-117">Alternatively, the EKM provider architecture enables [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to protect the data encryption keys by using an asymmetric key stored outside of [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] in an external cryptographic provider.</span></span> <span data-ttu-id="f36ee-118">Usar a arquitetura de provedor EKM acrescenta uma camada adicional de segurança e permite que as organizações separem o gerenciamento de chaves e dados.</span><span class="sxs-lookup"><span data-stu-id="f36ee-118">Using EKM provider architecture adds an additional layer of security and allows organizations to separate the management of keys and data.</span></span>

 <span data-ttu-id="f36ee-119">O [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector para o Azure Key Vault permite que o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] aproveite o serviço do cofre de chave altamente disponível, escalonável e de alto desempenho como um provedor EKM para proteção de chave de criptografia.</span><span class="sxs-lookup"><span data-stu-id="f36ee-119">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector for Azure Key Vault lets [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] leverage the scalable, high performance, and highly available key vault service as an EKM provider for encryption key protection.</span></span> <span data-ttu-id="f36ee-120">O serviço do cofre de chave pode ser usado com instalações do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] em Máquinas Virtuais [!INCLUDE[msCoName](../../../includes/msconame-md.md)] do Azure e para servidores locais.</span><span class="sxs-lookup"><span data-stu-id="f36ee-120">The key vault service can be used with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] installations on [!INCLUDE[msCoName](../../../includes/msconame-md.md)] Azure Virtual Machines and for on-premises servers.</span></span> <span data-ttu-id="f36ee-121">O serviço de chave de cofre também fornece a opção de usar rigidamente módulos de segurança de hardware (HSM) monitorados e controlados para um nível mais alto de proteção para as chaves de criptografia assimétrica.</span><span class="sxs-lookup"><span data-stu-id="f36ee-121">The key vault service also provides the option to use tightly controlled and monitored Hardware Security Modules (HSMs) for a higher level of protection for asymmetric encryption keys.</span></span> <span data-ttu-id="f36ee-122">Para obter mais informações sobre o cofre de chaves, consulte [Cofre de Chaves do Azure](https://go.microsoft.com/fwlink/?LinkId=521401).</span><span class="sxs-lookup"><span data-stu-id="f36ee-122">For more information about the key vault, see [Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521401).</span></span>

 <span data-ttu-id="f36ee-123">A imagem a seguir resume o fluxo do processo de EKM usando o cofre da chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-123">The following image summarizes the process flow of EKM using the key vault.</span></span> <span data-ttu-id="f36ee-124">Os números de etapa do processo na imagem não devem corresponder aos números de etapa de instalação que seguem a imagem.</span><span class="sxs-lookup"><span data-stu-id="f36ee-124">The process step numbers in the image are not meant to match the setup step numbers that follow the image.</span></span>

 <span data-ttu-id="f36ee-125">![EKM do SQL Server com o Azure Key Vault](../../../database-engine/media/ekm-using-azure-key-vault.png "EKM do SQL Server com o Azure Key Vault")</span><span class="sxs-lookup"><span data-stu-id="f36ee-125">![SQL Server EKM using the Azure Key Vault](../../../database-engine/media/ekm-using-azure-key-vault.png "SQL Server EKM using the Azure Key Vault")</span></span>

##  <a name="step-1-set-up-the-key-vault-for-use-by-sql-server"></a><a name="Step1"></a><span data-ttu-id="f36ee-126">Etapa 1: configurar o Key Vault para uso por SQL Server</span><span class="sxs-lookup"><span data-stu-id="f36ee-126">Step 1: Set up the Key Vault for use by SQL Server</span></span>
 <span data-ttu-id="f36ee-127">Use as seguintes etapas para configurar uma chave de cofre para uso com o [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] para proteção de chave de criptografia.</span><span class="sxs-lookup"><span data-stu-id="f36ee-127">Use the following steps to set up a key vault for use with the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] for encryption key protection.</span></span> <span data-ttu-id="f36ee-128">Um cofre já pode estar em uso para a organização.</span><span class="sxs-lookup"><span data-stu-id="f36ee-128">A vault may already be in use for the organization.</span></span> <span data-ttu-id="f36ee-129">Quando não houver um cofre, o Administrador do Azure de sua organização, designado para gerenciar chaves de criptografia, poderá criar um cofre, gerar uma chave assimétrica no cofre e, então, autorizar [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para usar a chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-129">When a vault does not exist, the Azure Administrator in your organization that is designated to manage encryption keys can create a vault, generate an asymmetric key in the vault, and then authorize [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use the key.</span></span> <span data-ttu-id="f36ee-130">Familiarize-se com o serviço de cofre de chave consultando [Introdução ao Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402)e a referência de [Cmdlets do PowerShell do Azure Key Vault](https://docs.microsoft.com/powershell/module/azurerm.keyvault) .</span><span class="sxs-lookup"><span data-stu-id="f36ee-130">To familiarize yourself with the key vault service review [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402), and the PowerShell [Azure Key Vault Cmdlets](https://docs.microsoft.com/powershell/module/azurerm.keyvault) reference.</span></span>

> [!IMPORTANT]
>  <span data-ttu-id="f36ee-131">Se tiver várias assinaturas do Azure, você deve usar a assinatura que contém o [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f36ee-131">If you have multiple Azure subscriptions, you must use the subscription that contains [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>

1.  <span data-ttu-id="f36ee-132">**Crie um cofre:** Crie um cofre usando as instruções na seção **Criar um cofre da chave** da [Introdução ao Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="f36ee-132">**Create a vault:** Create a vault by using the instructions in the **Create a key vault** section of [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span> <span data-ttu-id="f36ee-133">Registre o nome do cofre.</span><span class="sxs-lookup"><span data-stu-id="f36ee-133">Record the name of the vault.</span></span> <span data-ttu-id="f36ee-134">Este tópico usa **ContosoKeyVault** como o nome da chave de cofre.</span><span class="sxs-lookup"><span data-stu-id="f36ee-134">This topic uses **ContosoKeyVault** as the key vault name.</span></span>

2.  <span data-ttu-id="f36ee-135">**Gere uma chave assimétrica no cofre:** A chave assimétrica no cofre da chave é usada para proteger as chaves de criptografia [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f36ee-135">**Generate an asymmetric key in the vault:** The asymmetric key in the key vault is used to protect [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption keys.</span></span> <span data-ttu-id="f36ee-136">Somente a parte pública da chave assimétrica nunca deixa o cofre, a parte particular nunca é exportada pelo cofre.</span><span class="sxs-lookup"><span data-stu-id="f36ee-136">Only the public portion of the asymmetric key ever leaves the vault, the private portion is never exported by the vault.</span></span> <span data-ttu-id="f36ee-137">Todas as operações de criptografia usando a chave assimétrica são delegadas ao Azure Key Vault e são protegidas pela segurança de chave de cofre.</span><span class="sxs-lookup"><span data-stu-id="f36ee-137">All cryptographic operations using the asymmetric key are delegated to the Azure Key Vault, and are protected by the key vault security.</span></span>

     <span data-ttu-id="f36ee-138">Há várias maneiras de gerar uma chave assimétrica e armazená-la no cofre.</span><span class="sxs-lookup"><span data-stu-id="f36ee-138">There are several ways that you can generate an asymmetric key and store it in the vault.</span></span> <span data-ttu-id="f36ee-139">Externamente, você pode gerar uma chave e importá-la para o cofre como um arquivo .pfx.</span><span class="sxs-lookup"><span data-stu-id="f36ee-139">You can externally generate a key, and import the key into the vault as a .pfx file.</span></span> <span data-ttu-id="f36ee-140">Ou criar a chave diretamente no cofre usando as APIs do cofre da chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-140">Or create the key directly in the vault by using the key vault APIs.</span></span>

     <span data-ttu-id="f36ee-141">O Connector [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] requer que as chaves assimétricas sejam RSA de 2048 bits e o nome da chave só pode usar caracteres que contenham "a-z", "A-Z", "0-9" e "-".</span><span class="sxs-lookup"><span data-stu-id="f36ee-141">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector requires the asymmetric keys to be 2048-bit RSA, and the key name can only use the characters "a-z", "A-Z", "0-9", and "-".</span></span> <span data-ttu-id="f36ee-142">Neste documento, o nome da chave assimétrica é conhecido como **ContosoMasterKey**.</span><span class="sxs-lookup"><span data-stu-id="f36ee-142">In this document the name of the asymmetric key is referred to as **ContosoMasterKey**.</span></span> <span data-ttu-id="f36ee-143">Substitua isso pelo nome exclusivo usado para a chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-143">Replace this with the unique name you use for the key.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="f36ee-144">Importar a chave assimétrica é altamente recomendável para cenários de produção, pois ela permite que o administrador garanta a chave em um sistema de caução de chaves.</span><span class="sxs-lookup"><span data-stu-id="f36ee-144">Importing the asymmetric key is highly recommended for production scenarios because it allows the administrator to escrow the key in a key escrow system.</span></span> <span data-ttu-id="f36ee-145">Se a chave assimétrica for criada no cofre, ela não pode ser mantida em garantia porque a chave privada nunca pode deixar o cofre.</span><span class="sxs-lookup"><span data-stu-id="f36ee-145">If the asymmetric key is created in the vault, it cannot be escrowed because the private key can never leave the vault.</span></span> <span data-ttu-id="f36ee-146">As chaves usadas para proteger dados críticos devem ser mantidas em garantia.</span><span class="sxs-lookup"><span data-stu-id="f36ee-146">Keys used to protect critical data should be escrowed.</span></span> <span data-ttu-id="f36ee-147">A perda de uma chave assimétrica resultará em dados irrecuperáveis permanentemente.</span><span class="sxs-lookup"><span data-stu-id="f36ee-147">The loss of an asymmetric key will result in permanently unrecoverable data.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="f36ee-148">O cofre da chave dá suporte a várias versões da mesma chave nomeada.</span><span class="sxs-lookup"><span data-stu-id="f36ee-148">The key vault supports multiple versions of the same named key.</span></span> <span data-ttu-id="f36ee-149">As chaves usadas pelo Connector [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] não devem estar com controle de versão ou reversão.</span><span class="sxs-lookup"><span data-stu-id="f36ee-149">Keys to be used by [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector should not be versioned or rolled.</span></span> <span data-ttu-id="f36ee-150">Se o administrador deseja distribuir a chave usada para criptografia [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] , uma nova chave com um nome diferente deve ser criada no cofre e usada para criptografar DEK.</span><span class="sxs-lookup"><span data-stu-id="f36ee-150">If the administrator wants to roll the key used for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption, a new key with a different name should be created in the vault and used to encrypt the DEK.</span></span>

     <span data-ttu-id="f36ee-151">Para obter mais informações sobre como importar uma chave no cofre de chave ou criar uma chave no cofre de chave (não recomendado para um ambiente de produção), consulte a seção **Adicionar uma chave ou um segredo no cofre chave** em [Introdução ao Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="f36ee-151">For more information on how to import a key into the key vault or to create a key in the key vault (not recommended for a production environment), see the **Add a key or secret to the key vault** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span>

3.  <span data-ttu-id="f36ee-152">**Obtenha as Entidades de Serviço do Active Directory do Azure para uso com o SQL Server:** Quando a empresa se inscreve para um serviço de nuvem da Microsoft, ela recebe um Active Directory do Azure.</span><span class="sxs-lookup"><span data-stu-id="f36ee-152">**Get Azure Active Directory Service Principals to use for SQL Server:** When the organization signs up for a Microsoft cloud service, it gets an Azure Active Directory.</span></span> <span data-ttu-id="f36ee-153">Crie **Entidades de serviço** no Active Directory do Azure para [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para uso (para autenticar-se com o Active Directory do Azure) ao acessar o cofre de chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-153">Create **Service Principals** in the Azure Active Directory for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use (to authenticate itself to Azure Active Directory) while accessing the key vault.</span></span>

    -   <span data-ttu-id="f36ee-154">Uma **Entidade de serviço** será necessária para que o administrador [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] acesse o cofre durante a configuração de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para usar a criptografia.</span><span class="sxs-lookup"><span data-stu-id="f36ee-154">One **Service Principal** will be needed by a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator to access the vault while configuring [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] to use encryption.</span></span>

    -   <span data-ttu-id="f36ee-155">Outra **Entidade de serviço** será necessária pelo [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] para acessar o cofre para descodificar chaves usadas na criptografia [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f36ee-155">Another **Service Principal** will be needed by the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)] to access the vault for unwrapping keys used in [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption.</span></span>

     <span data-ttu-id="f36ee-156">Para obter mais informações sobre como registrar um aplicativo e gerar uma entidade de serviço, consulte a seção **Registrar um aplicativo com o Active Directory do Azure** em [Introdução ao Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="f36ee-156">For more information about how to register an application and generate a service principal, see the **Register an Application with Azure Active Directory** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span> <span data-ttu-id="f36ee-157">O processo de registro retorna uma **ID do aplicativo** (também conhecida como uma **ID DO CLIENTE**) e uma **Chave de autenticação** (também conhecida como um **Segredo**) para cada **Entidade de serviço**do Active Directory do Azure.</span><span class="sxs-lookup"><span data-stu-id="f36ee-157">The registration process returns an **Application ID** (also known as a **CLIENT ID**) and a **Authentication Key** (also known as a **Secret**) for each Azure Active Directory **Service Principal**.</span></span> <span data-ttu-id="f36ee-158">Quando usado na `CREATE CREDENTIAL` instrução, o hífen deve ser removido da ID do **cliente**.</span><span class="sxs-lookup"><span data-stu-id="f36ee-158">When used in the `CREATE CREDENTIAL` statement, the hyphen must be removed from the **CLIENT ID**.</span></span> <span data-ttu-id="f36ee-159">Registre isso para uso nos scripts abaixo:</span><span class="sxs-lookup"><span data-stu-id="f36ee-159">Record these for use in the scripts below:</span></span>

    -   <span data-ttu-id="f36ee-160">**Entidade de serviço** para um logon **sysadmin** : **CLIENTID_sysadmin_login** e **SECRET_sysadmin_login**</span><span class="sxs-lookup"><span data-stu-id="f36ee-160">**Service Principal** for a **sysadmin** login: **CLIENTID_sysadmin_login** and **SECRET_sysadmin_login**</span></span>

    -   <span data-ttu-id="f36ee-161">**Entidade de serviço** para o [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]: **CLIENTID_DBEngine** e **SECRET_DBEngine**.</span><span class="sxs-lookup"><span data-stu-id="f36ee-161">**Service Principal** for the [!INCLUDE[ssDEnoversion](../../../includes/ssdenoversion-md.md)]: **CLIENTID_DBEngine** and **SECRET_DBEngine**.</span></span>

4.  <span data-ttu-id="f36ee-162">**Conceda permissão para que as entidades de serviço acessem o Key Vault:** As entidades de **CLIENTID_sysadmin_login** e **CLIENTID_DBEngineService** exigem as permissões **Get**, **list**, **wrapKey**e **unwrapKey** no cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="f36ee-162">**Grant Permission for the Service Principals to access the Key Vault:** Both the **CLIENTID_sysadmin_login** and **CLIENTID_DBEngineService Principals** require the **get**, **list**, **wrapKey**, and **unwrapKey** permissions in the key vault.</span></span> <span data-ttu-id="f36ee-163">Se você pretende criar chaves por meio de [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] também precisará conceder a permissão **criar** no cofre de chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-163">If you intend to create keys through [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] you also need to grant the **create** permission in key vault.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="f36ee-164">Os usuários devem ter pelo menos as operações **wrapKey** e **unwrapKey** para o cofre da chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-164">Users must have at least the **wrapKey** and **unwrapKey** operations for the key vault.</span></span>

     <span data-ttu-id="f36ee-165">Para obter mais informações sobre como conceder permissões para o cofre, consulte a seção **Autorizar o uso pelo aplicativo da chave ou segredo** em [Introdução ao Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span><span class="sxs-lookup"><span data-stu-id="f36ee-165">For more information about granting permissions to the vault, see the **Authorize the application to use the key or secret** section in [Get Started with Azure Key Vault](https://go.microsoft.com/fwlink/?LinkId=521402).</span></span>

     <span data-ttu-id="f36ee-166">Links para a documentação do Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="f36ee-166">Links to Azure Key Vault documentation</span></span>

    -   [<span data-ttu-id="f36ee-167">O que é o Cofre da Chave do Azure?</span><span class="sxs-lookup"><span data-stu-id="f36ee-167">What is Azure Key Vault?</span></span>](https://go.microsoft.com/fwlink/?LinkId=521401)

    -   [<span data-ttu-id="f36ee-168">Introdução ao Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="f36ee-168">Get Started with Azure Key Vault</span></span>](https://go.microsoft.com/fwlink/?LinkId=521402)

    -   <span data-ttu-id="f36ee-169">Referência dos [Cmdlets do Cofre de Chaves do Azure](https://docs.microsoft.com/powershell/module/azurerm.keyvault) do PowerShell</span><span class="sxs-lookup"><span data-stu-id="f36ee-169">PowerShell [Azure Key Vault Cmdlets](https://docs.microsoft.com/powershell/module/azurerm.keyvault) reference</span></span>

##  <a name="step-2-install-the-sql-server-connector"></a><a name="Step2"></a><span data-ttu-id="f36ee-170">Etapa 2: instalar o Conector do SQL Server</span><span class="sxs-lookup"><span data-stu-id="f36ee-170">Step 2: Install the SQL Server Connector</span></span>
 <span data-ttu-id="f36ee-171">O Connector [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] é baixado e instalado pelo administrador do computador [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f36ee-171">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector is downloaded and installed by the administrator of the [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] computer.</span></span> <span data-ttu-id="f36ee-172">O Connector [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] está disponível para download no [Centro de Download da Microsoft](https://go.microsoft.com/fwlink/p/?LinkId=521700).</span><span class="sxs-lookup"><span data-stu-id="f36ee-172">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector is available as a download from the [Microsoft Download Center](https://go.microsoft.com/fwlink/p/?LinkId=521700).</span></span>  <span data-ttu-id="f36ee-173">Procure **SQL Server Connector para Microsoft Azure Key Vault**, examine os detalhes, requisitos de sistema e instruções de instalação e escolha baixar o conector e iniciar a instalação usando **Executar**.</span><span class="sxs-lookup"><span data-stu-id="f36ee-173">Search for **SQL Server Connector for Microsoft Azure Key Vault**, review the details, system requirements and install instructions and choose to download the connector and start the installation using **Run**.</span></span> <span data-ttu-id="f36ee-174">Examine e aceite a licença e continue.</span><span class="sxs-lookup"><span data-stu-id="f36ee-174">Review the license and accept the license and continue.</span></span>

 <span data-ttu-id="f36ee-175">Por padrão, o conector é instalado em **C:\Program Files\SQL Server Connector para Microsoft Azure Key Vault**.</span><span class="sxs-lookup"><span data-stu-id="f36ee-175">By default the connector is installed at **C:\Program Files\SQL Server Connector for Microsoft Azure Key Vault**.</span></span> <span data-ttu-id="f36ee-176">Esse local pode ser alterado durante a instalação.</span><span class="sxs-lookup"><span data-stu-id="f36ee-176">This location can be changed during setup.</span></span> <span data-ttu-id="f36ee-177">(Se alterado, ajuste os scripts a seguir).</span><span class="sxs-lookup"><span data-stu-id="f36ee-177">(If changed, adjust the scripts below.)</span></span>

 <span data-ttu-id="f36ee-178">Ao concluir a instalação, os seguintes itens são instalados no computador:</span><span class="sxs-lookup"><span data-stu-id="f36ee-178">On completing the install, the following are installed on the machine:</span></span>

-   <span data-ttu-id="f36ee-179">**Microsoft.AzureKeyVaultService.EKM.dll**: Esse é o DLL de provedor EKM criptográfico que precisa ser registrado com [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] usando a instrução CREATE CRYPTOGRAPHIC PROVIDER.</span><span class="sxs-lookup"><span data-stu-id="f36ee-179">**Microsoft.AzureKeyVaultService.EKM.dll**: This is the cryptographic EKM provider DLL that needs to be registered with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] by using the CREATE CRYPTOGRAPHIC PROVIDER statement.</span></span>

-   <span data-ttu-id="f36ee-180">**Azure Key Vault SQL Server Connector**: Isso é um serviço Windows que permite que o provedor EKM criptográfico se comunique com o cofre de chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-180">**Azure Key Vault SQL Server Connector**: This is a Windows service that enables the cryptographic EKM provider to communicate with the key vault.</span></span>

 <span data-ttu-id="f36ee-181">A instalação do Connector [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] também permite que você baixe opcionalmente os scripts de exemplo para criptografia [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f36ee-181">The [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] Connector installation also allows you to optionally download sample scripts for [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption.</span></span>

##  <a name="step-3-configure-sql-server-to-use-an-ekm-provider-for-the-key-vault"></a><a name="Step3"></a><span data-ttu-id="f36ee-182">Etapa 3: configurar SQL Server para usar um provedor EKM para o Key Vault</span><span class="sxs-lookup"><span data-stu-id="f36ee-182">Step 3: Configure SQL Server to use an EKM provider for the Key Vault</span></span>

###  <a name="permissions"></a><a name="Permissions"></a> <span data-ttu-id="f36ee-183">Permissões</span><span class="sxs-lookup"><span data-stu-id="f36ee-183">Permissions</span></span>
 <span data-ttu-id="f36ee-184">Para concluir esse processo todo é necessária a permissão CONTROL SERVER ou associação na função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="f36ee-184">To complete this entire process requires CONTROL SERVER permission or membership in the **sysadmin** fixed server role.</span></span> <span data-ttu-id="f36ee-185">Ações específicas requerem as seguintes permissões:</span><span class="sxs-lookup"><span data-stu-id="f36ee-185">Specific actions require the following permissions:</span></span>

-   <span data-ttu-id="f36ee-186">Para criar um provedor criptográfico, é necessária a permissão CONTROL SERVER ou associação na função de servidor fixa **sysadmin** .</span><span class="sxs-lookup"><span data-stu-id="f36ee-186">To create a cryptographic provider, requires CONTROL SERVER permission or membership in the **sysadmin** fixed server role.</span></span>

-   <span data-ttu-id="f36ee-187">Para alterar uma opção de configuração e executar a instrução RECONFIGURE, você deve ter a permissão em nível de servidor ALTER SETTINGS.</span><span class="sxs-lookup"><span data-stu-id="f36ee-187">To change a configuration option and run the RECONFIGURE statement, you must be granted the ALTER SETTINGS server-level permission.</span></span> <span data-ttu-id="f36ee-188">A permissão ALTER SETTINGS é implicitamente mantida pelas funções de servidor fixas **sysadmin** e **serveradmin** .</span><span class="sxs-lookup"><span data-stu-id="f36ee-188">The ALTER SETTINGS permission is implicitly held by the **sysadmin** and **serveradmin** fixed server roles.</span></span>

-   <span data-ttu-id="f36ee-189">Para criar uma credencial, é necessária a permissão ALTER ANY CREDENTIAL.</span><span class="sxs-lookup"><span data-stu-id="f36ee-189">To create a credential, requires ALTER ANY CREDENTIAL permission.</span></span>

-   <span data-ttu-id="f36ee-190">Para adicionar uma credencial para um logon, é necessária a permissão ALTER ANY LOGIN.</span><span class="sxs-lookup"><span data-stu-id="f36ee-190">To add a credential to a login, requires ALTER ANY LOGIN permission.</span></span>

-   <span data-ttu-id="f36ee-191">Para criar uma chave assimétrica, é necessária a permissão CREATE ASYMMETRIC KEY.</span><span class="sxs-lookup"><span data-stu-id="f36ee-191">To create an asymmetric key, requires CREATE ASYMMETRIC KEY permission.</span></span>

###  <a name="to-configure-sql-server-to-use-a-cryptographic-provider"></a><a name="TsqlProcedure"></a><span data-ttu-id="f36ee-192">Para configurar SQL Server para usar um provedor criptográfico</span><span class="sxs-lookup"><span data-stu-id="f36ee-192">To configure SQL Server to use a cryptographic provider</span></span>

1.  <span data-ttu-id="f36ee-193">Configurar o [!INCLUDE[ssDE](../../../includes/ssde-md.md)] para usar EKM e registrar (criar) o provedor criptográfico com [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f36ee-193">Configure the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to use EKM, and register (create) the cryptographic provider with [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span>

    ```sql
    -- Enable advanced options.
    USE master;
    GO

    sp_configure 'show advanced options', 1 ;
    GO
    RECONFIGURE ;
    GO
    -- Enable EKM provider
    sp_configure 'EKM provider enabled', 1 ;
    GO
    RECONFIGURE ;
    GO

    -- Create a cryptographic provider, using the SQL Server Connector
    -- which is an EKM provider for the Azure Key Vault. This example uses 
    -- the name AzureKeyVault_EKM_Prov.

    CREATE CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov 
    FROM FILE = 'C:\Program Files\SQL Server Connector for Microsoft Azure Key Vault\Microsoft.AzureKeyVaultService.EKM.dll';
    GO
    ```

2.  <span data-ttu-id="f36ee-194">Instalação de uma credencial [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para um logon de administrador [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para usar o cofre de chave a fim de configurar e gerenciar cenários de criptografia [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="f36ee-194">Setup a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] credential for a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] administrator login to use the key vault in order to setup and manage [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] encryption scenarios.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="f36ee-195">O argumento **Identity** de `CREATE CREDENTIAL` requer o nome do cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="f36ee-195">The **IDENTITY** argument of `CREATE CREDENTIAL` requires the key vault name.</span></span> <span data-ttu-id="f36ee-196">O argumento **Secret** de `CREATE CREDENTIAL` requer o *\<Client ID>* (sem hifens) e *\<Secret>* deve ser passado juntos sem um espaço entre eles.</span><span class="sxs-lookup"><span data-stu-id="f36ee-196">The **SECRET** argument of `CREATE CREDENTIAL` requires the *\<Client ID>* (without hyphens) and *\<Secret>* to be passed together without a space between them.</span></span>

     <span data-ttu-id="f36ee-197">No exemplo a seguir, a **ID do cliente** ( `EF5C8E09-4D2A-4A76-9998-D93440D8115D` ) é removida dos hifens e inserida como a cadeia de caracteres `EF5C8E094D2A4A769998D93440D8115D` e o **segredo** é representado pela cadeia de caracteres *SECRET_sysadmin_login*.</span><span class="sxs-lookup"><span data-stu-id="f36ee-197">In the following example, the **Client ID** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) is stripped of the hyphens and entered as the string `EF5C8E094D2A4A769998D93440D8115D` and the **Secret** is represented by the string *SECRET_sysadmin_login*.</span></span>

    ```sql
    USE master;
    CREATE CREDENTIAL sysadmin_ekm_cred 
        WITH IDENTITY = 'ContosoKeyVault', 
        SECRET = 'EF5C8E094D2A4A769998D93440D8115DSECRET_sysadmin_login' 
    FOR CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov ;

    -- Add the credential to the SQL Server administrators domain login 
    ALTER LOGIN [<domain>/<login>]
    ADD CREDENTIAL sysadmin_ekm_cred;
    ```

     <span data-ttu-id="f36ee-198">Para obter um exemplo de como usar variáveis para os `CREATE CREDENTIAL` argumentos e remover programaticamente os hifens da ID do cliente, consulte [criar credencial &#40;TRANSACT-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f36ee-198">For an example of using variables for the `CREATE CREDENTIAL` arguments and programmatically removing the hyphens from the Client ID, see [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql).</span></span>

3.  <span data-ttu-id="f36ee-199">Se você importou uma chave assimétrica, conforme descrito anteriormente na etapa 1, seção 3, abra a chave fornecendo o nome da chave no exemplo a seguir.</span><span class="sxs-lookup"><span data-stu-id="f36ee-199">If you imported an asymmetric key as described earlier in step 1, section 3, open the key by providing your key name in the following example.</span></span>

    ```sql
    CREATE ASYMMETRIC KEY CONTOSO_KEY 
    FROM PROVIDER [AzureKeyVault_EKM_Prov]
    WITH PROVIDER_KEY_NAME = 'ContosoMasterKey',
    CREATION_DISPOSITION = OPEN_EXISTING;
    ```

     <span data-ttu-id="f36ee-200">Embora não seja recomendado para produção (porque não é possível exportar a chave), é possível criar uma chave assimétrica diretamente no cofre do [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f36ee-200">Though not recommended for production (because the key cannot be exported), it is possible to create an asymmetric key directly in the vault from [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="f36ee-201">Se uma chave não foi importada anteriormente, crie uma chave assimétrica no cofre de chave para teste usando o script a seguir.</span><span class="sxs-lookup"><span data-stu-id="f36ee-201">If you did not import a key earlier, then create an asymmetric key in the key vault for testing by using the following script.</span></span> <span data-ttu-id="f36ee-202">Execute o script usando um logon fornecido com a credencial **sysadmin_ekm_cred** .</span><span class="sxs-lookup"><span data-stu-id="f36ee-202">Execute the script, using a login provisioned with the **sysadmin_ekm_cred** credential.</span></span>

    ```sql
    CREATE ASYMMETRIC KEY CONTOSO_KEY 
    FROM PROVIDER [AzureKeyVault_EKM_Prov]
    WITH ALGORITHM = RSA_2048,
    PROVIDER_KEY_NAME = 'ContosoMasterKey';
    ```

> [!TIP]
>  <span data-ttu-id="f36ee-203">Os usuários receberão o erro **Não é possível exportar a chave pública do provedor. Código de erro do provedor: 2053.**</span><span class="sxs-lookup"><span data-stu-id="f36ee-203">Users receiving the error **Cannot export public key from the provider. Provider error code: 2053.**</span></span> <span data-ttu-id="f36ee-204">deve verificar suas permissões **get**, **list**, **wrapKey**e **unwrapKey** no cofre da chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-204">should check their **get**, **list**, **wrapKey**, and **unwrapKey** permissions in the key vault.</span></span>

 <span data-ttu-id="f36ee-205">Para saber mais, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f36ee-205">For more information, see the following:</span></span>

-   [<span data-ttu-id="f36ee-206">sp_configure &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f36ee-206">sp_configure &#40;Transact-SQL&#41;</span></span>](/sql/relational-databases/system-stored-procedures/sp-configure-transact-sql)

-   [<span data-ttu-id="f36ee-207">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f36ee-207">CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-cryptographic-provider-transact-sql)

-   [<span data-ttu-id="f36ee-208">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f36ee-208">CREATE CREDENTIAL &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-credential-transact-sql)

-   [<span data-ttu-id="f36ee-209">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f36ee-209">CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-asymmetric-key-transact-sql)

-   [<span data-ttu-id="f36ee-210">CREATE LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f36ee-210">CREATE LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-login-transact-sql)

-   [<span data-ttu-id="f36ee-211">ALTER LOGIN &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f36ee-211">ALTER LOGIN &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-login-transact-sql)

## <a name="examples"></a><span data-ttu-id="f36ee-212">Exemplos</span><span class="sxs-lookup"><span data-stu-id="f36ee-212">Examples</span></span>

###  <a name="example-a-transparent-data-encryption-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleA"></a><span data-ttu-id="f36ee-213">Exemplo A: Transparent Data Encryption usando uma chave assimétrica da Key Vault</span><span class="sxs-lookup"><span data-stu-id="f36ee-213">Example A: Transparent Data Encryption by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="f36ee-214">Depois de concluir as etapas acima, crie uma credencial e um logon, crie uma chave de criptografia do banco de dados protegida pela chave assimétrica no cofre de chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-214">After completing the steps above, create a credential and a login, create a database encryption key protected by the asymmetric key in the key vault.</span></span> <span data-ttu-id="f36ee-215">Use a chave de criptografia do banco de dados para criptografar um banco de dados com TDE.</span><span class="sxs-lookup"><span data-stu-id="f36ee-215">Use the database encryption key to encrypt a database with TDE.</span></span>

 <span data-ttu-id="f36ee-216">Criptografar um banco de dados requer permissão CONTROL no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f36ee-216">To encrypt a database requires CONTROL permission on the database.</span></span>

##### <a name="to-enable-tde-using-ekm-and-the-key-vault"></a><span data-ttu-id="f36ee-217">Habilitar TDE usando EKM e a chave de cofre</span><span class="sxs-lookup"><span data-stu-id="f36ee-217">To enable TDE using EKM and the Key Vault</span></span>

1.  <span data-ttu-id="f36ee-218">Crie uma credencial [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] para o [!INCLUDE[ssDE](../../../includes/ssde-md.md)] para usar quando acessar o cofre chave EKM durante o carregamento de banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f36ee-218">Create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] credential for the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] to use when accessing the key vault EKM during database load.</span></span>

    > [!IMPORTANT]
    >  <span data-ttu-id="f36ee-219">O argumento **Identity** de `CREATE CREDENTIAL` requer o nome do cofre de chaves.</span><span class="sxs-lookup"><span data-stu-id="f36ee-219">The **IDENTITY** argument of `CREATE CREDENTIAL` requires the key vault name.</span></span> <span data-ttu-id="f36ee-220">O argumento **Secret** de `CREATE CREDENTIAL` requer o *\<Client ID>* (sem hifens) e *\<Secret>* deve ser passado juntos sem um espaço entre eles.</span><span class="sxs-lookup"><span data-stu-id="f36ee-220">The **SECRET** argument of `CREATE CREDENTIAL` requires the *\<Client ID>* (without hyphens) and *\<Secret>* to be passed together without a space between them.</span></span>

     <span data-ttu-id="f36ee-221">No exemplo a seguir, a **ID do cliente** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) não tem hifens e foi inserida como a cadeia de caracteres `EF5C8E094D2A4A769998D93440D8115D` , e **Secret** é representado pela cadeia de caracteres *SECRET_DBEngine*.</span><span class="sxs-lookup"><span data-stu-id="f36ee-221">In the following example, the **Client ID** (`EF5C8E09-4D2A-4A76-9998-D93440D8115D`) is stripped of the hyphens and entered as the string `EF5C8E094D2A4A769998D93440D8115D` and the **Secret** is represented by the string *SECRET_DBEngine*.</span></span>

    ```sql
    USE master;
    CREATE CREDENTIAL Azure_EKM_TDE_cred 
        WITH IDENTITY = 'ContosoKeyVault', 
        SECRET = 'EF5C8E094D2A4A769998D93440D8115DSECRET_DBEngine' 
        FOR CRYPTOGRAPHIC PROVIDER AzureKeyVault_EKM_Prov ;
    ```

2.  <span data-ttu-id="f36ee-222">Criar um logon [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] a ser usado pelo [!INCLUDE[ssDE](../../../includes/ssde-md.md)] para TDE e adicione a credencial a ele.</span><span class="sxs-lookup"><span data-stu-id="f36ee-222">Create a [!INCLUDE[ssNoVersion](../../../includes/ssnoversion-md.md)] login to be used by the [!INCLUDE[ssDE](../../../includes/ssde-md.md)] for TDE, and add the credential to it.</span></span> <span data-ttu-id="f36ee-223">Este exemplo usa a chave assimétrica CONTOSO_KEY armazenada no cofre de chave, que foi importada ou criada anteriormente para o banco de dados mestre, como descrito na [Etapa 3, seção 3](#Step3) acima.</span><span class="sxs-lookup"><span data-stu-id="f36ee-223">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier for the master database, as described in [Step 3, section 3](#Step3) above.</span></span>

    ```sql
    USE master;
    -- Create a SQL Server login associated with the asymmetric key 
    -- for the Database engine to use when it loads a database 
    -- encrypted by TDE.
    CREATE LOGIN TDE_Login 
    FROM ASYMMETRIC KEY CONTOSO_KEY;
    GO 

    -- Alter the TDE Login to add the credential for use by the 
    -- Database Engine to access the key vault
    ALTER LOGIN TDE_Login 
    ADD CREDENTIAL Azure_EKM_TDE_cred ;
    GO
    ```

3.  <span data-ttu-id="f36ee-224">Crie a chave de criptografia do banco de dados (DEK) que será usada para a TDE.</span><span class="sxs-lookup"><span data-stu-id="f36ee-224">Create the database encryption key (DEK) that will be used for TDE.</span></span> <span data-ttu-id="f36ee-225">A DEK pode ser criada usando qualquer algoritmo com suporte do SQL Server ou o comprimento da chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-225">The DEK can be created using any SQL Server supported algorithm or key length.</span></span> <span data-ttu-id="f36ee-226">A DEK estará protegida pela chave assimétrica no cofre de chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-226">The DEK will be protected by the asymmetric key in the key vault.</span></span>

     <span data-ttu-id="f36ee-227">Este exemplo usa a chave assimétrica CONTOSO_KEY armazenada no cofre de chave, que foi importada ou criada anteriormente, como descrito na [Etapa 3, seção 3](#Step3) acima.</span><span class="sxs-lookup"><span data-stu-id="f36ee-227">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier, as described in [Step 3, section 3](#Step3) above.</span></span>

    ```sql
    USE ContosoDatabase;
    GO

    CREATE DATABASE ENCRYPTION KEY 
    WITH ALGORITHM = AES_128 
    ENCRYPTION BY SERVER ASYMMETRIC KEY CONTOSO_KEY;
    GO

    -- Alter the database to enable transparent data encryption.
    ALTER DATABASE ContosoDatabase 
    SET ENCRYPTION ON ;
    GO
    ```

     <span data-ttu-id="f36ee-228">Para saber mais, consulte o seguinte:</span><span class="sxs-lookup"><span data-stu-id="f36ee-228">For more information, see the following:</span></span>

    -   [<span data-ttu-id="f36ee-229">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f36ee-229">CREATE DATABASE ENCRYPTION KEY &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/create-database-encryption-key-transact-sql)

    -   [<span data-ttu-id="f36ee-230">ALTER DATABASE &#40;Transact-SQL&#41;</span><span class="sxs-lookup"><span data-stu-id="f36ee-230">ALTER DATABASE &#40;Transact-SQL&#41;</span></span>](/sql/t-sql/statements/alter-database-transact-sql)

###  <a name="example-b-encrypting-backups-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleB"></a><span data-ttu-id="f36ee-231">Exemplo B: criptografar backups usando uma chave assimétrica do Key Vault</span><span class="sxs-lookup"><span data-stu-id="f36ee-231">Example B: Encrypting Backups by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="f36ee-232">Há suporte para backups criptografados começando com [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="f36ee-232">Encrypted backups are supported starting with [!INCLUDE[ssSQL14](../../../includes/sssql14-md.md)].</span></span> <span data-ttu-id="f36ee-233">O exemplo a seguir cria e restaura um backup criptografado e uma chave de criptografia de dados protegida pela chave assimétrica no cofre de chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-233">The following example creates and restores a backup encrypted a data encryption key protected by the asymmetric key in the key vault.</span></span>

```sql
USE master;
BACKUP DATABASE [DATABASE_TO_BACKUP]
TO DISK = N'[PATH TO BACKUP FILE]' 
WITH FORMAT, INIT, SKIP, NOREWIND, NOUNLOAD, 
ENCRYPTION(ALGORITHM = AES_256, SERVER ASYMMETRIC KEY = [CONTOSO_KEY]);
GO
```

 <span data-ttu-id="f36ee-234">Código de restauração de exemplo.</span><span class="sxs-lookup"><span data-stu-id="f36ee-234">Sample restore code.</span></span>

```sql
RESTORE DATABASE [DATABASE_TO_BACKUP]
FROM DISK = N'[PATH TO BACKUP FILE]' WITH FILE = 1, NOUNLOAD, REPLACE;
GO
```

 <span data-ttu-id="f36ee-235">Para obter mais informações sobre opções de backup, consulte [backup &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span><span class="sxs-lookup"><span data-stu-id="f36ee-235">For more information about backup options, see [BACKUP &#40;Transact-SQL&#41;](/sql/t-sql/statements/backup-transact-sql).</span></span>

###  <a name="example-c-column-level-encryption-by-using-an-asymmetric-key-from-the-key-vault"></a><a name="ExampleC"></a><span data-ttu-id="f36ee-236">Exemplo C: criptografia de nível de coluna usando uma chave assimétrica do Key Vault</span><span class="sxs-lookup"><span data-stu-id="f36ee-236">Example C: Column Level Encryption by Using an Asymmetric Key from the Key Vault</span></span>
 <span data-ttu-id="f36ee-237">O exemplo a seguir cria uma chave simétrica protegida pela chave assimétrica no cofre de chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-237">The following example creates a symmetric key protected by the asymmetric key in the key vault.</span></span> <span data-ttu-id="f36ee-238">Em seguida, a chave simétrica é usada para criptografar dados no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="f36ee-238">Then the symmetric key is used to encrypt data in the database.</span></span>

 <span data-ttu-id="f36ee-239">Este exemplo usa a chave assimétrica CONTOSO_KEY armazenada no cofre de chave, que foi importada ou criada anteriormente, como descrito na [Etapa 3, seção 3](#Step3) acima.</span><span class="sxs-lookup"><span data-stu-id="f36ee-239">This example uses the CONTOSO_KEY asymmetric key stored in the key vault, which was imported or created earlier, as described in [Step 3, section 3](#Step3) above.</span></span> <span data-ttu-id="f36ee-240">Para usar essa chave assimétrica no banco de dados `ContosoDatabase` , você deve executar a instrução CREATE ASYMMETRIC KEY novamente, para fornecer ao banco de dados `ContosoDatabase` uma referência para a chave.</span><span class="sxs-lookup"><span data-stu-id="f36ee-240">To use this asymmetric key in the `ContosoDatabase` database, you must execute the CREATE ASYMMETRIC KEY statement again, to provide the `ContosoDatabase` database with a reference to the key.</span></span>

```sql
USE [ContosoDatabase];
GO

-- Create a reference to the key in the key vault
CREATE ASYMMETRIC KEY CONTOSO_KEY 
FROM PROVIDER [AzureKeyVault_EKM_Prov]
WITH PROVIDER_KEY_NAME = 'ContosoMasterKey',
CREATION_DISPOSITION = OPEN_EXISTING;

-- Create the data encryption key.
-- The data encryption key can be created using any SQL Server 
-- supported algorithm or key length.
-- The DEK will be protected by the asymmetric key in the key vault

CREATE SYMMETRIC KEY DATA_ENCRYPTION_KEY
    WITH ALGORITHM=AES_256
    ENCRYPTION BY ASYMMETRIC KEY CONTOSO_KEY;

DECLARE @DATA VARBINARY(MAX);

--Open the symmetric key for use in this session
OPEN SYMMETRIC KEY DATA_ENCRYPTION_KEY 
DECRYPTION BY ASYMMETRIC KEY CONTOSO_KEY;

--Encrypt syntax
SELECT @DATA = ENCRYPTBYKEY(KEY_GUID('DATA_ENCRYPTION_KEY'), CONVERT(VARBINARY,'Plain text data to encrypt'));

-- Decrypt syntax
SELECT CONVERT(VARCHAR, DECRYPTBYKEY(@DATA));

--Close the symmetric key
CLOSE SYMMETRIC KEY DATA_ENCRYPTION_KEY;
```

## <a name="see-also"></a><span data-ttu-id="f36ee-241">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="f36ee-241">See Also</span></span>
 <span data-ttu-id="f36ee-242">[Criar provedor criptográfico &#40;Transact-sql&#41;](/sql/t-sql/statements/create-cryptographic-provider-transact-sql) [criar credencial &#40;transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [criar chave assimétrica &#40;TRANSACT-sql&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [criar chave simétrica &#40;Transact-sql&#41;](/sql/t-sql/statements/create-symmetric-key-transact-sql) [gerenciamento extensível de chaves &#40;EKM&#41;](extensible-key-management-ekm.md) [habilitar TDE usando](enable-tde-on-sql-server-using-ekm.md) a [criptografia de backup](../../backup-restore/backup-encryption.md) do EKM [criar um backup criptografado](../../backup-restore/create-an-encrypted-backup.md)</span><span class="sxs-lookup"><span data-stu-id="f36ee-242">[CREATE CRYPTOGRAPHIC PROVIDER &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-cryptographic-provider-transact-sql) [CREATE CREDENTIAL &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-credential-transact-sql) [CREATE ASYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-asymmetric-key-transact-sql) [CREATE SYMMETRIC KEY &#40;Transact-SQL&#41;](/sql/t-sql/statements/create-symmetric-key-transact-sql) [Extensible Key Management &#40;EKM&#41;](extensible-key-management-ekm.md) [Enable TDE Using EKM](enable-tde-on-sql-server-using-ekm.md) [Backup Encryption](../../backup-restore/backup-encryption.md) [Create an Encrypted Backup](../../backup-restore/create-an-encrypted-backup.md)</span></span>
