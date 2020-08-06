---
title: Instalar o SQL Server 2014 usando um arquivo de configuração | Microsoft Docs
ms.custom: ''
ms.date: 01/20/2016
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: install
ms.topic: conceptual
ms.assetid: a832153a-6775-4bed-83f0-55790766d885
author: MashaMSFT
ms.author: mathoma
ms.openlocfilehash: a2f09ad6253762fe5b525f6c918931f4806c84c7
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679494"
---
# <a name="install-sql-server-2014-using-a-configuration-file"></a><span data-ttu-id="8ed00-102">Instalar o SQL Server 2014 usando um arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="8ed00-102">Install SQL Server 2014 Using a Configuration File</span></span>
  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8ed00-103">A Instalação fornece a capacidade de gerar um arquivo de configuração baseado no padrão do sistema e em entradas de tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="8ed00-103">Setup provides the ability to generate a configuration file based upon the system default and run-time inputs.</span></span> <span data-ttu-id="8ed00-104">É possível usar o arquivo de configuração para implantar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] em toda a empresa com a mesma configuração.</span><span class="sxs-lookup"><span data-stu-id="8ed00-104">You can use the configuration file to deploy [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] throughout the enterprise with the same configuration.</span></span> <span data-ttu-id="8ed00-105">Também é possível padronizar instalações manuais em toda a empresa criando um arquivo em lotes que inicie o Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="8ed00-105">You can also standardize manual installations throughout the enterprise, by creating a batch file that launches Setup.exe.</span></span>  
  
 <span data-ttu-id="8ed00-106">A Instalação dá suporte ao uso do arquivo de configuração apenas através do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="8ed00-106">Setup supports the use of the configuration file only through the command prompt.</span></span> <span data-ttu-id="8ed00-107">A ordem de processamento dos parâmetros ao usar o arquivo de configuração é descrita a seguir:</span><span class="sxs-lookup"><span data-stu-id="8ed00-107">The processing order of the parameters while using the configuration file is outlined below:</span></span>  
  
-   <span data-ttu-id="8ed00-108">O arquivo de configuração substitui os padrões em um pacote</span><span class="sxs-lookup"><span data-stu-id="8ed00-108">The configuration file overwrites the defaults in a package</span></span>  
  
-   <span data-ttu-id="8ed00-109">Os valores da linha de comando substituem os valores do arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="8ed00-109">Command-line values overwrite the values in the configuration file</span></span>  
  
 <span data-ttu-id="8ed00-110">O arquivo de configuração pode ser usado para acompanhar os parâmetros e valores de cada instalação.</span><span class="sxs-lookup"><span data-stu-id="8ed00-110">The configuration file can be used to track the parameters and values for each installation.</span></span> <span data-ttu-id="8ed00-111">Isto torna o arquivo de configuração útil para verificar e auditar as instalações.</span><span class="sxs-lookup"><span data-stu-id="8ed00-111">This makes the configuration file useful for verifying and auditing the installations.</span></span>  
  
## <a name="configuration-file-structure"></a><span data-ttu-id="8ed00-112">Estrutura do arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="8ed00-112">Configuration File Structure</span></span>  
 <span data-ttu-id="8ed00-113">O ConfigurationFile.ini é um arquivo de texto com parâmetros (par de nome/valor) e comentários descritivos.</span><span class="sxs-lookup"><span data-stu-id="8ed00-113">The ConfigurationFile.ini file is a text file with parameters (name/value pair) and descriptive comments.</span></span>  
  
 <span data-ttu-id="8ed00-114">O seguinte exemplo é de um arquivo ConfigurationFile.ini:</span><span class="sxs-lookup"><span data-stu-id="8ed00-114">The following is an example of a ConfigurationFile.ini file:</span></span>  
  
```  
; Microsoft SQL Server Configuration file  
[OPTIONS]  
; Specifies a Setup work flow, like INSTALL, UNINSTALL, or UPGRADE.   
; This is a required parameter.   
ACTION="Install"  
; Specifies features to install, uninstall, or upgrade.   
; The list of top-level features include SQL, AS, RS, IS, and Tools.   
; The SQL feature will install the database engine, replication, and full-text.   
; The Tools feature will install Management Tools, Books online,   
; SQL Server Data Tools, and other shared components.   
FEATURES=SQL,Tools  
```  
  
#### <a name="how-to-generate-a-configuration-file"></a><span data-ttu-id="8ed00-115">Como gerar um arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="8ed00-115">How to generate a configuration file</span></span>  
  
1.  <span data-ttu-id="8ed00-116">Insira a mídia de instalação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="8ed00-116">Insert the [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] installation media.</span></span> <span data-ttu-id="8ed00-117">Na pasta raiz, clique duas vezes em Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="8ed00-117">From the root folder, double-click Setup.exe.</span></span> <span data-ttu-id="8ed00-118">Para instalar a partir de um compartilhamento de rede, localize a pasta raiz no compartilhamento e clique duas vezes em Setup.exe.</span><span class="sxs-lookup"><span data-stu-id="8ed00-118">To install from a network share, locate the root folder on the share, and then double-click Setup.exe.</span></span>  
  
    > [!NOTE]  
    >  [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] <span data-ttu-id="8ed00-119">Express Edition não cria um arquivo de configuração automaticamente.</span><span class="sxs-lookup"><span data-stu-id="8ed00-119">Express Edition setup does not create a configuration file automatically.</span></span> <span data-ttu-id="8ed00-120">O comando a seguir iniciará a instalação e criará um arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="8ed00-120">The following command will start  setup and create a configuration file.</span></span>  
    >   
    >  <span data-ttu-id="8ed00-121">SETUP.exe /UIMODE=Normal /ACTION=INSTALL</span><span class="sxs-lookup"><span data-stu-id="8ed00-121">SETUP.exe /UIMODE=Normal /ACTION=INSTALL</span></span>  
  
2.  <span data-ttu-id="8ed00-122">Conclua o assistente até a página **Pronto para Instalar** .</span><span class="sxs-lookup"><span data-stu-id="8ed00-122">Follow the wizard through to the **Ready to Install** page.</span></span> <span data-ttu-id="8ed00-123">O caminho para o arquivo de configuração é especificado na página **Pronto para Instalar** na seção do caminho do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="8ed00-123">The path to the configuration file is specified in the **Ready to Install** page in the configuration file path section.</span></span> <span data-ttu-id="8ed00-124">Para obter mais informações sobre como instalar [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] o, consulte [instalar SQL Server 2014 do assistente de instalação &#40;&#41;de ](install-sql-server-from-the-installation-wizard-setup.md)instalação.</span><span class="sxs-lookup"><span data-stu-id="8ed00-124">For more information about how to install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], see [Install SQL Server 2014 from the Installation Wizard &#40;Setup&#41;](install-sql-server-from-the-installation-wizard-setup.md).</span></span>  
  
3.  <span data-ttu-id="8ed00-125">Cancele a instalação sem realmente concluí-la para gerar o arquivo INI.</span><span class="sxs-lookup"><span data-stu-id="8ed00-125">Cancel the setup without actually completing the installation, to generate the INI file.</span></span>  
  
    > [!NOTE]  
    >  <span data-ttu-id="8ed00-126">A infraestrutura da instalação gravará todos os parâmetros adequados para as ações que foram executadas, com exceção de informações confidencias, como senhas.</span><span class="sxs-lookup"><span data-stu-id="8ed00-126">The setup infrastructure writes out all the appropriate parameters for the actions that were run, with the exception of sensitive information such as passwords.</span></span> <span data-ttu-id="8ed00-127">O parâmetro /IAcceptSQLServerLicenseTerms também não é gravado no arquivo de configuração e requer uma modificação do arquivo de configuração ou um valor a ser fornecido no prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="8ed00-127">The /IAcceptSQLServerLicenseTerms parameter is also not written out to the configuration file and requires either a modification of the configuration file or a value to be supplied at the command prompt.</span></span> <span data-ttu-id="8ed00-128">Para obter mais informações, consulte [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) (Instalar o SQL Server 2014 do Prompt de Comando).</span><span class="sxs-lookup"><span data-stu-id="8ed00-128">For more information, see [Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md).</span></span> <span data-ttu-id="8ed00-129">Além disso, um valor é incluído para os parâmetros boolianos onde um valor geralmente não é fornecido por meio do prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="8ed00-129">In addition, a value is included for Boolean parameters where a value is usually not supplied through the command prompt.</span></span>  
  
## <a name="using-the-configuration-file-to-install-ssnoversion"></a><span data-ttu-id="8ed00-130">Usando o arquivo de configuração para instalar o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ed00-130">Using the Configuration File to Install [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span></span>  
 <span data-ttu-id="8ed00-131">É possível usar o arquivo de configuração apenas em instalações de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="8ed00-131">You can only use the configuration file on command-line installations.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8ed00-132">Se você precisar fazer alterações no arquivo de configuração, é recomendável fazer uma cópia e trabalhar com a cópia.</span><span class="sxs-lookup"><span data-stu-id="8ed00-132">If you need to make changes to the configuration file, we recommend that you make a copy and work with the copy.</span></span>  
  
#### <a name="how-to-use-a-configuration-file-to-install-a-stand-alone-ssnoversion-instance"></a><span data-ttu-id="8ed00-133">Como usar um arquivo de configuração para instalar uma instância autônoma do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]</span><span class="sxs-lookup"><span data-stu-id="8ed00-133">How to use a configuration file to install a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance</span></span>  
  
-   <span data-ttu-id="8ed00-134">Execute a instalação por meio do prompt de comando e forneça o ConfigurationFile.ini usando o parâmetro *ConfigurationFile* .</span><span class="sxs-lookup"><span data-stu-id="8ed00-134">Run the installation through the command prompt and supply the ConfigurationFile.ini using the *ConfigurationFile* parameter.</span></span>  
  
#### <a name="how-to-use-a-configuration-file-to-prepare-and-complete-an-image-of-a-stand-alone-ssnoversion-instance-sysprep"></a><span data-ttu-id="8ed00-135">Como usar um arquivo de configuração para preparar e concluir uma imagem de uma instância autônoma do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] (SysPrep)</span><span class="sxs-lookup"><span data-stu-id="8ed00-135">How to use a configuration file to prepare and complete an image of a stand-alone [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] instance (SysPrep)</span></span>  
  
1.  <span data-ttu-id="8ed00-136">Para preparar uma ou mais instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e configurá-las na mesma máquina.</span><span class="sxs-lookup"><span data-stu-id="8ed00-136">To prepare one or more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and configure them on the same machine.</span></span>  
  
    -   <span data-ttu-id="8ed00-137">Execute **Preparação de imagem de uma instância autônoma do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** na página **Avançado** da Central de Instalação e capture o arquivo de configuração da preparação de imagem.</span><span class="sxs-lookup"><span data-stu-id="8ed00-137">Run **Image preparation of a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center and capture the prepare image configuration file.</span></span>  
  
    -   <span data-ttu-id="8ed00-138">Use o mesmo arquivo de configuração de preparação de imagem como um modelo para preparar mais instâncias do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8ed00-138">Use the same prepare image configuration file as a template to prepare more instances of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span>  
  
    -   <span data-ttu-id="8ed00-139">Execute **Conclusão de imagem de uma instância autônoma preparada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** na página **Avançado** da Central de Instalação para configurar instâncias preparadas no computador.</span><span class="sxs-lookup"><span data-stu-id="8ed00-139">Run **Image completion of a prepared stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center to configure a prepared instances on the machine.</span></span>  
  
2.  <span data-ttu-id="8ed00-140">Para preparar uma imagem do sistema operacional incluindo uma instância preparada não configurada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], usando a ferramenta SysPrep do Windows.</span><span class="sxs-lookup"><span data-stu-id="8ed00-140">To prepare an image of the operating system including an unconfigured prepared instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], using Windows SysPrep tool.</span></span>  
  
    -   <span data-ttu-id="8ed00-141">Execute a **Preparação de imagem de uma instância autônoma do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** na página Avançado da Central de Instalação e capture o arquivo de configuração da preparação de imagem.</span><span class="sxs-lookup"><span data-stu-id="8ed00-141">Run the **Image preparation of a stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the Advanced page of the Installation Center and capture the prepare image configuration file.</span></span>  
  
    -   <span data-ttu-id="8ed00-142">Execute a **Conclusão de imagem de uma instância autônoma preparada do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** na página **Avançado** da Central de Instalação, mas cancele-a na página **Pronto para Concluir** depois de capturar o arquivo de configuração completo.</span><span class="sxs-lookup"><span data-stu-id="8ed00-142">Run the **Image completion of a prepared stand-alone instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)]** from the **Advanced** page of the Installation Center, but cancel it on the **Ready to Complete** page after capturing the complete configuration file.</span></span>  
  
    -   <span data-ttu-id="8ed00-143">O arquivo de configuração de imagem completo pode ser armazenado com a imagem do Windows para automatizar a configuração das instâncias preparadas.</span><span class="sxs-lookup"><span data-stu-id="8ed00-143">The complete image configuration file can be stored with the Windows image for automating the configuration of the prepared instances.</span></span>  
  
#### <a name="how-to-install-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="8ed00-144">Como instalar um cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="8ed00-144">How to install a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
1.  <span data-ttu-id="8ed00-145">Opção de Instalação Integrada (criar um único cluster de failover de nó em um nó e, para nós adicionais, executar AddNode neles):</span><span class="sxs-lookup"><span data-stu-id="8ed00-145">Integrated Install option (create a single node failover cluster on a node and for additional nodes, run AddNode on them):</span></span>  
  
    -   <span data-ttu-id="8ed00-146">Execute a opção "Instalar um Cluster de Failover" e capture o arquivo de configuração que lista todas as configurações de instalação.</span><span class="sxs-lookup"><span data-stu-id="8ed00-146">Run the "Install a Failover Cluster" option and capture the configuration file that lists all the installation settings.</span></span>  
  
    -   <span data-ttu-id="8ed00-147">Execute a instalação de cluster de failover de linha de comando fornecendo o parâmetro *ConfigurationFile* .</span><span class="sxs-lookup"><span data-stu-id="8ed00-147">Run the command-line failover cluster install by supplying the *ConfigurationFile* parameter.</span></span>  
  
    -   <span data-ttu-id="8ed00-148">Em um nó adicional a ser adicionado, execute AddNode para capturar o arquivo ConfigurationFile.ini aplicável ao cluster de failover existente.</span><span class="sxs-lookup"><span data-stu-id="8ed00-148">On an additional node to be added, run AddNode to capture the ConfigurationFile.ini file applicable to the existing failover cluster.</span></span>  
  
    -   <span data-ttu-id="8ed00-149">Execute o AddNode de linha de comando em todos os nós adicionais que serão unidos ao cluster de failover fornecendo o mesmo arquivo de configuração usando o parâmetro ConfigurationFile.</span><span class="sxs-lookup"><span data-stu-id="8ed00-149">Run the command-line AddNode on all the additional nodes that will join the failover cluster, by supplying the same configuration file using the ConfigurationFile parameter.</span></span>  
  
2.  <span data-ttu-id="8ed00-150">Opção de Instalação avançada (preparar cluster de failover em todos os nós de cluster de failover e, após preparar todos os nós, execução completa no nó que possui o disco compartilhado):</span><span class="sxs-lookup"><span data-stu-id="8ed00-150">Advanced install option (prepare failover cluster on all failover cluster nodes, then, after preparing all the nodes, run complete on the node that owns the shared disk):</span></span>  
  
    -   <span data-ttu-id="8ed00-151">Execute **Preparar** em um dos nós e capture o arquivo ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="8ed00-151">Run **Prepare** on one of the nodes, and capture the ConfigurationFile.ini file.</span></span>  
  
    -   <span data-ttu-id="8ed00-152">Forneça o mesmo arquivo ConfigurationFile.ini para Instalação em todos os nós que serão preparados para o cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="8ed00-152">Supply the same ConfigurationFile.ini file to Setup on all the nodes that will be prepared for the failover cluster.</span></span>  
  
    -   <span data-ttu-id="8ed00-153">Após a preparação de todos os nós, execute uma operação de cluster de failover completa no nó que possui o disco compartilhado e capture o arquivo ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="8ed00-153">After all the nodes have been prepared, run a complete failover cluster operation on the node that owns the shared disk and capture the ConfigurationFile.ini file.</span></span>  
  
    -   <span data-ttu-id="8ed00-154">Em seguida, você pode fornecer esse arquivo ConfigurationFile.ini para concluir o cluster de failover.</span><span class="sxs-lookup"><span data-stu-id="8ed00-154">You can then supply this ConfigurationFile.ini file to complete the failover cluster.</span></span>  
  
#### <a name="how-to-add-or-remove-a-node-to-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="8ed00-155">Como adicionar ou remover um nó de um cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] usando o arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="8ed00-155">How to add or remove a node to a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
-   <span data-ttu-id="8ed00-156">Se você tiver um arquivo de configuração que foi usado anteriormente para adicionar um nó ou para remover um nó de um cluster de failover, poderá reutilizar esse mesmo arquivo para adicionar ou remover nós adicionais.</span><span class="sxs-lookup"><span data-stu-id="8ed00-156">If you have a configuration file that was previously used to add a node to or remove a node from a failover cluster, you can reuse that same file to add or remove additional nodes.</span></span>  
  
#### <a name="how-to-upgrade-a-ssnoversion-failover-cluster-using-the-configuration-file"></a><span data-ttu-id="8ed00-157">Como atualizar um cluster de failover do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] com o arquivo de configuração</span><span class="sxs-lookup"><span data-stu-id="8ed00-157">How to upgrade a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] failover cluster using the configuration file</span></span>  
  
1.  <span data-ttu-id="8ed00-158">Execute Atualizar no nó passivo e capture o arquivo ConfigurationFile.ini.</span><span class="sxs-lookup"><span data-stu-id="8ed00-158">Run upgrade on the passive node and capture the ConfigurationFile.ini file.</span></span> <span data-ttu-id="8ed00-159">Isso pode ser feito executando a atualização real ou saindo no final sem fazer a atualização real.</span><span class="sxs-lookup"><span data-stu-id="8ed00-159">You can do this either by performing the actual upgrade, or exiting at the end without doing the actual upgrade.</span></span>  
  
2.  <span data-ttu-id="8ed00-160">Em todos os nós adicionais a serem atualizados, forneça o arquivo ConfigurationFile.ini para concluir o processo.</span><span class="sxs-lookup"><span data-stu-id="8ed00-160">On all the additional nodes to be upgraded, supply the ConfigurationFile.ini file to complete the process.</span></span>  
  
## <a name="sample-syntax"></a><span data-ttu-id="8ed00-161">Sintaxe de exemplo</span><span class="sxs-lookup"><span data-stu-id="8ed00-161">Sample Syntax</span></span>  
 <span data-ttu-id="8ed00-162">Os exemplos a seguir mostram como usar o arquivo de configuração:</span><span class="sxs-lookup"><span data-stu-id="8ed00-162">Following are some examples on how to use the configuration file:</span></span>  
  
-   <span data-ttu-id="8ed00-163">Para especificar o arquivo de configuração no prompt de comando:</span><span class="sxs-lookup"><span data-stu-id="8ed00-163">To specify the configuration file at the command prompt:</span></span>  
  
```  
Setup.exe /ConfigurationFile=MyConfigurationFile.INI  
```  
  
-   <span data-ttu-id="8ed00-164">Para especificar senhas no prompt de comando em vez de no arquivo de configuração:</span><span class="sxs-lookup"><span data-stu-id="8ed00-164">To specify passwords at the command prompt instead of in the configuration file:</span></span>  
  
```  
Setup.exe /SQLSVCPASSWORD="************" /AGTSVCPASSWORD="************" /ASSVCPASSWORD="************" /ISSVCPASSWORD="************" /RSSVCPASSWORD="************" /ConfigurationFile=MyConfigurationFile.INI  
```  
  
## <a name="see-also"></a><span data-ttu-id="8ed00-165">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8ed00-165">See Also</span></span>  
 <span data-ttu-id="8ed00-166">[Instalar o SQL Server 2014 no prompt de comando](install-sql-server-from-the-command-prompt.md) </span><span class="sxs-lookup"><span data-stu-id="8ed00-166">[Install SQL Server 2014 from the Command Prompt](install-sql-server-from-the-command-prompt.md) </span></span>  
 <span data-ttu-id="8ed00-167">[Instalação do cluster de failover do SQL Server](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md) </span><span class="sxs-lookup"><span data-stu-id="8ed00-167">[SQL Server Failover Cluster Installation](../../sql-server/failover-clusters/install/sql-server-failover-cluster-installation.md) </span></span>  
 [<span data-ttu-id="8ed00-168">Atualizar um cluster de failover do SQL Server</span><span class="sxs-lookup"><span data-stu-id="8ed00-168">Upgrade a SQL Server Failover Cluster</span></span>](../../sql-server/failover-clusters/windows/upgrade-a-sql-server-failover-cluster-instance.md)  
  
  
