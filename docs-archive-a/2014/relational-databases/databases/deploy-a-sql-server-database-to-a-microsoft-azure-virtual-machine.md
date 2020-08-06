---
title: Implantar um banco de dados do SQL Server em uma máquina virtual do Microsoft Azure | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: database-engine
ms.topic: conceptual
f1_keywords:
- sql12.swb.deploymentwizard.deploymentsettings.f1
- sql12.swb.deploymentwizard.progress.f1
- sql11.swb.usevmdialog.f1
- sql11.swb.deploymentwizard.f1
- sql12.swb.deploymentwizard.azuresignin.f1
- sql11.swb.deploymentwizard.summary.f1
- sql11.swb.deploymentwizard.azuresignin.f1
- sql12.swb.deploymentwizard.f1
- sql12.swb.sqlvmdialog.f1
- sql11.swb.newvmdialog.f1
- sql12.swb.deploymentwizard.results.f1
- sql11.swb.deploymentwizard.progress.f1
- sql12.swb.newvmdialog.f1
- sql12.swb.deploymentwizard.sourcesettings.f1
- sql12.swb.usevmdialog.f1
- sql11.swb.deploymentwizard.sourcesettings.f1
- sql11.swb.deploymentwizard.results.f1
- sql12.swb.deploymentwizard.summary.f1
- sql11.swb.deploymentwizard.deploymentsettings.f1
helpviewer_keywords:
- Deploy a database
- Deploy to Azure VM
- Migrate to Azure
- Azure virtual machine
- Migrate to Azure VM
- Migrate to the cloud
- SQL Server Management Studio
- SSMS
- Deploy database wizard
- Deploy a SQL Server database to Azure
- Azure VM
ms.assetid: 5e82e66a-262e-4d4f-aa89-39cb62696d06
author: stevestein
ms.author: sstein
ms.openlocfilehash: d48c06db038a775811cba6705fbaf1d97a960f6c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87683549"
---
# <a name="deploy-a-sql-server-database-to-a-microsoft-azure-virtual-machine"></a><span data-ttu-id="b34c6-102">Implantar um banco de dados do SQL Server em uma máquina virtual do Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="b34c6-102">Deploy a SQL Server Database to a Microsoft Azure Virtual Machine</span></span>
  <span data-ttu-id="b34c6-103">Use o assistente **para implantar um banco de dados SQL Server em uma VM do Azure** para implantar um banco de dados de uma instância do [!INCLUDE[ssDE](../../includes/ssde-md.md)] para [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em uma VM (máquina virtual) do Azure.</span><span class="sxs-lookup"><span data-stu-id="b34c6-103">Use the **Deploy a SQL Server Database to an Azure VM** wizard to deploy a database from an instance of the [!INCLUDE[ssDE](../../includes/ssde-md.md)] to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] in an Azure Virtual Machine (VM).</span></span> <span data-ttu-id="b34c6-104">O assistente utiliza uma operação de backup completo de banco de dados, de modo que sempre copia o esquema de banco de dados completo e os dados de um banco de dados de usuário do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b34c6-104">The wizard utilizes a full database backup operation, so it always copies the complete database schema and the data from a SQL Server user database.</span></span> <span data-ttu-id="b34c6-105">O assistente também faz toda a configuração da VM do Azure para você, de modo que nenhuma configuração prévia de VM é necessária.</span><span class="sxs-lookup"><span data-stu-id="b34c6-105">The wizard also does all of the Azure VM configuration for you, so no pre-configuration of the VM is required.</span></span>  
  
 <span data-ttu-id="b34c6-106">Você não pode usar o assistente para backups diferenciais porque o assistente não substituirá um banco de dados existente que tenha o mesmo nome.</span><span class="sxs-lookup"><span data-stu-id="b34c6-106">You cannot use the wizard for differential backups because the wizard will not overwrite an existing database that has the same database name.</span></span> <span data-ttu-id="b34c6-107">Para substituir um banco de dados existente na VM, você deverá primeiro remover o banco de dados existente ou alterar o nome dele.</span><span class="sxs-lookup"><span data-stu-id="b34c6-107">To replace an existing database on the VM, you must first drop the existing database or change the database name.</span></span> <span data-ttu-id="b34c6-108">Se houver um conflito de nomeação entre o nome do banco de dados de uma operação de implantação em curso e um banco de dados existente na VM, o assistente sugerirá um nome de banco de dados anexado para que o banco de dados em curso permita que você conclua a operação.</span><span class="sxs-lookup"><span data-stu-id="b34c6-108">If there is a naming conflict between the database name for an in-flight deploy operation and an existing database on the VM, the wizard will suggest an appended database name for the in-flight database to enable you to complete the operation.</span></span>  
  
##  <a name="before-you-begin"></a><a name="before_you_begin"></a> <span data-ttu-id="b34c6-109">Antes de começar</span><span class="sxs-lookup"><span data-stu-id="b34c6-109">Before You Begin</span></span>  
 <span data-ttu-id="b34c6-110">Para concluir esse assistente, você deve poder fornecer as informações a seguir e definir as configurações:</span><span class="sxs-lookup"><span data-stu-id="b34c6-110">To complete this wizard, you must be able to provide the following information and have these configuration settings in place:</span></span>  
  
-   <span data-ttu-id="b34c6-111">Os detalhes de conta Microsoft associados à sua assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="b34c6-111">The Microsoft account details associated with your Azure subscription.</span></span>  
  
-   <span data-ttu-id="b34c6-112">Seu perfil de publicação do Azure.</span><span class="sxs-lookup"><span data-stu-id="b34c6-112">Your Azure publishing profile.</span></span>  
  
    > [!CAUTION]  
    >  <span data-ttu-id="b34c6-113">No momento, o SQL Server oferece suporte à versão do perfil de publicação 2.0.</span><span class="sxs-lookup"><span data-stu-id="b34c6-113">SQL Server currently supports publishing profile version 2.0.</span></span> <span data-ttu-id="b34c6-114">Para baixar a versão com suporte do perfil de publicação, consulte [Download do perfil de publicação 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span><span class="sxs-lookup"><span data-stu-id="b34c6-114">To download the supported version of the publishing profile, see [Download Publishing Profile 2.0](https://go.microsoft.com/fwlink/?LinkId=396421).</span></span>  
  
-   <span data-ttu-id="b34c6-115">O certificado de gerenciamento carregado em sua assinatura do Azure.</span><span class="sxs-lookup"><span data-stu-id="b34c6-115">The management certificate uploaded to your Azure subscription.</span></span>  
  
-   <span data-ttu-id="b34c6-116">O certificado de gerenciamento salvo no repositório de certificados pessoais no computador em que o assistente sendo executado.</span><span class="sxs-lookup"><span data-stu-id="b34c6-116">The management certificate saved into the personal certificate store on the computer where the wizard is running.</span></span>  
  
-   <span data-ttu-id="b34c6-117">Você deve ter um local de armazenamento temporário que esteja disponível para o computador onde o banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] está hospedado.</span><span class="sxs-lookup"><span data-stu-id="b34c6-117">You must have a temporary storage location that is available to the computer where the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database is hosted.</span></span> <span data-ttu-id="b34c6-118">O local de armazenamento temporário também deve estar disponível para o computador onde o assistente está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="b34c6-118">The temporary storage location must also be available to the computer where the wizard is running.</span></span>  
  
-   <span data-ttu-id="b34c6-119">Se você estiver implantando o banco de dados em uma VM existente, a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] deve ser configurada para escutar em uma porta TCP/IP.</span><span class="sxs-lookup"><span data-stu-id="b34c6-119">If you are deploying the database to an existing VM, the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] must be configured to listen on a TCP/IP port.</span></span>  
  
-   <span data-ttu-id="b34c6-120">Uma imagem da galeria ou VM do Azure que você planeja usar para a criação da VM deve ter a SQL Server Adaptador de Nuvem configurada e em execução.</span><span class="sxs-lookup"><span data-stu-id="b34c6-120">Either an Azure VM or Gallery image you plan to use for creation of the VM must have the SQL Server Cloud Adapter configured and running.</span></span>  
  
-   <span data-ttu-id="b34c6-121">Você deve configurar um ponto de extremidade aberto para seu SQL Server Adaptador de Nuvem no gateway do Azure com a porta privada 11435.</span><span class="sxs-lookup"><span data-stu-id="b34c6-121">You must configure an open endpoint for your SQL Server Cloud Adapter on the Azure gateway with private port 11435.</span></span>  
  
 <span data-ttu-id="b34c6-122">Além disso, se você planeja implantar seu banco de dados em uma VM do Azure existente, você também deve ser capaz de fornecer:</span><span class="sxs-lookup"><span data-stu-id="b34c6-122">In addition, if you plan to deploy your database into an existing Azure VM, you must also be able to provide:</span></span>  
  
-   <span data-ttu-id="b34c6-123">O nome DNS do serviço de nuvem que hospeda a VM.</span><span class="sxs-lookup"><span data-stu-id="b34c6-123">The DNS name of the cloud service that hosts your VM.</span></span>  
  
-   <span data-ttu-id="b34c6-124">As credenciais do administrador para a VM.</span><span class="sxs-lookup"><span data-stu-id="b34c6-124">Administrator credentials for the VM.</span></span>  
  
-   <span data-ttu-id="b34c6-125">Credenciais com privilégios de Operador de backup no banco de dados que pretende implantar, da instância de origem do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b34c6-125">Credentials with Backup operator privileges on the database you plan to deploy, from the source instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="b34c6-126">Para obter mais informações sobre como executar SQL Server em máquinas virtuais do Azure, consulte [preparando-se para migrar para SQL Server em máquinas virtuais do Azure](https://msdn.microsoft.com/library/dn133142.aspx).</span><span class="sxs-lookup"><span data-stu-id="b34c6-126">For more information about running SQL Server in Azure virtual machines, see [Getting Ready to Migrate to SQL Server in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133142.aspx).</span></span>  
  
 <span data-ttu-id="b34c6-127">Em computadores que executam sistemas operacionais do Windows Server, você deverá usar os seguintes parâmetros de configuração para executar esse assistente:</span><span class="sxs-lookup"><span data-stu-id="b34c6-127">On computers running Windows Server operating systems, you must use the following configuration settings to run this wizard:</span></span>  
  
-   <span data-ttu-id="b34c6-128">Desative a Configuração de Segurança Avançada: use o Gerenciador do Servidor > Servidor Local para definir a ESC (Configuração de Segurança Avançada) do Internet Explorer como **OFF**.</span><span class="sxs-lookup"><span data-stu-id="b34c6-128">Turn off Enhanced Security Configuration:  Use Server Manager > Local Server to set Internet Explorer Enhanced Security Configuration (ESC) to **OFF**.</span></span>  
  
-   <span data-ttu-id="b34c6-129">Habilite o JavaScript: Internet Explorer > Opções da Internet > Segurança > Nível do Cliente > Scripts > Scripts Ativos: **Habilitar**.</span><span class="sxs-lookup"><span data-stu-id="b34c6-129">Enable JavaScript:  Internet Explorer > Internet Options > Security > Customer Level > Scripting > Active Scripting: **Enable**.</span></span>  
  
###  <a name="limitations-and-restrictions"></a><a name="limitations"></a> <span data-ttu-id="b34c6-130">Limitações e restrições</span><span class="sxs-lookup"><span data-stu-id="b34c6-130">Limitations and Restrictions</span></span>  
 <span data-ttu-id="b34c6-131">A limitação de tamanho do banco de dados para essa operação é de 1 TB.</span><span class="sxs-lookup"><span data-stu-id="b34c6-131">The database size limitation for this operation is 1 TB.</span></span>  
  
 <span data-ttu-id="b34c6-132">Esse recurso de implantação está disponível no SQL Server Management Studio para o [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span><span class="sxs-lookup"><span data-stu-id="b34c6-132">This deployment feature is available in SQL Server Management Studio for [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)].</span></span>  
  
 <span data-ttu-id="b34c6-133">Esse recurso de implantação é para uso apenas com bancos de dados de usuário; implantar bancos de dados de sistema não tem suporte.</span><span class="sxs-lookup"><span data-stu-id="b34c6-133">This deployment feature is for use only with user databases; deploying system databases is not supported.</span></span>  
  
 <span data-ttu-id="b34c6-134">O recurso de implantação não oferece suporte aos serviços hospedados associados a um grupo de afinidade.</span><span class="sxs-lookup"><span data-stu-id="b34c6-134">The deployment feature does not support hosted services that are associated with an Affinity Group.</span></span> <span data-ttu-id="b34c6-135">Por exemplo, as contas de armazenamento associadas a um grupo de afinidade não podem ser selecionadas para uso na página **Configurações de Implantação** desse assistente.</span><span class="sxs-lookup"><span data-stu-id="b34c6-135">For example, storage accounts associated with an Affinity Group cannot be selected for use on the **Deployment Settings** page of this wizard.</span></span>  
  
 <span data-ttu-id="b34c6-136">A versão do SQL Server na VM deve ser o mesmo ou posterior que a versão do SQL Server de origem.</span><span class="sxs-lookup"><span data-stu-id="b34c6-136">The SQL Server version in the VM must be the same or later than the source SQL Server version.</span></span> <span data-ttu-id="b34c6-137">SQL Server versões de banco de dados que podem ser implantadas em uma VM do Azure usando este assistente:</span><span class="sxs-lookup"><span data-stu-id="b34c6-137">SQL Server database versions that can be deployed to an Azure VM using this wizard:</span></span>  
  
-   <span data-ttu-id="b34c6-138">SQL Server 2008</span><span class="sxs-lookup"><span data-stu-id="b34c6-138">SQL Server 2008</span></span>  
  
-   <span data-ttu-id="b34c6-139">SQL Server 2008 R2</span><span class="sxs-lookup"><span data-stu-id="b34c6-139">SQL Server 2008 R2</span></span>  
  
-   <span data-ttu-id="b34c6-140">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="b34c6-140">SQL Server 2012</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
 <span data-ttu-id="b34c6-141">SQL Server versões de banco de dados executadas em um banco de dados de VM do Azure podem ser implantadas em:</span><span class="sxs-lookup"><span data-stu-id="b34c6-141">SQL Server database versions running in an Azure VM database can be deployed to:</span></span>  
  
-   <span data-ttu-id="b34c6-142">SQL Server 2012</span><span class="sxs-lookup"><span data-stu-id="b34c6-142">SQL Server 2012</span></span>  
  
-   [!INCLUDE[ssSQL14](../../includes/sssql14-md.md)]  
  
 <span data-ttu-id="b34c6-143">Se houver um conflito de nomeação entre o nome do banco de dados de uma operação de implantação em curso e um banco de dados existente na VM, o assistente sugerirá um nome de banco de dados anexado para que o banco de dados em curso permita que você conclua a operação.</span><span class="sxs-lookup"><span data-stu-id="b34c6-143">If there is a naming conflict between the database name for an in-flight deploy operation and an existing database on the VM, the wizard will suggest an appended database name for the in-flight database to enable you to complete the operation.</span></span>  
  
###  <a name="considerations-for-deploying-a-filestream-enabled-database-to-an-azure-vm"></a><a name="filestream"></a> <span data-ttu-id="b34c6-144">Considerações para implantar um banco de dados habilitado para FILESTREAM em uma VM do Azure</span><span class="sxs-lookup"><span data-stu-id="b34c6-144">Considerations for Deploying a FILESTREAM-enabled Database to an Azure VM</span></span>  
 <span data-ttu-id="b34c6-145">Observe as seguintes diretrizes e restrições ao implantar bancos de dados com BLOBS armazenados em objetos FILESTREAM:</span><span class="sxs-lookup"><span data-stu-id="b34c6-145">Note the following guidelines and restrictions when deploying databases that have BLOBS stored in FILESTREAM objects:</span></span>  
  
-   <span data-ttu-id="b34c6-146">O recurso de implantação não pode implantar um banco de dados habilitado para FILESTREAM em uma nova VM.</span><span class="sxs-lookup"><span data-stu-id="b34c6-146">The deployment feature cannot deploy a FILESTREAM-enabled database into a new VM.</span></span> <span data-ttu-id="b34c6-147">Se FILESTREAM não estiver habilitado na VM antes da execução do assistente, a operação de restauração do banco de dados falhará e a operação do assistente não poderá ser concluída com êxito.</span><span class="sxs-lookup"><span data-stu-id="b34c6-147">If FILESTREAM is not enabled in the VM before you run the wizard, the database restore operation will fail and the wizard operation will not be able to complete successfully.</span></span> <span data-ttu-id="b34c6-148">Para implantar com êxito um banco de dados que usa FILESTREAM, habilite-o na instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] na VM do host antes de iniciar o assistente.</span><span class="sxs-lookup"><span data-stu-id="b34c6-148">To successfully deploy a database that uses FILESTREAM, enable FILESTREAM in the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] on the host VM before launching the wizard.</span></span> <span data-ttu-id="b34c6-149">Para obter mais informações, veja [FILESTREAM (SQL Server)](https://msdn.microsoft.com/library/gg471497.aspx).</span><span class="sxs-lookup"><span data-stu-id="b34c6-149">For more information, see [FILESTREAM (SQL Server)](https://msdn.microsoft.com/library/gg471497.aspx).</span></span>  
  
-   <span data-ttu-id="b34c6-150">Se seu banco de dados utiliza OLTP na memória, você pode implantar o banco de dados na VM do Azure sem modificações no banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b34c6-150">If your database utilizes In-Memory OLTP, you can deploy the database to an Azure VM without any modifications to the database.</span></span> <span data-ttu-id="b34c6-151">Para obter mais informações, veja [OLTP in-memory (otimização na memória)](https://msdn.microsoft.com/library/dn133186\(SQL.120\).aspx).</span><span class="sxs-lookup"><span data-stu-id="b34c6-151">For more information, see [In-Memory OLTP (In-Memory Optimization)](https://msdn.microsoft.com/library/dn133186\(SQL.120\).aspx).</span></span>  
  
###  <a name="considerations-for-geographic-distribution-of-assets"></a><a name="geography"></a><span data-ttu-id="b34c6-152">Considerações sobre a distribuição geográfica de ativos</span><span class="sxs-lookup"><span data-stu-id="b34c6-152">Considerations for Geographic Distribution of Assets</span></span>  
 <span data-ttu-id="b34c6-153">Observe que os seguintes recursos devem estar localizados na mesma região geográfica:</span><span class="sxs-lookup"><span data-stu-id="b34c6-153">Note that the following assets must be located in the same geographic region:</span></span>  
  
-   <span data-ttu-id="b34c6-154">Serviço de Nuvem</span><span class="sxs-lookup"><span data-stu-id="b34c6-154">Cloud Service</span></span>  
  
-   <span data-ttu-id="b34c6-155">Local da VM</span><span class="sxs-lookup"><span data-stu-id="b34c6-155">VM Location</span></span>  
  
-   <span data-ttu-id="b34c6-156">Serviço de armazenamento de disco de dados</span><span class="sxs-lookup"><span data-stu-id="b34c6-156">Data Disk Storage Service</span></span>  
  
 <span data-ttu-id="b34c6-157">Se os recursos listados acima não forem colocalizados, o assistente não poderá ser concluído com êxito.</span><span class="sxs-lookup"><span data-stu-id="b34c6-157">If the assets listed above are not co-located, the wizard will not be able to complete successfully.</span></span>  
  
###  <a name="wizard-configuration-settings"></a><a name="configuration_settings"></a><span data-ttu-id="b34c6-158">Definições de configuração do assistente</span><span class="sxs-lookup"><span data-stu-id="b34c6-158">Wizard Configuration Settings</span></span>  
 <span data-ttu-id="b34c6-159">Use os detalhes de configuração a seguir para modificar as configurações de uma implantação de banco de dados do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para uma VM do Azure.</span><span class="sxs-lookup"><span data-stu-id="b34c6-159">Use the following configuration details to modify settings for a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database deployment to an Azure VM.</span></span>  
  
-   <span data-ttu-id="b34c6-160">**Caminho padrão para o arquivo de configuração** – %LOCALAPPDATA%\SQL Server\Deploy to SQL in WA VM\DeploymentSettings.xml</span><span class="sxs-lookup"><span data-stu-id="b34c6-160">**Default path for the configuration file** - %LOCALAPPDATA%\SQL Server\Deploy to SQL in WA VM\DeploymentSettings.xml</span></span>  
  
-   <span data-ttu-id="b34c6-161">**Estrutura do arquivo de configuração**</span><span class="sxs-lookup"><span data-stu-id="b34c6-161">**Configuration file structure**</span></span>  
  
    -   \<DeploymentSettings>  
  
        -   <span data-ttu-id="b34c6-162"><OtherSettings</span><span class="sxs-lookup"><span data-stu-id="b34c6-162"><OtherSettings</span></span>  
  
            -   <span data-ttu-id="b34c6-163">TraceLevel = "depurar"\<!-- Logging level --></span><span class="sxs-lookup"><span data-stu-id="b34c6-163">TraceLevel="Debug" \<!-- Logging level --></span></span>  
  
            -   <span data-ttu-id="b34c6-164">BackupPath = " \\ \\ [nome do servidor] \\ [volume] \\ "\<!-- The last used path for backup. Used as default in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="b34c6-164">BackupPath="\\\\[server name]\\[volume]\\" \<!-- The last used path for backup. Used as default in the wizard. --></span></span>  
  
            -   <span data-ttu-id="b34c6-165">CleanupDisabled = false/>\<!-- Wizard will not delete intermediate files and Azure objects (VM, CS, SA). --></span><span class="sxs-lookup"><span data-stu-id="b34c6-165">CleanupDisabled = False /> \<!-- Wizard will not delete intermediate files and Azure objects (VM, CS, SA). --></span></span>  
  
        -   <span data-ttu-id="b34c6-166"><PublishProfile\<!-- The last used publish profile information. --></span><span class="sxs-lookup"><span data-stu-id="b34c6-166"><PublishProfile \<!-- The last used publish profile information. --></span></span>  
  
            -   <span data-ttu-id="b34c6-167">Certificado = "12A34B567890123ABCD4EF567A8"\<!-- The certificate for use in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="b34c6-167">Certificate="12A34B567890123ABCD4EF567A8" \<!-- The certificate for use in the wizard. --></span></span>  
  
            -   <span data-ttu-id="b34c6-168">Subscription = "1a2b34c5-67d8-90ef-AB12-xxxxxxxxxxxxx"\<!-- The subscription for use in the wizard. --></span><span class="sxs-lookup"><span data-stu-id="b34c6-168">Subscription="1a2b34c5-67d8-90ef-ab12-xxxxxxxxxxxxx" \<!-- The subscription for use in the wizard. --></span></span>  
  
            -   <span data-ttu-id="b34c6-169">Nome = "minha assinatura"\<!-- The name of the subscription. --></span><span class="sxs-lookup"><span data-stu-id="b34c6-169">Name="My Subscription" \<!-- The name of the subscription. --></span></span>  
  
            -   <span data-ttu-id="b34c6-170">Publisher="" /></span><span class="sxs-lookup"><span data-stu-id="b34c6-170">Publisher="" /></span></span>  
  
    -   \</DeploymentSettings>  
  
 <span data-ttu-id="b34c6-171">**Valores do arquivo de configuração**</span><span class="sxs-lookup"><span data-stu-id="b34c6-171">**Configuration file values**</span></span>  
  
###  <a name="permissions"></a><a name="permissions"></a> <span data-ttu-id="b34c6-172">Permissões</span><span class="sxs-lookup"><span data-stu-id="b34c6-172">Permissions</span></span>  
 <span data-ttu-id="b34c6-173">O banco de dados que está sendo implantado deve estar em um estado normal e deve ser acessível à conta de usuário que executa o assistente. A conta de usuário deve ter permissões para executar uma operação de backup.</span><span class="sxs-lookup"><span data-stu-id="b34c6-173">The database being deployed must be in a normal state, the database must be accessible to the user account running the wizard, and the user account must have permissions to perform a backup operation.</span></span>  
  
##  <a name="using-the-deploy-database-to-azure-vm-wizard"></a><a name="launch_wizard"></a><span data-ttu-id="b34c6-174">Usando o assistente para implantar banco de dados para VM do Azure</span><span class="sxs-lookup"><span data-stu-id="b34c6-174">Using the Deploy Database to Azure VM Wizard</span></span>  
 <span data-ttu-id="b34c6-175">**Para iniciar o assistente, use as seguintes etapas:**</span><span class="sxs-lookup"><span data-stu-id="b34c6-175">**To launch the wizard, use the following steps:**</span></span>  
  
1.  <span data-ttu-id="b34c6-176">Use o SQL Server Management Studio para se conectar à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com o banco de dados que deseja implantar.</span><span class="sxs-lookup"><span data-stu-id="b34c6-176">Use SQL Server Management Studio to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] with the database you want to deploy.</span></span>  
  
2.  <span data-ttu-id="b34c6-177">No **Pesquisador de Objetos**, expanda o nome da instância e o nó **Bancos de Dados** .</span><span class="sxs-lookup"><span data-stu-id="b34c6-177">In **Object Explorer**, expand the instance name, then expand the **Databases** node.</span></span>  
  
3.  <span data-ttu-id="b34c6-178">Clique com o botão direito do mouse no banco de dados que você deseja implantar, selecione **tarefas**e, em seguida, selecione **implantar banco de dados na VM do Azure...**</span><span class="sxs-lookup"><span data-stu-id="b34c6-178">Right-click the database you want to deploy, select **Tasks**, and then select **Deploy Database to Azure VM...**</span></span>  
  

  
##  <a name="introduction-page"></a><a name="Introduction"></a> <span data-ttu-id="b34c6-179">Página de Introdução</span><span class="sxs-lookup"><span data-stu-id="b34c6-179">Introduction Page</span></span>  
 <span data-ttu-id="b34c6-180">Esta página descreve o assistente **para implantar um SQL Server banco de dados em uma VM do Azure** .</span><span class="sxs-lookup"><span data-stu-id="b34c6-180">This page describes the **Deploy a SQL Server Database to an Azure VM** wizard.</span></span>  
  
 <span data-ttu-id="b34c6-181">**Opções**</span><span class="sxs-lookup"><span data-stu-id="b34c6-181">**Options**</span></span>  
  
-   <span data-ttu-id="b34c6-182">**Não mostrar esta página novamente.**</span><span class="sxs-lookup"><span data-stu-id="b34c6-182">**Do not show this page again.**</span></span> <span data-ttu-id="b34c6-183">- Clique nesta caixa de seleção para não exibir mais a página Introdução no futuro.</span><span class="sxs-lookup"><span data-stu-id="b34c6-183">- Click this check box to stop the Introduction page from being displayed in the future.</span></span>  
  
-   <span data-ttu-id="b34c6-184">**Avançar** - continua na página **Configurações de Origem** .</span><span class="sxs-lookup"><span data-stu-id="b34c6-184">**Next** - Proceeds to the **Source Settings** page.</span></span>  
  
-   <span data-ttu-id="b34c6-185">**Cancelar** – cancela a operação e fecha o assistente.</span><span class="sxs-lookup"><span data-stu-id="b34c6-185">**Cancel** - Cancels the operation and closes the wizard.</span></span>  
  
-   <span data-ttu-id="b34c6-186">**Ajuda** -inicia o tópico da ajuda do MSDN para o assistente.</span><span class="sxs-lookup"><span data-stu-id="b34c6-186">**Help** - Launches the MSDN Help topic for the wizard.</span></span>  
  
##  <a name="source-settings"></a><a name="Source_settings"></a><span data-ttu-id="b34c6-187">Configurações de origem</span><span class="sxs-lookup"><span data-stu-id="b34c6-187">Source Settings</span></span>  
 <span data-ttu-id="b34c6-188">Use esta página para se conectar à instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda o banco de dados que você deseja implantar na VM do Azure.</span><span class="sxs-lookup"><span data-stu-id="b34c6-188">Use this page to connect to the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the database you want to deploy to the Azure VM.</span></span> <span data-ttu-id="b34c6-189">Você também especificará um local temporário para os arquivos a serem salvos no computador local antes de serem transferidos para o Azure.</span><span class="sxs-lookup"><span data-stu-id="b34c6-189">You will also specify a temporary location for files to be saved from the local machine before they are transferred to Azure.</span></span> <span data-ttu-id="b34c6-190">Pode ser um local de rede compartilhado.</span><span class="sxs-lookup"><span data-stu-id="b34c6-190">This can be a shared, network location.</span></span>  
  
 <span data-ttu-id="b34c6-191">**Opções**</span><span class="sxs-lookup"><span data-stu-id="b34c6-191">**Options**</span></span>  
  
-   <span data-ttu-id="b34c6-192">Clique em **conectar...** e especifique os detalhes da conexão para a instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] que hospeda o banco de dados a ser implantado.</span><span class="sxs-lookup"><span data-stu-id="b34c6-192">Click **Connect...** and then specify connection details for the instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] that hosts the database to deploy.</span></span>  
  
-   <span data-ttu-id="b34c6-193">Use a lista suspensa **Selecionar Banco de Dados** para especificar o banco de dados a ser implantado.</span><span class="sxs-lookup"><span data-stu-id="b34c6-193">Use the **Select Database** drop-down list to specify the database to deploy.</span></span>  
  
-   <span data-ttu-id="b34c6-194">No campo **outras configurações** , especifique uma pasta compartilhada que poderá ser acessada pelo serviço de VM do Azure.</span><span class="sxs-lookup"><span data-stu-id="b34c6-194">In the **Other Settings** field, specify a shared folder that will be accessible to the Azure VM service.</span></span>  
  
##  <a name="azure-sign-in"></a><a name="Azure_sign-in"></a><span data-ttu-id="b34c6-195">Entrada do Azure</span><span class="sxs-lookup"><span data-stu-id="b34c6-195">Azure Sign-in</span></span>  
 <span data-ttu-id="b34c6-196">Use esta página para se conectar ao Azure e fornecer o certificado de gerenciamento ou os detalhes do perfil de publicação.</span><span class="sxs-lookup"><span data-stu-id="b34c6-196">Use this page to connect to Azure and provide management certificate or publishing profile details.</span></span>  
  
 <span data-ttu-id="b34c6-197">**Opções**</span><span class="sxs-lookup"><span data-stu-id="b34c6-197">**Options**</span></span>  
  
-   <span data-ttu-id="b34c6-198">**Certificado de gerenciamento** -Use essa opção para especificar um certificado do repositório de certificados local que corresponde ao certificado de gerenciamento do Azure.</span><span class="sxs-lookup"><span data-stu-id="b34c6-198">**Management Certificate** - Use this option to specify a certificate from the local certificate store that matches the management certificate from Azure.</span></span>  
  
-   <span data-ttu-id="b34c6-199">**Perfil de publicação** – Use essa opção se você já tiver um perfil de publicação baixado em seu computador.</span><span class="sxs-lookup"><span data-stu-id="b34c6-199">**Publishing Profile** - Use this option if you already have a publishing profile downloaded to your computer.</span></span>  
  
-   <span data-ttu-id="b34c6-200">**Entrar** -Use esta opção para entrar no Azure usando um conta Microsoft-por exemplo, uma conta do Live ID ou do hotmail-para gerar e baixar um novo certificado de gerenciamento.</span><span class="sxs-lookup"><span data-stu-id="b34c6-200">**Sign In** - Use this option to sign in to Azure using a Microsoft account - for example, a Live ID or Hotmail account - to generate and download a new management certificate.</span></span> <span data-ttu-id="b34c6-201">Observe que o número de certificados por assinatura é limitado.</span><span class="sxs-lookup"><span data-stu-id="b34c6-201">Note that the number of certificates per subscription is limited.</span></span>  
  
-   <span data-ttu-id="b34c6-202">**Assinatura** – selecione, digite ou cole sua ID de assinatura do Azure que corresponda ao certificado de gerenciamento do repositório de certificados local ou de um perfil de publicação.</span><span class="sxs-lookup"><span data-stu-id="b34c6-202">**Subscription** - Select, type, or paste your Azure subscription ID that matches the management certificate from the local certificate store or a publishing profile.</span></span>  
  
##  <a name="deployment-settings-page"></a><a name="Deployment_settings"></a><span data-ttu-id="b34c6-203">Página Configurações de implantação</span><span class="sxs-lookup"><span data-stu-id="b34c6-203">Deployment Settings Page</span></span>  
 <span data-ttu-id="b34c6-204">Use esta página para especificar o servidor de destino e fornecer detalhes sobre seu novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b34c6-204">Use this page to specify the destination server and to provide details about your new database.</span></span>  
  
 <span data-ttu-id="b34c6-205">**Opções**</span><span class="sxs-lookup"><span data-stu-id="b34c6-205">**Options**</span></span>  
  
-   <span data-ttu-id="b34c6-206">**Máquina virtual do Azure** -especifique os detalhes da VM que hospedará o banco de dados de SQL Server:</span><span class="sxs-lookup"><span data-stu-id="b34c6-206">**Azure Virtual Machine** - Specify details for the VM that will host the SQL Server database:</span></span>  
  
-   <span data-ttu-id="b34c6-207">**Nome do serviço de nuvem** – especifique o nome do serviço que hospeda a VM.</span><span class="sxs-lookup"><span data-stu-id="b34c6-207">**Cloud Service name** - Specify the name of the service that hosts the VM.</span></span> <span data-ttu-id="b34c6-208">Para criar um novo Serviço em Nuvem, especifique um nome para o novo Serviço em Nuvem.</span><span class="sxs-lookup"><span data-stu-id="b34c6-208">To create a new Cloud Service, specify a name for the new Cloud Service.</span></span>  
  
-   <span data-ttu-id="b34c6-209">**Nome da máquina virtual** – especifique o nome da VM que hospedará o banco de dados SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b34c6-209">**Virtual Machine name** - Specify the name of the VM that will host the SQL Server database.</span></span> <span data-ttu-id="b34c6-210">Para criar uma nova VM do Azure, especifique um nome para a nova VM.</span><span class="sxs-lookup"><span data-stu-id="b34c6-210">To create a new Azure VM, specify a name for the new VM.</span></span>  
  
-   <span data-ttu-id="b34c6-211">**Configurações** – use o botão configurações para criar uma nova VM para hospedar o banco de dados SQL Server.</span><span class="sxs-lookup"><span data-stu-id="b34c6-211">**Settings** - Use the Settings button to create a new VM to host the SQL Server database.</span></span> <span data-ttu-id="b34c6-212">Se você estiver usando uma VM existente, as informações fornecidas serão usadas para autenticar suas credenciais.</span><span class="sxs-lookup"><span data-stu-id="b34c6-212">If you are using an existing VM, the information you provide will be used to authenticate your credentials.</span></span>  
  
-   <span data-ttu-id="b34c6-213">**Conta de armazenamento** – selecione a conta de armazenamento na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="b34c6-213">**Storage account** - Select the storage account from the drop-down list.</span></span> <span data-ttu-id="b34c6-214">Para criar uma nova conta de armazenamento, especifique um nome para a nova conta.</span><span class="sxs-lookup"><span data-stu-id="b34c6-214">To create a new storage account, specify a name for the new account.</span></span> <span data-ttu-id="b34c6-215">Observe que as contas de armazenamento associadas a um grupo de afinidade não estarão disponíveis na lista suspensa.</span><span class="sxs-lookup"><span data-stu-id="b34c6-215">Note that storage accounts associated with an Affinity Group will not be available in the drop-down list.</span></span>  
  
-   <span data-ttu-id="b34c6-216">**Banco de dados de destino** -especifique os detalhes do banco de dados de destino.</span><span class="sxs-lookup"><span data-stu-id="b34c6-216">**Target Database** - Specify details for the target database.</span></span>  
  
-   <span data-ttu-id="b34c6-217">**Conexão do servidor** -detalhes de conexão do servidor.</span><span class="sxs-lookup"><span data-stu-id="b34c6-217">**Server Connection** - Connection details for the server.</span></span>  
  
-   <span data-ttu-id="b34c6-218">**Banco de dados** -especifique ou confirme o nome de um novo banco de dados.</span><span class="sxs-lookup"><span data-stu-id="b34c6-218">**Database** - Specify or confirm the name of a new database.</span></span> <span data-ttu-id="b34c6-219">Se o nome do banco de dados já existir na instância do SQL Server de destino, sugerimos especificar um nome de banco de dados modificado.</span><span class="sxs-lookup"><span data-stu-id="b34c6-219">If the database name already exists on the destination SQL Server instance, we suggest that you specify a modified database name.</span></span>  
  
##  <a name="summary-page"></a><a name="Summary"></a> <span data-ttu-id="b34c6-220">Página de Resumo</span><span class="sxs-lookup"><span data-stu-id="b34c6-220">Summary Page</span></span>  
 <span data-ttu-id="b34c6-221">Use essa página para analisar as configurações especificadas da operação.</span><span class="sxs-lookup"><span data-stu-id="b34c6-221">Use this page to review the specified settings for the operation.</span></span> <span data-ttu-id="b34c6-222">Para concluir a operação de implantação usando as configurações especificadas, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="b34c6-222">To complete the deploy operation using the specified settings, click **Finish**.</span></span> <span data-ttu-id="b34c6-223">Para cancelar a operação de implantação e sair do assistente, clique em **Cancelar**.</span><span class="sxs-lookup"><span data-stu-id="b34c6-223">To cancel the deploy operation and exit the wizard, click **Cancel**.</span></span>  
  
 <span data-ttu-id="b34c6-224">Pode haver etapas manuais necessárias para implantar detalhes do banco de dados no banco de dados SQL Server na VM do Azure.</span><span class="sxs-lookup"><span data-stu-id="b34c6-224">There may be manual steps required to deploy database details to the SQL Server database on the Azure VM.</span></span> <span data-ttu-id="b34c6-225">Essas etapas serão descritas em detalhes para você.</span><span class="sxs-lookup"><span data-stu-id="b34c6-225">These steps will be outlined in detail for you.</span></span>  
  
##  <a name="results-page"></a><a name="Results"></a><span data-ttu-id="b34c6-226">Página de resultados</span><span class="sxs-lookup"><span data-stu-id="b34c6-226">Results Page</span></span>  
 <span data-ttu-id="b34c6-227">Esta página reporta o êxito ou falha da operação de implantação, mostrando os resultados de cada ação.</span><span class="sxs-lookup"><span data-stu-id="b34c6-227">This page reports the success or failure of the deploy operation, showing the results of each action.</span></span> <span data-ttu-id="b34c6-228">Todas as ações que encontrarem um erro terão uma indicação na coluna **Resultado** .</span><span class="sxs-lookup"><span data-stu-id="b34c6-228">Any action that encountered an error will have an indication in the **Result** column.</span></span> <span data-ttu-id="b34c6-229">Clique no link para exibir um relatório do erro para essa ação.</span><span class="sxs-lookup"><span data-stu-id="b34c6-229">Click the link to view a report of the error for that action.</span></span>  
  
 <span data-ttu-id="b34c6-230">Clique em **Concluir** para fechar o assistente.</span><span class="sxs-lookup"><span data-stu-id="b34c6-230">Click **Finish** to close the wizard.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="b34c6-231">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="b34c6-231">See Also</span></span>  
 <span data-ttu-id="b34c6-232">[Adaptador de Nuvem para SQL Server](../../database-engine/cloud-adapter-for-sql-server.md) </span><span class="sxs-lookup"><span data-stu-id="b34c6-232">[Cloud Adapter for SQL Server](../../database-engine/cloud-adapter-for-sql-server.md) </span></span>  
 <span data-ttu-id="b34c6-233">[Gerenciamento do ciclo de vida do banco](../database-lifecycle-management.md) </span><span class="sxs-lookup"><span data-stu-id="b34c6-233">[Database Lifecycle Management](../database-lifecycle-management.md) </span></span>  
 <span data-ttu-id="b34c6-234">[Exportar um aplicativo da camada de dados](../data-tier-applications/export-a-data-tier-application.md) </span><span class="sxs-lookup"><span data-stu-id="b34c6-234">[Export a Data-tier Application](../data-tier-applications/export-a-data-tier-application.md) </span></span>  
 <span data-ttu-id="b34c6-235">[Importar um arquivo BACPAC para criar um novo banco de dados de usuário](../data-tier-applications/import-a-bacpac-file-to-create-a-new-user-database.md) </span><span class="sxs-lookup"><span data-stu-id="b34c6-235">[Import a BACPAC File to Create a New User Database](../data-tier-applications/import-a-bacpac-file-to-create-a-new-user-database.md) </span></span>  
 <span data-ttu-id="b34c6-236">[Backup e restauração do banco de dados SQL do Azure](https://msdn.microsoft.com/library/azure/jj650016.aspx) </span><span class="sxs-lookup"><span data-stu-id="b34c6-236">[Azure SQL Database Backup and Restore](https://msdn.microsoft.com/library/azure/jj650016.aspx) </span></span>  
 <span data-ttu-id="b34c6-237">[Implantação de SQL Server em máquinas virtuais do Azure](https://msdn.microsoft.com/library/dn133141.aspx) </span><span class="sxs-lookup"><span data-stu-id="b34c6-237">[SQL Server Deployment in Azure Virtual Machines](https://msdn.microsoft.com/library/dn133141.aspx) </span></span>  
 [<span data-ttu-id="b34c6-238">Preparando-se para migrar para o SQL Server em Máquinas Virtuais do Azure</span><span class="sxs-lookup"><span data-stu-id="b34c6-238">Getting Ready to Migrate to SQL Server in Azure Virtual Machines</span></span>](https://msdn.microsoft.com/library/dn133142.aspx)  
  
  
