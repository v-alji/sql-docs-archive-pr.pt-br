---
title: Referência da interface do usuário do assistente de instalação do pacote | Microsoft Docs
ms.custom: ''
ms.date: 03/06/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.deploymentwizard.confirminstallation.f1
- sql12.dts.deploymentwizard.deploydtspackages.f1
- sql12.dts.deploymentwizard.selectinstfolder.f1
- sql12.dts.deploymentwizard.specifytargetsqlserver.f1
- sql12.dts.deploymentwizard.welcome.f1
- sql12.dts.deploymentwizard.finish.f1
- sql12.dts.deploymentwizard.configurepackages.f1
- sql12.dts.deploymentwizard.packagevalidation.f1
helpviewer_keywords:
- Package Installer Wizard
ms.assetid: 6fca44d9-5001-4644-bcf3-c2d10a674b97
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c15b423c66891e799f7f8dcd27682036dce6d8de
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87679416"
---
# <a name="package-installation-wizard-ui-reference"></a><span data-ttu-id="8f9f2-102">Referência da interface do usuário do Assistente de Instalação de Pacotes</span><span class="sxs-lookup"><span data-stu-id="8f9f2-102">Package Installation Wizard UI Reference</span></span>
  <span data-ttu-id="8f9f2-103">Use o **Assistente de Instalação de Pacotes** para implantar um projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] , inclusive os pacotes e arquivos diversos contidos nele, bem como todas as dependências do pacote.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-103">Use the **Package Installation Wizard** to deploy a [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, including the packages and miscellaneous files it contains and any package dependencies.</span></span>  
  
 <span data-ttu-id="8f9f2-104">Antes de implantar pacotes, você pode criar configurações e implantá-las com os pacotes.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-104">Before you deploy packages, you can create configurations and then deploy them with the packages.</span></span> [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] <span data-ttu-id="8f9f2-105">usa configurações para atualizar dinamicamente as propriedades de pacotes e objetos de pacote em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-105">uses configurations to dynamically update properties of packages and package objects at run time.</span></span> <span data-ttu-id="8f9f2-106">Por exemplo, a cadeia de conexão de uma conexão OLE DB pode ser definida dinamicamente em tempo de execução fornecendo-se uma configuração que mapeie um valor para uma propriedade que contenha a cadeia de conexão.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-106">For example, the connection string of an OLE DB connection can be set dynamically at run time by providing a configuration that maps a value to the property that contains the connection string.</span></span>  
  
 <span data-ttu-id="8f9f2-107">Você não pode executar o Assistente de Instalação de Pacotes enquanto não criar um projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e um utilitário de implantação.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-107">You cannot run the Package Installation Wizard until you build an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project and create a deployment utility.</span></span> <span data-ttu-id="8f9f2-108">Para obter mais informações, consulte [Implantar pacotes por meio do utilitário de implantação](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md).</span><span class="sxs-lookup"><span data-stu-id="8f9f2-108">For more information, see [Deploy Packages by Using the Deployment Utility](../../2014/integration-services/deploy-packages-by-using-the-deployment-utility.md).</span></span>  
  
 <span data-ttu-id="8f9f2-109">As seções a seguir descrevem as páginas do assistente.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-109">The following sections describe pages of the wizard.</span></span>  
  
## <a name="welcome-to-the-package-installation-wizard-page"></a><span data-ttu-id="8f9f2-110">Bem-vindo à página Assistente de Instalação de Pacotes</span><span class="sxs-lookup"><span data-stu-id="8f9f2-110">Welcome to the Package Installation Wizard Page</span></span>  
 <span data-ttu-id="8f9f2-111">Use o **Assistente de Instalação de Pacotes** para implantar um projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] para o qual você criou um utilitário de implantação de pacotes.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-111">Use the **Package Installation Wizard** to deploy an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project for which you built a package deployment utility.</span></span>  
  
 <span data-ttu-id="8f9f2-112">**Não mostrar esta página inicial novamente**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-112">**Do not show this starting page again**</span></span>  
 <span data-ttu-id="8f9f2-113">Selecione para ignorar a página inicial ao executar o assistente novamente.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-113">Select to skip the starting page when you run the wizard again.</span></span>  
  
 <span data-ttu-id="8f9f2-114">**Próximo**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-114">**Next**</span></span>  
 <span data-ttu-id="8f9f2-115">Vá para a próxima página do assistente.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-115">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="8f9f2-116">**Concluir**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-116">**Finish**</span></span>  
 <span data-ttu-id="8f9f2-117">Pule para a página Concluir o assistente de instalação de pacotes.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-117">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="8f9f2-118">Use esta opção caso você já tenha retornado às páginas anteriores do assistente para revisar suas opções e especificado todas as opções necessárias.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-118">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="configure-packages-page"></a><span data-ttu-id="8f9f2-119">Configurar a página Pacotes</span><span class="sxs-lookup"><span data-stu-id="8f9f2-119">Configure Packages Page</span></span>  
 <span data-ttu-id="8f9f2-120">Use a página **Configurar Pacotes** para editar as configurações do pacote.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-120">Use the **Configure Packages** page to edit package configurations.</span></span>  
  
### <a name="options"></a><span data-ttu-id="8f9f2-121">Opções</span><span class="sxs-lookup"><span data-stu-id="8f9f2-121">Options</span></span>  
 <span data-ttu-id="8f9f2-122">**Arquivo de configuração**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-122">**Configuration file**</span></span>  
 <span data-ttu-id="8f9f2-123">Edite o conteúdo de um arquivo de configuração selecionando o arquivo na lista.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-123">Edit the contents of a configuration file by selecting the file from the list.</span></span>  
  
 <span data-ttu-id="8f9f2-124">**Tópicos relacionados:** [Criar configurações de pacote](../../2014/integration-services/create-package-configurations.md)</span><span class="sxs-lookup"><span data-stu-id="8f9f2-124">**Related Topics:** [Create Package Configurations](../../2014/integration-services/create-package-configurations.md)</span></span>  
  
 <span data-ttu-id="8f9f2-125">**Caminho**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-125">**Path**</span></span>  
 <span data-ttu-id="8f9f2-126">Exiba o caminho da propriedade a ser configurada.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-126">View the path of the property to be configured.</span></span>  
  
 <span data-ttu-id="8f9f2-127">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-127">**Type**</span></span>  
 <span data-ttu-id="8f9f2-128">Exiba o tipo de dados da propriedade.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-128">View the data type of the property.</span></span>  
  
 <span data-ttu-id="8f9f2-129">**Valor**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-129">**Value**</span></span>  
 <span data-ttu-id="8f9f2-130">Especifique o valor da configuração.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-130">Specify the value of the configuration.</span></span>  
  
 <span data-ttu-id="8f9f2-131">**Próximo**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-131">**Next**</span></span>  
 <span data-ttu-id="8f9f2-132">Vá para a próxima página do assistente.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-132">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="8f9f2-133">**Concluir**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-133">**Finish**</span></span>  
 <span data-ttu-id="8f9f2-134">Pule para a página Concluir o assistente de instalação de pacotes.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-134">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="8f9f2-135">Use esta opção caso você já tenha retornado às páginas anteriores do assistente para revisar suas opções e especificado todas as opções necessárias.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-135">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="confirm-installation-page"></a><span data-ttu-id="8f9f2-136">Página Confirmar Instalação</span><span class="sxs-lookup"><span data-stu-id="8f9f2-136">Confirm Installation Page</span></span>  
 <span data-ttu-id="8f9f2-137">Use a página **Confirmar Instalação** para iniciar a instalação de pacotes, para exibir o status e para exibir as informações que serão usadas pelo assistente para instalar os arquivos a partir do projeto especificado.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-137">Use the **Confirm Installation** page to start the installation of packages, to view the status, and to view the information that the wizard will use to install files from the specified project.</span></span>  
  
 <span data-ttu-id="8f9f2-138">**Próximo**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-138">**Next**</span></span>  
 <span data-ttu-id="8f9f2-139">Instale os pacotes e suas dependências e vá para a próxima página do assistente quando instalação for concluída.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-139">Install the packages and their dependencies and go to the next wizard page when installation is completed.</span></span>  
  
 <span data-ttu-id="8f9f2-140">**Status**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-140">**Status**</span></span>  
 <span data-ttu-id="8f9f2-141">Mostra o progresso da instalação do pacote.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-141">Shows the progress of the package installation.</span></span>  
  
 <span data-ttu-id="8f9f2-142">**Concluir**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-142">**Finish**</span></span>  
 <span data-ttu-id="8f9f2-143">Vá para a página Concluir o assistente de instalação de pacotes.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-143">Go to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="8f9f2-144">Use esta opção caso você já tenha retornado às páginas anteriores do assistente para revisar suas opções e especificado todas as opções necessárias.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-144">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all the required options.</span></span>  
  
## <a name="deploy-ssis-packages-page"></a><span data-ttu-id="8f9f2-145">Página Implantar Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="8f9f2-145">Deploy SSIS Packages Page</span></span>  
 <span data-ttu-id="8f9f2-146">Use a página **Implantar Pacotes do SSIS** para especificar onde os pacotes do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e suas dependências serão instalados.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-146">Use the **Deploy SSIS Packages** page to specify where to install [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] packages and their dependencies.</span></span>  
  
### <a name="options"></a><span data-ttu-id="8f9f2-147">Opções</span><span class="sxs-lookup"><span data-stu-id="8f9f2-147">Options</span></span>  
 <span data-ttu-id="8f9f2-148">**Implantação do sistema de arquivos**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-148">**File system deployment**</span></span>  
 <span data-ttu-id="8f9f2-149">Distribua os pacotes e suas dependências em uma pasta especificada no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-149">Deploy packages and dependencies in a specified folder in the file system.</span></span>  
  
 <span data-ttu-id="8f9f2-150">**Implantação no SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-150">**SQL Server deployment**</span></span>  
 <span data-ttu-id="8f9f2-151">Implante os pacotes e suas dependências em uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f9f2-151">Deploy packages and dependencies in an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="8f9f2-152">Use esta opção caso o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] compartilhe pacotes entre servidores.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-152">Use this option if [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] shares packages between servers.</span></span> <span data-ttu-id="8f9f2-153">Todas as dependências do pacote são instaladas na pasta especificada no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-153">Any package dependencies are installed in the specified folder in the file system.</span></span>  
  
 <span data-ttu-id="8f9f2-154">**Validar pacotes após a instalação**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-154">**Validate packages after installation**</span></span>  
 <span data-ttu-id="8f9f2-155">Indique se é preciso validar os pacotes após a instalação.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-155">Indicate whether to validate packages after installation.</span></span>  
  
 <span data-ttu-id="8f9f2-156">**Próximo**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-156">**Next**</span></span>  
 <span data-ttu-id="8f9f2-157">Vá para a próxima página do assistente.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-157">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="8f9f2-158">**Concluir**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-158">**Finish**</span></span>  
 <span data-ttu-id="8f9f2-159">Pule para a página Concluir o assistente de instalação de pacotes.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-159">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="8f9f2-160">Use esta opção caso você já tenha retornado às páginas anteriores do assistente para revisar suas opções e especificado todas as opções necessárias.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-160">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="packages-validation-page"></a><span data-ttu-id="8f9f2-161">Página Validação de Pacotes</span><span class="sxs-lookup"><span data-stu-id="8f9f2-161">Packages Validation Page</span></span>  
 <span data-ttu-id="8f9f2-162">Use a página **Validação de Pacotes** para exibir o progresso e os resultados da validação do pacote.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-162">Use the **Packages Validation** page to view the progress and results of the package validation.</span></span>  
  
 <span data-ttu-id="8f9f2-163">**Próximo**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-163">**Next**</span></span>  
 <span data-ttu-id="8f9f2-164">Vá para a próxima página do assistente.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-164">Go to the next page in the wizard.</span></span>  
  
## <a name="select-installation-folder-page"></a><span data-ttu-id="8f9f2-165">Página Selecionar Pasta de Instalação</span><span class="sxs-lookup"><span data-stu-id="8f9f2-165">Select Installation Folder Page</span></span>  
 <span data-ttu-id="8f9f2-166">Use a página **Selecionar Pasta de Instalação** para especificar a pasta do arquivo de sistemas na qual os pacotes e as dependências de pacotes serão instalados.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-166">Use the **Select Installation Folder** page to specify the file system folder in which to install the packages and their dependencies.</span></span>  
  
### <a name="options"></a><span data-ttu-id="8f9f2-167">Opções</span><span class="sxs-lookup"><span data-stu-id="8f9f2-167">Options</span></span>  
 <span data-ttu-id="8f9f2-168">**Pasta**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-168">**Folder**</span></span>  
 <span data-ttu-id="8f9f2-169">Especifique o caminho e a pasta nos quais o pacote e suas dependências serão copiados.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-169">Specify the path and folder in which to copy the package and its dependencies.</span></span>  
  
 <span data-ttu-id="8f9f2-170">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-170">**Browse**</span></span>  
 <span data-ttu-id="8f9f2-171">Procure a pasta de destino usando a caixa de diálogo **Procurar Pasta** .</span><span class="sxs-lookup"><span data-stu-id="8f9f2-171">Browse to the target folder by using the **Browse For Folder** dialog box.</span></span>  
  
 <span data-ttu-id="8f9f2-172">**Próximo**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-172">**Next**</span></span>  
 <span data-ttu-id="8f9f2-173">Vá para a próxima página do assistente.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-173">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="8f9f2-174">**Concluir**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-174">**Finish**</span></span>  
 <span data-ttu-id="8f9f2-175">Pule para a página Concluir o assistente de instalação de pacotes.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-175">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="8f9f2-176">Use esta opção caso você já tenha retornado às páginas anteriores do assistente para revisar suas opções e especificado todas as opções necessárias.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-176">Use this option if you have backtracked through the wizard pages to revise your choices and if have specified all of the required options.</span></span>  
  
## <a name="specify-target-sql-server-page"></a><span data-ttu-id="8f9f2-177">Página Especificar SQL Server de Destino</span><span class="sxs-lookup"><span data-stu-id="8f9f2-177">Specify Target SQL Server Page</span></span>  
 <span data-ttu-id="8f9f2-178">Use a página **Especificar SQL Server de Destino** para especificar as opções para implantar o pacote a uma instância do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="8f9f2-178">Use the **Specify Target SQL Server** page to specify options for deploying the package to an instance of [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
### <a name="options"></a><span data-ttu-id="8f9f2-179">Opções</span><span class="sxs-lookup"><span data-stu-id="8f9f2-179">Options</span></span>  
 <span data-ttu-id="8f9f2-180">**Nome do servidor**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-180">**Server name**</span></span>  
 <span data-ttu-id="8f9f2-181">Especifique o nome do servidor para o qual deseja implantar os pacotes.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-181">Specify the name of the server to deploy the packages to.</span></span>  
  
 <span data-ttu-id="8f9f2-182">**Usar Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-182">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="8f9f2-183">Especifique se será usada a Autenticação do Windows para efetuar login no servidor.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-183">Specify whether to use Windows Authentication to log on to the server.</span></span> <span data-ttu-id="8f9f2-184">A Autenticação do Windows é recomendada para obter melhor segurança.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-184">Windows Authentication is recommended for better security.</span></span>  
  
 <span data-ttu-id="8f9f2-185">**Usar Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-185">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="8f9f2-186">Especifique se o pacote deve usar a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] para fazer login no servidor.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-186">Specify whether the package should use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication to log on to the server.</span></span> <span data-ttu-id="8f9f2-187">Se você usar a Autenticação do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] , será preciso fornecer um nome de usuário e uma senha.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-187">If you use [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] Authentication, you must provide a user name and password.</span></span>  
  
 <span data-ttu-id="8f9f2-188">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-188">**User name**</span></span>  
 <span data-ttu-id="8f9f2-189">Especifique um nome de usuário.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-189">Specify a user name.</span></span>  
  
 <span data-ttu-id="8f9f2-190">**Senha**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-190">**Password**</span></span>  
 <span data-ttu-id="8f9f2-191">Especifique uma senha.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-191">Specify a password.</span></span>  
  
 <span data-ttu-id="8f9f2-192">**Caminho do pacote**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-192">**Package path**</span></span>  
 <span data-ttu-id="8f9f2-193">Especifique o nome da pasta lógica ou digite "/" para a pasta padrão.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-193">Specify the name of the logical folder, or enter "/" for the default folder.</span></span>  
  
 <span data-ttu-id="8f9f2-194">Para selecionar a pasta na caixa de diálogo **Pacote do SSIS** , clique em procurar (...). Entretanto, a caixa de diálogo não fornece uma maneira para selecionar a pasta padrão.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-194">To select the folder in the **SSIS Package** dialog box, click browse (...). However, the dialog box does not provide a means to select the default folder.</span></span> <span data-ttu-id="8f9f2-195">Se desejar usar a pasta padrão, digite "/" na caixa de texto.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-195">If you want to use the default folder, you have to enter "/" in the text box.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="8f9f2-196">Se você não inserir um caminho de pacote válido, a seguinte mensagem de erro será exibida: "Um ou mais argumentos são inválidos."</span><span class="sxs-lookup"><span data-stu-id="8f9f2-196">If you do not enter a valid package path, the following error message appears: "One or more arguments are invalid."</span></span>  
  
 <span data-ttu-id="8f9f2-197">**Depender do armazenamento do servidor para criptografia**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-197">**Rely on server storage for encryption**</span></span>  
 <span data-ttu-id="8f9f2-198">Selecione esta opção para usar os recursos do [!INCLUDE[ssDE](../includes/ssde-md.md)] para ajudar a manter a segurança dos pacotes.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-198">Select to use security features of the [!INCLUDE[ssDE](../includes/ssde-md.md)] to help secure the packages.</span></span>  
  
 <span data-ttu-id="8f9f2-199">**Próximo**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-199">**Next**</span></span>  
 <span data-ttu-id="8f9f2-200">Vá para a próxima página do assistente.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-200">Go to the next page in the wizard.</span></span>  
  
 <span data-ttu-id="8f9f2-201">**Concluir**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-201">**Finish**</span></span>  
 <span data-ttu-id="8f9f2-202">Pule para a página Concluir o assistente de instalação de pacotes.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-202">Skip to the Finish the Package Installation Wizard page.</span></span> <span data-ttu-id="8f9f2-203">Use esta opção caso você já tenha retornado às páginas anteriores do assistente para revisar suas opções e especificado todas as opções necessárias.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-203">Use this option if you have backtracked through the wizard pages to revise your choices and have specified all of the required options.</span></span>  
  
## <a name="finish-the-package-installation-page"></a><span data-ttu-id="8f9f2-204">Página Concluir o Assistente de Instalação de Pacotes</span><span class="sxs-lookup"><span data-stu-id="8f9f2-204">Finish the Package Installation Page</span></span>  
 <span data-ttu-id="8f9f2-205">Use a página **Concluir o Assistente de Instalação de Pacotes** para exibir um resumo dos resultados da instalação do pacote.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-205">Use the **Finish the Package Installation Wizard** page to view a summary of the package installation results.</span></span> <span data-ttu-id="8f9f2-206">Esta página fornece detalhes como o nome do projeto do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] que foi implantado, os pacotes que foram instalados, os arquivos de configuração e o local da instalação.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-206">This page provides details such as the name of the deployed [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] project, the packages that were installed, the configuration files, and the installation location.</span></span>  
  
 <span data-ttu-id="8f9f2-207">**Concluir**</span><span class="sxs-lookup"><span data-stu-id="8f9f2-207">**Finish**</span></span>  
 <span data-ttu-id="8f9f2-208">Para sair do assistente, clique em **Concluir**.</span><span class="sxs-lookup"><span data-stu-id="8f9f2-208">Exit the wizard by clicking **Finish**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="8f9f2-209">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="8f9f2-209">See Also</span></span>  
 [<span data-ttu-id="8f9f2-210">Implantação de pacote &#40;SSIS&#41;</span><span class="sxs-lookup"><span data-stu-id="8f9f2-210">Package Deployment &#40;SSIS&#41;</span></span>](packages/legacy-package-deployment-ssis.md)  
  
  
