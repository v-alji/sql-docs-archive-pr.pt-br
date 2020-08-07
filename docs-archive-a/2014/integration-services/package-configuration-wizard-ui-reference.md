---
title: Referência da interface do usuário do assistente de configuração de pacote | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.configwizard.selectobjects.f1
- sql12.dts.configwizard.selecconfigtype.f1
- sql12.dts.configwizard.finishdtsconfiguration.f1
- sql12.dts.configwizard.welcome.f1
ms.assetid: adca6938-6d5a-40ec-950e-dceb79d044fe
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 222c5f58ca4e942dd23909b433ab346c500fceed
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87582531"
---
# <a name="package-configuration-wizard-ui-reference"></a><span data-ttu-id="eb31c-102">Referência da interface do usuário do Assistente de Configuração de Pacotes</span><span class="sxs-lookup"><span data-stu-id="eb31c-102">Package Configuration Wizard UI Reference</span></span>
  <span data-ttu-id="eb31c-103">Use o **Assistente de Configuração de Pacotes** para criar configurações que atualizem as propriedades de um pacote do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] e seus respectivos objetos em tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="eb31c-103">Use the **Package Configuration Wizard** to create configurations that update the properties of an [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] package and its objects at run time.</span></span> <span data-ttu-id="eb31c-104">Esse assistente é executado quando você adiciona uma nova configuração ou modifica uma existente na caixa de diálogo **Organizador de Configurações do Pacote** .</span><span class="sxs-lookup"><span data-stu-id="eb31c-104">This wizard runs when you add a new configuration or modify an existing one in the **Package Configurations Organizer** dialog box.</span></span> <span data-ttu-id="eb31c-105">Para abrir a caixa de diálogo **Organizador de Configurações do Pacote** , selecione **Configurações de Pacote** no menu **SSIS** no [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb31c-105">To open the **Package Configurations Organizer** dialog box, select **Package Configurations** on the **SSIS** menu in [!INCLUDE[ssBIDevStudioFull](../includes/ssbidevstudiofull-md.md)].</span></span> <span data-ttu-id="eb31c-106">Para obter mais informações, consulte [Criar configurações de pacote](../../2014/integration-services/create-package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="eb31c-106">For more information, see [Create Package Configurations](../../2014/integration-services/create-package-configurations.md).</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="eb31c-107">As configurações estão disponíveis para o modelo de implantação de pacote.</span><span class="sxs-lookup"><span data-stu-id="eb31c-107">Configurations are available for the package deployment model.</span></span> <span data-ttu-id="eb31c-108">Os parâmetros são usados no lugar das configurações para o modelo de implantação de projeto.</span><span class="sxs-lookup"><span data-stu-id="eb31c-108">Parameters are used in place of configurations for the project deployment model.</span></span> <span data-ttu-id="eb31c-109">O modelo de implantação de projeto permite que você implante projetos do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] no servidor do [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="eb31c-109">The project deployment model enables you to deploy [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] projects to the [!INCLUDE[ssISnoversion](../includes/ssisnoversion-md.md)] server.</span></span> <span data-ttu-id="eb31c-110">Para obter mais informações sobre os modelos de implantação, consulte [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span><span class="sxs-lookup"><span data-stu-id="eb31c-110">For more information about the deployment models, see [Deployment of Projects and Packages](packages/deploy-integration-services-ssis-projects-and-packages.md).</span></span>  
  
 <span data-ttu-id="eb31c-111">As seções a seguir descrevem as páginas do Assistente.</span><span class="sxs-lookup"><span data-stu-id="eb31c-111">The following sections describe pages of the Wizard.</span></span>  
  
## <a name="welcome-to-the-package-configuration-wizard-page"></a><span data-ttu-id="eb31c-112">Bem-vindo à página Assistente de Configuração de Pacotes</span><span class="sxs-lookup"><span data-stu-id="eb31c-112">Welcome to the Package Configuration Wizard Page</span></span>  
 <span data-ttu-id="eb31c-113">Use o **Assistente de Configuração do SSIS** para criar configurações que atualizem as propriedades de um pacote e seus respectivos objetos no tempo de execução.</span><span class="sxs-lookup"><span data-stu-id="eb31c-113">Use the **SSIS Configuration Wizard** to create configurations that update the properties of a package and its objects at run time.</span></span>  
  
### <a name="options"></a><span data-ttu-id="eb31c-114">Opções</span><span class="sxs-lookup"><span data-stu-id="eb31c-114">Options</span></span>  
 <span data-ttu-id="eb31c-115">**Não mostrar esta página novamente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-115">**Don't show this page again**</span></span>  
 <span data-ttu-id="eb31c-116">Ignore a página inicial da próxima vez que abrir o assistente.</span><span class="sxs-lookup"><span data-stu-id="eb31c-116">Skip the welcome page the next time you open the wizard.</span></span>  
  
 <span data-ttu-id="eb31c-117">**Próximo**</span><span class="sxs-lookup"><span data-stu-id="eb31c-117">**Next**</span></span>  
 <span data-ttu-id="eb31c-118">Vá para a próxima página do assistente.</span><span class="sxs-lookup"><span data-stu-id="eb31c-118">Go the next page in the wizard.</span></span>  
  
## <a name="select-configuration-type-page"></a><span data-ttu-id="eb31c-119">Selecionar a página Tipo de configuração</span><span class="sxs-lookup"><span data-stu-id="eb31c-119">Select Configuration Type Page</span></span>  
 <span data-ttu-id="eb31c-120">Use a página **Selecionar Tipo de Configuração** para especificar o tipo de configuração que deseja criar.</span><span class="sxs-lookup"><span data-stu-id="eb31c-120">Use the **Select Configuration Type** page to specify the type of configuration to create.</span></span>  
  
 <span data-ttu-id="eb31c-121">Se precisar de mais informações para determinar qual tipo de configuração usar, consulte [Configurações de Pacote](../../2014/integration-services/package-configurations.md).</span><span class="sxs-lookup"><span data-stu-id="eb31c-121">If you need additional information to determine which type of configuration to use, see [Package Configurations](../../2014/integration-services/package-configurations.md).</span></span>  
  
### <a name="static-options"></a><span data-ttu-id="eb31c-122">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="eb31c-122">Static Options</span></span>  
 <span data-ttu-id="eb31c-123">**Tipo de configuração**</span><span class="sxs-lookup"><span data-stu-id="eb31c-123">**Configuration type**</span></span>  
 <span data-ttu-id="eb31c-124">Selecione o tipo de fonte na qual deseja armazenar a configuração usando as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="eb31c-124">Select the type of source in which to store the configuration, using the following options:</span></span>  
  
|<span data-ttu-id="eb31c-125">Valor</span><span class="sxs-lookup"><span data-stu-id="eb31c-125">Value</span></span>|<span data-ttu-id="eb31c-126">Descrição</span><span class="sxs-lookup"><span data-stu-id="eb31c-126">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eb31c-127">**Arquivo de configuração XML**</span><span class="sxs-lookup"><span data-stu-id="eb31c-127">**XML configuration file**</span></span>|<span data-ttu-id="eb31c-128">Armazene a configuração como um arquivo XML.</span><span class="sxs-lookup"><span data-stu-id="eb31c-128">Store the configuration as an XML file.</span></span> <span data-ttu-id="eb31c-129">Se este valor for selecionado, as opções dinâmicas serão exibidas na seção **Tipo de Configuração**.</span><span class="sxs-lookup"><span data-stu-id="eb31c-129">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="eb31c-130">**Variável de ambiente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-130">**Environment variable**</span></span>|<span data-ttu-id="eb31c-131">Armazene a configuração em uma das variáveis de ambiente.</span><span class="sxs-lookup"><span data-stu-id="eb31c-131">Store the configuration in one of the environment variables.</span></span> <span data-ttu-id="eb31c-132">Se este valor for selecionado, as opções dinâmicas serão exibidas na seção **Tipo de Configuração**.</span><span class="sxs-lookup"><span data-stu-id="eb31c-132">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="eb31c-133">**Entrada de Registro**</span><span class="sxs-lookup"><span data-stu-id="eb31c-133">**Registry entry**</span></span>|<span data-ttu-id="eb31c-134">Armazene a configuração no Registro.</span><span class="sxs-lookup"><span data-stu-id="eb31c-134">Store the configuration in the Registry.</span></span> <span data-ttu-id="eb31c-135">Se este valor for selecionado, as opções dinâmicas serão exibidas na seção **Tipo de Configuração**.</span><span class="sxs-lookup"><span data-stu-id="eb31c-135">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="eb31c-136">**Variável de pacote pai**</span><span class="sxs-lookup"><span data-stu-id="eb31c-136">**Parent package variable**</span></span>|<span data-ttu-id="eb31c-137">Armazene a configuração como uma variável no pacote que contém a tarefa.</span><span class="sxs-lookup"><span data-stu-id="eb31c-137">Store the configuration as a variable in the package that contains the task.</span></span>  <span data-ttu-id="eb31c-138">Se este valor for selecionado, as opções dinâmicas serão exibidas na seção **Tipo de Configuração**.</span><span class="sxs-lookup"><span data-stu-id="eb31c-138">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
|<span data-ttu-id="eb31c-139">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="eb31c-139">**SQL Server**</span></span>|<span data-ttu-id="eb31c-140">Armazene a configuração em uma tabela no [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="eb31c-140">Store the configuration in a table in [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="eb31c-141">Se este valor for selecionado, as opções dinâmicas serão exibidas na seção **Tipo de Configuração**.</span><span class="sxs-lookup"><span data-stu-id="eb31c-141">Selecting this value displays the dynamic options in the section, **Configuration Type**.</span></span>|  
  
 <span data-ttu-id="eb31c-142">**Próximo**</span><span class="sxs-lookup"><span data-stu-id="eb31c-142">**Next**</span></span>  
 <span data-ttu-id="eb31c-143">Visualize a próxima página da sequência do assistente.</span><span class="sxs-lookup"><span data-stu-id="eb31c-143">View the next page in the wizard sequence.</span></span>  
  
### <a name="dynamic-options"></a><span data-ttu-id="eb31c-144">Opções dinâmicas</span><span class="sxs-lookup"><span data-stu-id="eb31c-144">Dynamic Options</span></span>  
  
#### <a name="configuration-type-option--xml-configuration-file"></a><span data-ttu-id="eb31c-145">Opção Tipo de Configuração = Arquivo de Configuração XML</span><span class="sxs-lookup"><span data-stu-id="eb31c-145">Configuration Type Option = XML Configuration File</span></span>  
 <span data-ttu-id="eb31c-146">**Especificar as definições de configuração diretamente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-146">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="eb31c-147">Use para especificar as configurações diretamente.</span><span class="sxs-lookup"><span data-stu-id="eb31c-147">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="eb31c-148">Valor</span><span class="sxs-lookup"><span data-stu-id="eb31c-148">Value</span></span>|<span data-ttu-id="eb31c-149">Descrição</span><span class="sxs-lookup"><span data-stu-id="eb31c-149">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eb31c-150">**Nome do arquivo de configuração**</span><span class="sxs-lookup"><span data-stu-id="eb31c-150">**Configuration file name**</span></span>|<span data-ttu-id="eb31c-151">Digite o caminho do arquivo de configuração gerado pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="eb31c-151">Type the path of the configuration file that the wizard generates.</span></span>|  
|<span data-ttu-id="eb31c-152">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="eb31c-152">**Browse**</span></span>|<span data-ttu-id="eb31c-153">Use a caixa de diálogo **Selecionar Local do Arquivo de Configuração** para especificar o caminho do arquivo de configuração gerado pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="eb31c-153">Use the **Select Configuration File Location** dialog box to specify the path of the configuration file that the wizard generates.</span></span> <span data-ttu-id="eb31c-154">Se o arquivo não existir, ele será criado pelo assistente.</span><span class="sxs-lookup"><span data-stu-id="eb31c-154">If the file does not exist, it is created by the wizard.</span></span>|  
  
 <span data-ttu-id="eb31c-155">**O local de configuração é armazenado em uma variável de ambiente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-155">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="eb31c-156">Use para especificar a variável de ambiente na qual você deseja armazenar a configuração.</span><span class="sxs-lookup"><span data-stu-id="eb31c-156">Use to specify the environment variable in which to store the configuration.</span></span>  
  
|<span data-ttu-id="eb31c-157">Valor</span><span class="sxs-lookup"><span data-stu-id="eb31c-157">Value</span></span>|<span data-ttu-id="eb31c-158">Descrição</span><span class="sxs-lookup"><span data-stu-id="eb31c-158">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eb31c-159">**Variável de ambiente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-159">**Environment variable**</span></span>|<span data-ttu-id="eb31c-160">Selecione uma variável de ambiente da lista.</span><span class="sxs-lookup"><span data-stu-id="eb31c-160">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-option--environment-variable"></a><span data-ttu-id="eb31c-161">Opção Tipo de Configuração = Variável de Ambiente</span><span class="sxs-lookup"><span data-stu-id="eb31c-161">Configuration Type Option = Environment Variable</span></span>  
 <span data-ttu-id="eb31c-162">**Variável de ambiente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-162">**Environment variable**</span></span>  
 <span data-ttu-id="eb31c-163">Selecione a variável de ambiente que contém as informações de configuração.</span><span class="sxs-lookup"><span data-stu-id="eb31c-163">Select the environment variable that contains the configuration information.</span></span>  
  
#### <a name="configuration-type-option--registry-entry"></a><span data-ttu-id="eb31c-164">Opção Tipo de Configuração = Entrada de Registro</span><span class="sxs-lookup"><span data-stu-id="eb31c-164">Configuration Type Option = Registry Entry</span></span>  
 <span data-ttu-id="eb31c-165">**Especificar as definições de configuração diretamente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-165">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="eb31c-166">Use para especificar as configurações diretamente.</span><span class="sxs-lookup"><span data-stu-id="eb31c-166">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="eb31c-167">Valor</span><span class="sxs-lookup"><span data-stu-id="eb31c-167">Value</span></span>|<span data-ttu-id="eb31c-168">Descrição</span><span class="sxs-lookup"><span data-stu-id="eb31c-168">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eb31c-169">**Entrada de Registro**</span><span class="sxs-lookup"><span data-stu-id="eb31c-169">**Registry entry**</span></span>|<span data-ttu-id="eb31c-170">Digite a chave do Registro que contém as informações de configuração.</span><span class="sxs-lookup"><span data-stu-id="eb31c-170">Type the Registry key that contains the configuration information.</span></span> <span data-ttu-id="eb31c-171">O formato é \<registry key>.</span><span class="sxs-lookup"><span data-stu-id="eb31c-171">The format is \<registry key>.</span></span><br /><br /> <span data-ttu-id="eb31c-172">A chave do Registro já deve existir em HKEY_CURRENT_USER e deve ter um valor chamado Value (valor).</span><span class="sxs-lookup"><span data-stu-id="eb31c-172">The Registry key must already exist in HKEY_CURRENT_USER and have a value named Value.</span></span> <span data-ttu-id="eb31c-173">O valor pode ser um DWORD ou uma cadeia de caracteres.</span><span class="sxs-lookup"><span data-stu-id="eb31c-173">The value can be a DWORD or a string.</span></span><br /><br /> <span data-ttu-id="eb31c-174">Se desejar usar uma chave do Registro que não está na raiz de HKEY_CURRENT_USER, use o formato \<Registry key\registry key\\...> para identificar a chave.</span><span class="sxs-lookup"><span data-stu-id="eb31c-174">If you want to use a Registry key is not at the root of HKEY_CURRENT_USER, use the format \<Registry key\registry key\\...> to identify the key.</span></span>|  
  
 <span data-ttu-id="eb31c-175">**O local de configuração é armazenado em uma variável de ambiente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-175">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="eb31c-176">Use para especificar a variável de ambiente na qual deseja armazenar a configuração.</span><span class="sxs-lookup"><span data-stu-id="eb31c-176">Use to specify the environment variable to store the configuration in.</span></span>  
  
|<span data-ttu-id="eb31c-177">Valor</span><span class="sxs-lookup"><span data-stu-id="eb31c-177">Value</span></span>|<span data-ttu-id="eb31c-178">Descrição</span><span class="sxs-lookup"><span data-stu-id="eb31c-178">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eb31c-179">**Variável de ambiente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-179">**Environment variable**</span></span>|<span data-ttu-id="eb31c-180">Selecione uma variável de ambiente da lista.</span><span class="sxs-lookup"><span data-stu-id="eb31c-180">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-option--parent-package-variable"></a><span data-ttu-id="eb31c-181">Opção Tipo de Configuração = Variável de pacote pai</span><span class="sxs-lookup"><span data-stu-id="eb31c-181">Configuration Type Option = Parent Package Variable</span></span>  
 <span data-ttu-id="eb31c-182">**Especificar as definições de configuração diretamente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-182">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="eb31c-183">Use para especificar as configurações diretamente.</span><span class="sxs-lookup"><span data-stu-id="eb31c-183">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="eb31c-184">Valor</span><span class="sxs-lookup"><span data-stu-id="eb31c-184">Value</span></span>|<span data-ttu-id="eb31c-185">Descrição</span><span class="sxs-lookup"><span data-stu-id="eb31c-185">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eb31c-186">**Variável pai**</span><span class="sxs-lookup"><span data-stu-id="eb31c-186">**Parent variable**</span></span>|<span data-ttu-id="eb31c-187">Especifique a variável no pacote pai que contém as informações de configuração.</span><span class="sxs-lookup"><span data-stu-id="eb31c-187">Specify the variable in the parent package that contains the configuration information.</span></span>|  
  
 <span data-ttu-id="eb31c-188">**O local de configuração é armazenado em uma variável de ambiente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-188">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="eb31c-189">Use para especificar a variável de ambiente que armazena a configuração.</span><span class="sxs-lookup"><span data-stu-id="eb31c-189">Use to specify the environment variable that stores the configuration.</span></span>  
  
|<span data-ttu-id="eb31c-190">Valor</span><span class="sxs-lookup"><span data-stu-id="eb31c-190">Value</span></span>|<span data-ttu-id="eb31c-191">Descrição</span><span class="sxs-lookup"><span data-stu-id="eb31c-191">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eb31c-192">**Variável de ambiente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-192">**Environment variable**</span></span>|<span data-ttu-id="eb31c-193">Selecione uma variável de ambiente da lista.</span><span class="sxs-lookup"><span data-stu-id="eb31c-193">Select an environment variable from the list.</span></span>|  
  
#### <a name="configuration-type-options--sql-server"></a><span data-ttu-id="eb31c-194">Opções de Tipo de Configuração = SQL Server</span><span class="sxs-lookup"><span data-stu-id="eb31c-194">Configuration Type Options = SQL Server</span></span>  
 <span data-ttu-id="eb31c-195">**Especificar as definições de configuração diretamente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-195">**Specify configuration settings directly**</span></span>  
 <span data-ttu-id="eb31c-196">Use para especificar as configurações diretamente.</span><span class="sxs-lookup"><span data-stu-id="eb31c-196">Use to specify settings directly.</span></span>  
  
|<span data-ttu-id="eb31c-197">Valor</span><span class="sxs-lookup"><span data-stu-id="eb31c-197">Value</span></span>|<span data-ttu-id="eb31c-198">Descrição</span><span class="sxs-lookup"><span data-stu-id="eb31c-198">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eb31c-199">**Conexão**</span><span class="sxs-lookup"><span data-stu-id="eb31c-199">**Connection**</span></span>|<span data-ttu-id="eb31c-200">Selecione uma conexão da lista ou clique em **Nova** para criar uma nova conexão.</span><span class="sxs-lookup"><span data-stu-id="eb31c-200">Select a connection from the list, or click **New** to create a new connection.</span></span>|  
|<span data-ttu-id="eb31c-201">**Tabela de configuração**</span><span class="sxs-lookup"><span data-stu-id="eb31c-201">**Configuration table**</span></span>|<span data-ttu-id="eb31c-202">Selecione uma tabela existente ou clique em **Nova** para gravar uma instrução SQL que cria uma nova tabela.</span><span class="sxs-lookup"><span data-stu-id="eb31c-202">Select an existing table, or click **New** to write a SQL statement that creates a new table.</span></span>|  
|<span data-ttu-id="eb31c-203">**Filtro de configuração**</span><span class="sxs-lookup"><span data-stu-id="eb31c-203">**Configuration filter**</span></span>|<span data-ttu-id="eb31c-204">Selecione um nome de configuração existente ou digite um novo nome.</span><span class="sxs-lookup"><span data-stu-id="eb31c-204">Select an existing configuration name or type a new name.</span></span><br /><br /> <span data-ttu-id="eb31c-205">Podem ser armazenadas muitas configurações do SQL Server na mesma tabela e cada configuração pode incluir vários itens de configuração.</span><span class="sxs-lookup"><span data-stu-id="eb31c-205">Many SQL Server configurations can be stored in the same table, and each configuration can include multiple configuration items.</span></span><br /><br /> <span data-ttu-id="eb31c-206">O valor definido pelo usuário é armazenado na tabela para identificar os itens de configuração que pertencem a uma determinada configuração.</span><span class="sxs-lookup"><span data-stu-id="eb31c-206">This user-defined value is stored in the table to identify configuration items that belong to a particular configuration</span></span>|  
  
 <span data-ttu-id="eb31c-207">**O local de configuração é armazenado em uma variável de ambiente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-207">**Configuration location is stored in an environment variable**</span></span>  
 <span data-ttu-id="eb31c-208">Use para especificar a variável de ambiente onde a configuração está armazenada.</span><span class="sxs-lookup"><span data-stu-id="eb31c-208">Use to specify the environment variable where the configuration is stored.</span></span>  
  
|<span data-ttu-id="eb31c-209">Valor</span><span class="sxs-lookup"><span data-stu-id="eb31c-209">Value</span></span>|<span data-ttu-id="eb31c-210">Descrição</span><span class="sxs-lookup"><span data-stu-id="eb31c-210">Description</span></span>|  
|-----------|-----------------|  
|<span data-ttu-id="eb31c-211">**Variável de ambiente**</span><span class="sxs-lookup"><span data-stu-id="eb31c-211">**Environment variable**</span></span>|<span data-ttu-id="eb31c-212">Selecione uma variável de ambiente da lista.</span><span class="sxs-lookup"><span data-stu-id="eb31c-212">Select an environment variable from the list.</span></span>|  
  
## <a name="select-objects-to-export-page"></a><span data-ttu-id="eb31c-213">Selecionar a página Objetos a Exportar</span><span class="sxs-lookup"><span data-stu-id="eb31c-213">Select Objects to Export Page</span></span>  
 <span data-ttu-id="eb31c-214">Use a página **Selecionar Propriedade de Destino ou Selecionar Propriedades a Serem Exportadas** para especificar as propriedades do objeto que a configuração contém.</span><span class="sxs-lookup"><span data-stu-id="eb31c-214">Use the **Select Target Property or Select Properties to Export** page to specify the object properties that the configuration contains.</span></span> <span data-ttu-id="eb31c-215">O recurso para selecionar várias propriedades estará disponível somente se você selecionar o tipo de configuração XML.</span><span class="sxs-lookup"><span data-stu-id="eb31c-215">The ability to select multiple properties is available only if you select the XML configuration type.</span></span>  
  
### <a name="options"></a><span data-ttu-id="eb31c-216">Opções</span><span class="sxs-lookup"><span data-stu-id="eb31c-216">Options</span></span>  
 <span data-ttu-id="eb31c-217">**Objetos**</span><span class="sxs-lookup"><span data-stu-id="eb31c-217">**Objects**</span></span>  
 <span data-ttu-id="eb31c-218">Expanda a hierarquia de pacotes e selecione as propriedades a serem exportadas.</span><span class="sxs-lookup"><span data-stu-id="eb31c-218">Expand the package hierarchy and select the properties to export.</span></span>  
  
 <span data-ttu-id="eb31c-219">**Atributos da propriedade**</span><span class="sxs-lookup"><span data-stu-id="eb31c-219">**Property attributes**</span></span>  
 <span data-ttu-id="eb31c-220">Exiba os atributos de uma propriedade.</span><span class="sxs-lookup"><span data-stu-id="eb31c-220">View the attributes of a property.</span></span>  
  
 <span data-ttu-id="eb31c-221">**Próximo**</span><span class="sxs-lookup"><span data-stu-id="eb31c-221">**Next**</span></span>  
 <span data-ttu-id="eb31c-222">Vá para a próxima página do assistente.</span><span class="sxs-lookup"><span data-stu-id="eb31c-222">Go to the next page in the wizard.</span></span>  
  
## <a name="completing-the-wizard-page"></a><span data-ttu-id="eb31c-223">Concluindo a página do assistente</span><span class="sxs-lookup"><span data-stu-id="eb31c-223">Completing the Wizard Page</span></span>  
 <span data-ttu-id="eb31c-224">Use a página **Concluindo o Assistente** para fornecer um nome para a configuração e definições de exibição usado pelo assistente para criar a configuração.</span><span class="sxs-lookup"><span data-stu-id="eb31c-224">Use the **Completing the Wizard** page to provide a name for the configuration and view settings used by the wizard to create the configuration.</span></span> <span data-ttu-id="eb31c-225">Ao concluir o assistente, o **Organizador de Configurações do Pacote** é exibido e ele lista todas as configurações do pacote.</span><span class="sxs-lookup"><span data-stu-id="eb31c-225">After the wizard completes, the **Package Configurations Organizer** is displayed, which lists all configurations for the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="eb31c-226">Opções</span><span class="sxs-lookup"><span data-stu-id="eb31c-226">Options</span></span>  
 <span data-ttu-id="eb31c-227">**Nome da configuração**</span><span class="sxs-lookup"><span data-stu-id="eb31c-227">**Configuration name**</span></span>  
 <span data-ttu-id="eb31c-228">Digite o nome da configuração.</span><span class="sxs-lookup"><span data-stu-id="eb31c-228">Type the name of the configuration.</span></span>  
  
 <span data-ttu-id="eb31c-229">**Visualização**</span><span class="sxs-lookup"><span data-stu-id="eb31c-229">**Preview**</span></span>  
 <span data-ttu-id="eb31c-230">Exiba as definições usadas pelo assistente para criar a configuração.</span><span class="sxs-lookup"><span data-stu-id="eb31c-230">View the settings used by the wizard to create the configuration.</span></span>  
  
 <span data-ttu-id="eb31c-231">**Concluir**</span><span class="sxs-lookup"><span data-stu-id="eb31c-231">**Finish**</span></span>  
 <span data-ttu-id="eb31c-232">Crie a configuração e saia do **Assistente de Configuração de Pacotes**.</span><span class="sxs-lookup"><span data-stu-id="eb31c-232">Create the configuration and exit the **Package Configuration Wizard**.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="eb31c-233">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="eb31c-233">See Also</span></span>  
 [<span data-ttu-id="eb31c-234">Criar configurações de pacote</span><span class="sxs-lookup"><span data-stu-id="eb31c-234">Create Package Configurations</span></span>](../../2014/integration-services/create-package-configurations.md)  
  
  
