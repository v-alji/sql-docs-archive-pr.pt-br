---
title: Assistente de conversão de projeto Integration Services | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.ssis.migrationwizard.f1
ms.assetid: a192b094-4d0f-4c21-b911-460ec844a49f
author: chugugrace
ms.author: chugu
ms.openlocfilehash: c47dc8ed1d0485a62128be732cc34de1dca35740
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87574176"
---
# <a name="integration-services-project-conversion-wizard"></a><span data-ttu-id="6f947-102">Assistente de Conversão de Projeto do Integration Services</span><span class="sxs-lookup"><span data-stu-id="6f947-102">Integration Services Project Conversion Wizard</span></span>
  <span data-ttu-id="6f947-103">O **Assistente de Conversão de Projeto do Integration Services** converte um projeto no modelo de implantação de projeto.</span><span class="sxs-lookup"><span data-stu-id="6f947-103">The **Integration Services Project Conversion Wizard** converts a project to the project deployment model.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f947-104">Se o projeto contiver uma ou mais fontes de dados, as fontes de dados serão removidas quando a conversão de projeto estiver concluída.</span><span class="sxs-lookup"><span data-stu-id="6f947-104">If the project contains one or more datasources, the datasources are removed when the project conversion is completed.</span></span> <span data-ttu-id="6f947-105">Para criar uma conexão com uma fonte de dados que pode ser compartilhada pelos pacotes no projeto, adicione um gerenciador de conexões no nível de projeto.</span><span class="sxs-lookup"><span data-stu-id="6f947-105">To create a connection to a data source that can be shared by the packages in the project, add a connection manager at the project level.</span></span> <span data-ttu-id="6f947-106">Para obter mais informações, consulte [adicionar, excluir ou compartilhar um Gerenciador de Conexão em um pacote](../../2014/integration-services/add-delete-or-share-a-connection-manager-in-a-package.md).</span><span class="sxs-lookup"><span data-stu-id="6f947-106">For more information, see [Add, Delete, or Share a Connection Manager in a Package](../../2014/integration-services/add-delete-or-share-a-connection-manager-in-a-package.md).</span></span>  
  
 <span data-ttu-id="6f947-107">**O que você deseja fazer?**</span><span class="sxs-lookup"><span data-stu-id="6f947-107">**What do you want to do?**</span></span>  
  
-   [<span data-ttu-id="6f947-108">Abrir o Assistente de Conversão de Projeto do Integration Services</span><span class="sxs-lookup"><span data-stu-id="6f947-108">Open the Integration Services Project Conversion Wizard</span></span>](#open_dialog)  
  
-   [<span data-ttu-id="6f947-109">Definir opções na página Localizar Pacotes</span><span class="sxs-lookup"><span data-stu-id="6f947-109">Set Options on the Locate Packages Page</span></span>](#locate)  
  
-   [<span data-ttu-id="6f947-110">Definir opções na página Selecionar Pacotes</span><span class="sxs-lookup"><span data-stu-id="6f947-110">Set Options on the Select Packages Page</span></span>](#selectPackages)  
  
-   [<span data-ttu-id="6f947-111">Definir opções na página Selecionar Destino</span><span class="sxs-lookup"><span data-stu-id="6f947-111">Set Options on the Select Destination Page</span></span>](#destination)  
  
-   [<span data-ttu-id="6f947-112">Definir opções na página Especificar Propriedades do Projeto</span><span class="sxs-lookup"><span data-stu-id="6f947-112">Set Options on the Specify Project Properties Page</span></span>](#projectProperties)  
  
-   [<span data-ttu-id="6f947-113">Definir opções na página Atualizar a Tarefa Executar Pacote</span><span class="sxs-lookup"><span data-stu-id="6f947-113">Set Options on the Update Execute Package Task Page</span></span>](#executePackage)  
  
-   [<span data-ttu-id="6f947-114">Definir opções na página Selecionar Configurações</span><span class="sxs-lookup"><span data-stu-id="6f947-114">Set Options on the Select Configurations Page</span></span>](#configurations)  
  
-   [<span data-ttu-id="6f947-115">Definir opções na página Criar Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6f947-115">Set Options on the Create Parameters Page</span></span>](#createParameters)  
  
-   [<span data-ttu-id="6f947-116">Definir opções na página Configurar Parâmetros</span><span class="sxs-lookup"><span data-stu-id="6f947-116">Set Options on the Configure Parameters Page</span></span>](#configureParameters)  
  
-   [<span data-ttu-id="6f947-117">Definir as opções na página Revisão</span><span class="sxs-lookup"><span data-stu-id="6f947-117">Set the Options on the Review page</span></span>](#review)  
  
-   [<span data-ttu-id="6f947-118">Definir as opções em Executar Conversão</span><span class="sxs-lookup"><span data-stu-id="6f947-118">Set the Options on the Perform Conversion</span></span>](#conversion)  
  
##  <a name="open-the-integration-services-project-conversion-wizard"></a><a name="open_dialog"></a><span data-ttu-id="6f947-119">Abrir o assistente de conversão de projeto Integration Services</span><span class="sxs-lookup"><span data-stu-id="6f947-119">Open the Integration Services Project Conversion Wizard</span></span>  
 <span data-ttu-id="6f947-120">Siga um destes procedimentos para abrir o **Assistente de Conversão de Projeto do Integration Services** .</span><span class="sxs-lookup"><span data-stu-id="6f947-120">Do one of the following to open the **Integration Services Project Conversion** Wizard.</span></span>  
  
-   <span data-ttu-id="6f947-121">Abra o projeto no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)]e, no Gerenciador de Soluções, clique com o botão direito do mouse no projeto e clique em **Converter em Modelo de Implantação de Projeto**.</span><span class="sxs-lookup"><span data-stu-id="6f947-121">Open the project in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)], and then in Solution Explorer, right-click the project and click **Convert to Project Deployment Model**.</span></span>  
  
-   <span data-ttu-id="6f947-122">No Pesquisador de Objetos, no [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], clique com o botão direito do mouse no nó **Projetos** e selecione **Importar Pacotes**.</span><span class="sxs-lookup"><span data-stu-id="6f947-122">From Object Explorer in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], right-click the **Projects** node and select **Import Packages**.</span></span>  
  
 <span data-ttu-id="6f947-123">Dependendo em se você executa o **Assistente de Conversão de Projeto do Integration Services** no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] ou no [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], o assistente executa tarefas de conversão diferentes.</span><span class="sxs-lookup"><span data-stu-id="6f947-123">Depending on whether you run the **Integration Services Project Conversion Wizard** from [!INCLUDE[vsprvs](../includes/vsprvs-md.md)] or from [!INCLUDE[ssManStudioFull](../includes/ssmanstudiofull-md.md)], the wizard performs different conversion tasks.</span></span> <span data-ttu-id="6f947-124">Para obter mais informações, consulte [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span><span class="sxs-lookup"><span data-stu-id="6f947-124">For more information, see [Deploy Projects to Integration Services Server](../../2014/integration-services/deploy-projects-to-integration-services-server.md).</span></span>  
  
##  <a name="set-options-on-the-locate-packages-page"></a><a name="locate"></a><span data-ttu-id="6f947-125">Definir opções na página localizar pacotes</span><span class="sxs-lookup"><span data-stu-id="6f947-125">Set Options on the Locate Packages Page</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f947-126"> A página **Localizar Pacotes** somente está disponível quando você executa o assistente de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f947-126">The **Locate Packages** page is available only when you run the wizard from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="6f947-127">A opção a seguir é exibida na página quando você seleciona **Sistema de arquivos** na lista suspensa **Origem** .</span><span class="sxs-lookup"><span data-stu-id="6f947-127">The following option displays on the page when you select **File system** in the **Source** drop-down list.</span></span> <span data-ttu-id="6f947-128">Selecione esta opção quando o pacote estiver no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="6f947-128">Select this option when the package is resides in the file system.</span></span>  
  
 <span data-ttu-id="6f947-129">**Pasta**</span><span class="sxs-lookup"><span data-stu-id="6f947-129">**Folder**</span></span>  
 <span data-ttu-id="6f947-130">Digite o caminho do pacote ou navegue para o pacote clicando em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="6f947-130">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="6f947-131">As opções a seguir são exibidas na página quando você seleciona **Repositório de Pacotes SSIS** na lista suspensa **Origem**.</span><span class="sxs-lookup"><span data-stu-id="6f947-131">The following options display on the page when you select **SSIS Package Store** in the **Source** drop-down list.</span></span> <span data-ttu-id="6f947-132">Para obter mais informações sobre o repositório de pacotes, consulte [Gerenciamento de Pacotes &#40;Serviço SSIS&#41;](service/package-management-ssis-service.md).</span><span class="sxs-lookup"><span data-stu-id="6f947-132">For more information about the package store, see [Package Management &#40;SSIS Service&#41;](service/package-management-ssis-service.md).</span></span>  
  
 <span data-ttu-id="6f947-133">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="6f947-133">**Server**</span></span>  
 <span data-ttu-id="6f947-134">Digite o nome do servidor ou selecione o servidor.</span><span class="sxs-lookup"><span data-stu-id="6f947-134">Type the server name or select the server.</span></span>  
  
 <span data-ttu-id="6f947-135">**Pasta**</span><span class="sxs-lookup"><span data-stu-id="6f947-135">**Folder**</span></span>  
 <span data-ttu-id="6f947-136">Digite o caminho do pacote ou navegue para o pacote clicando em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="6f947-136">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="6f947-137">As opções a seguir são exibidas na página quando você seleciona **Microsoft SQL Server** na lista suspensa **Origem** .</span><span class="sxs-lookup"><span data-stu-id="6f947-137">The following options display on the page when you select **Microsoft SQL Server** in the **Source** drop-down list.</span></span> <span data-ttu-id="6f947-138">Selecione esta opção quando o pacote estiver no Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f947-138">Select this option when the package resides in Microsoft [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)].</span></span>  
  
 <span data-ttu-id="6f947-139">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="6f947-139">**Server**</span></span>  
 <span data-ttu-id="6f947-140">Digite o nome do servidor ou selecione o servidor.</span><span class="sxs-lookup"><span data-stu-id="6f947-140">Type the server name or select the server.</span></span>  
  
 <span data-ttu-id="6f947-141">**Usar autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="6f947-141">**Use Windows authentication**</span></span>  
 <span data-ttu-id="6f947-142">O modo de Autenticação do Microsoft Windows permite que um usuário se conecte por meio de uma conta de usuário do Windows.</span><span class="sxs-lookup"><span data-stu-id="6f947-142">Microsoft Windows Authentication mode allows a user to connect through a Windows user account.</span></span> <span data-ttu-id="6f947-143">Se usar Autenticação do Windows, não será preciso fornecer um nome de usuário nem senha.</span><span class="sxs-lookup"><span data-stu-id="6f947-143">If you use Windows Authentication, you do not need to provide a user name or password.</span></span>  
  
 <span data-ttu-id="6f947-144">**Usar autenticação SQL Server**</span><span class="sxs-lookup"><span data-stu-id="6f947-144">**Use SQL Server authentication**</span></span>  
 <span data-ttu-id="6f947-145">Quando um usuário se conecta com um nome de logon e senha especificados em uma conexão não confiável, o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] autentica a conexão verificando se foi definida uma conta de logon do [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] e se a senha especificada corresponde a uma senha registrada previamente.</span><span class="sxs-lookup"><span data-stu-id="6f947-145">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] authenticates the connection by checking to see if a [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="6f947-146">Se o [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] não tiver uma conta de logon definida, ocorrerá falha na autenticação e o usuário receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="6f947-146">If [!INCLUDE[ssNoVersion](../includes/ssnoversion-md.md)] does not have a login account set, authentication fails, and the user receives an error message.</span></span>  
  
 <span data-ttu-id="6f947-147">**Nome de usuário**</span><span class="sxs-lookup"><span data-stu-id="6f947-147">**User name**</span></span>  
 <span data-ttu-id="6f947-148">Especifique um nome de usuário quando você estiver usando a Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6f947-148">Specify a user name when you are using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="6f947-149">**Senha**</span><span class="sxs-lookup"><span data-stu-id="6f947-149">**Password**</span></span>  
 <span data-ttu-id="6f947-150">Forneça uma senha quando você estiver usando a Autenticação do SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6f947-150">Provide the password when you are using SQL Server Authentication.</span></span>  
  
 <span data-ttu-id="6f947-151">**Pasta**</span><span class="sxs-lookup"><span data-stu-id="6f947-151">**Folder**</span></span>  
 <span data-ttu-id="6f947-152">Digite o caminho do pacote ou navegue para o pacote clicando em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="6f947-152">Type the package path, or navigate to the package by clicking **Browse**.</span></span>  
  
##  <a name="set-options-on-the-select-packages-page"></a><a name="selectPackages"></a><span data-ttu-id="6f947-153">Definir opções na página Selecionar pacotes</span><span class="sxs-lookup"><span data-stu-id="6f947-153">Set Options on the Select Packages Page</span></span>  
 <span data-ttu-id="6f947-154">**Nome do pacote**</span><span class="sxs-lookup"><span data-stu-id="6f947-154">**Package Name**</span></span>  
 <span data-ttu-id="6f947-155">Lista o arquivo do pacote.</span><span class="sxs-lookup"><span data-stu-id="6f947-155">Lists the package file.</span></span>  
  
 <span data-ttu-id="6f947-156">**Status**</span><span class="sxs-lookup"><span data-stu-id="6f947-156">**Status**</span></span>  
 <span data-ttu-id="6f947-157">Indica se um pacote está pronto para ser convertido ao modelo de implantação de projeto.</span><span class="sxs-lookup"><span data-stu-id="6f947-157">Indicates whether a package is ready to convert to the project deployment model.</span></span>  
  
 <span data-ttu-id="6f947-158">**Message**</span><span class="sxs-lookup"><span data-stu-id="6f947-158">**Message**</span></span>  
 <span data-ttu-id="6f947-159">Exibe uma mensagem associada ao pacote.</span><span class="sxs-lookup"><span data-stu-id="6f947-159">Displays a message associated with the package.</span></span>  
  
 <span data-ttu-id="6f947-160">**Senha**</span><span class="sxs-lookup"><span data-stu-id="6f947-160">**Password**</span></span>  
 <span data-ttu-id="6f947-161">Exibe uma senha associada ao pacote.</span><span class="sxs-lookup"><span data-stu-id="6f947-161">Displays a password associated with the package.</span></span> <span data-ttu-id="6f947-162">O texto da senha está oculto.</span><span class="sxs-lookup"><span data-stu-id="6f947-162">The password text is hidden.</span></span>  
  
 <span data-ttu-id="6f947-163">**Aplicar à seleção**</span><span class="sxs-lookup"><span data-stu-id="6f947-163">**Apply to selection**</span></span>  
 <span data-ttu-id="6f947-164">Clique para aplicar a senha na caixa de texto **Senha** , para o pacote ou pacotes selecionados.</span><span class="sxs-lookup"><span data-stu-id="6f947-164">Click to apply the password in the **Password** text box, to the selected package or packages.</span></span>  
  
 <span data-ttu-id="6f947-165">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="6f947-165">**Refresh**</span></span>  
 <span data-ttu-id="6f947-166">Atualiza a lista de pacotes.</span><span class="sxs-lookup"><span data-stu-id="6f947-166">Refreshes the list of packages.</span></span>  
  
##  <a name="set-options-on-the-select-destination-page"></a><a name="destination"></a><span data-ttu-id="6f947-167">Definir opções na página Selecionar destino</span><span class="sxs-lookup"><span data-stu-id="6f947-167">Set Options on the Select Destination Page</span></span>  
 <span data-ttu-id="6f947-168">Nessa página, especifique o nome e o caminho de um novo arquivo de implantação de projeto (.ispac) ou selecione um arquivo existente.</span><span class="sxs-lookup"><span data-stu-id="6f947-168">On this page, specify the name and path for a new project deployment file (.ispac) or select an existing file.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f947-169"> A página **Selecionar destino** somente está disponível quando você executa o assistente de [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f947-169">The **Select Destination** page is available only when you run the wizard from [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)].</span></span>  
  
 <span data-ttu-id="6f947-170">**Caminho de saída**</span><span class="sxs-lookup"><span data-stu-id="6f947-170">**Output path**</span></span>  
 <span data-ttu-id="6f947-171">Digite o caminho para o arquivo de implantação ou navegue para o arquivo clicando em **Procurar**.</span><span class="sxs-lookup"><span data-stu-id="6f947-171">Type the path for the deployment file or navigate to the file by clicking **Browse**.</span></span>  
  
 <span data-ttu-id="6f947-172">**Nome do projeto**</span><span class="sxs-lookup"><span data-stu-id="6f947-172">**Project name**</span></span>  
 <span data-ttu-id="6f947-173">Digite o nome do projeto.</span><span class="sxs-lookup"><span data-stu-id="6f947-173">Type the project name.</span></span>  
  
 <span data-ttu-id="6f947-174">**Nível de proteção**</span><span class="sxs-lookup"><span data-stu-id="6f947-174">**Protection level**</span></span>  
 <span data-ttu-id="6f947-175">Selecione o nível de proteção.</span><span class="sxs-lookup"><span data-stu-id="6f947-175">Select the protection level.</span></span> <span data-ttu-id="6f947-176">Para obter mais informações, consulte [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="6f947-176">For more information, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
 <span data-ttu-id="6f947-177">**Descrição do projeto**</span><span class="sxs-lookup"><span data-stu-id="6f947-177">**Project description**</span></span>  
 <span data-ttu-id="6f947-178">Digite uma descrição opcional para o projeto.</span><span class="sxs-lookup"><span data-stu-id="6f947-178">Type an optional description for the project.</span></span>  
  
##  <a name="set-options-on-the-specify-project-properties-page"></a><a name="projectProperties"></a><span data-ttu-id="6f947-179">Definir opções na página especificar propriedades do projeto</span><span class="sxs-lookup"><span data-stu-id="6f947-179">Set Options on the Specify Project Properties Page</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="6f947-180"> A página **Especificar Propriedades do Projeto** somente está disponível quando você executa o assistente de [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f947-180">The **Specify Project Properties** page is available only when you run the wizard from [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="6f947-181">**Nome do projeto**</span><span class="sxs-lookup"><span data-stu-id="6f947-181">**Project name**</span></span>  
 <span data-ttu-id="6f947-182">Lista o nome do projeto.</span><span class="sxs-lookup"><span data-stu-id="6f947-182">Lists the project name.</span></span>  
  
 <span data-ttu-id="6f947-183">**Nível de proteção**</span><span class="sxs-lookup"><span data-stu-id="6f947-183">**Protection level**</span></span>  
 <span data-ttu-id="6f947-184">Selecione um nível de proteção para os pacotes contidos no projeto.</span><span class="sxs-lookup"><span data-stu-id="6f947-184">Select a protection level for the packages contained in the project.</span></span> <span data-ttu-id="6f947-185">Para obter mais informações sobre níveis de proteção, consulte [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span><span class="sxs-lookup"><span data-stu-id="6f947-185">For more information about protection levels, see [Access Control for Sensitive Data in Packages](security/access-control-for-sensitive-data-in-packages.md).</span></span>  
  
 <span data-ttu-id="6f947-186">**Descrição do projeto**</span><span class="sxs-lookup"><span data-stu-id="6f947-186">**Project description**</span></span>  
 <span data-ttu-id="6f947-187">Digite uma descrição de projeto opcional.</span><span class="sxs-lookup"><span data-stu-id="6f947-187">Type an optional project description.</span></span>  
  
##  <a name="set-options-on-the-update-execute-package-task-page"></a><a name="executePackage"></a><span data-ttu-id="6f947-188">Definir opções na página atualizar tarefa Executar Pacote</span><span class="sxs-lookup"><span data-stu-id="6f947-188">Set Options on the Update Execute Package Task Page</span></span>  
 <span data-ttu-id="6f947-189">Atualizar as Tarefas Executar Pacote contidas nos pacotes, para usar uma referência baseada em projeto.</span><span class="sxs-lookup"><span data-stu-id="6f947-189">Update Execute Package Tasks contain in the packages, to use a project-based reference.</span></span> <span data-ttu-id="6f947-190">Para obter mais informações, consulte [Execute Package Task Editor](../../2014/integration-services/execute-package-task-editor.md).</span><span class="sxs-lookup"><span data-stu-id="6f947-190">For more information, see [Execute Package Task Editor](../../2014/integration-services/execute-package-task-editor.md).</span></span>  
  
 <span data-ttu-id="6f947-191">**Pacote pai**</span><span class="sxs-lookup"><span data-stu-id="6f947-191">**Parent Package**</span></span>  
 <span data-ttu-id="6f947-192">Lista o nome do pacote que executa o pacote filho usando a tarefa Executar Pacote.</span><span class="sxs-lookup"><span data-stu-id="6f947-192">Lists the name of the package that executes the child package using the Execute Package task.</span></span>  
  
 <span data-ttu-id="6f947-193">**Nome da tarefa**</span><span class="sxs-lookup"><span data-stu-id="6f947-193">**Task name**</span></span>  
 <span data-ttu-id="6f947-194">Lista o nome da tarefa Executar Pacote.</span><span class="sxs-lookup"><span data-stu-id="6f947-194">Lists the name of the Execute Package task.</span></span>  
  
 <span data-ttu-id="6f947-195">**Referência original**</span><span class="sxs-lookup"><span data-stu-id="6f947-195">**Original reference**</span></span>  
 <span data-ttu-id="6f947-196">Lista o caminho atual do pacote filho.</span><span class="sxs-lookup"><span data-stu-id="6f947-196">Lists the current path of the child package.</span></span>  
  
 <span data-ttu-id="6f947-197">**Atribuir referência**</span><span class="sxs-lookup"><span data-stu-id="6f947-197">**Assign reference**</span></span>  
 <span data-ttu-id="6f947-198">Selecione um pacote filho armazenado no projeto.</span><span class="sxs-lookup"><span data-stu-id="6f947-198">Select a child package stored in the project.</span></span>  
  
##  <a name="set-options-on-the-select-configurations-page"></a><a name="configurations"></a><span data-ttu-id="6f947-199">Definir opções na página Selecionar configurações</span><span class="sxs-lookup"><span data-stu-id="6f947-199">Set Options on the Select Configurations Page</span></span>  
 <span data-ttu-id="6f947-200">Selecione as configurações de pacote que você deseja substituir por parâmetros.</span><span class="sxs-lookup"><span data-stu-id="6f947-200">Select the package configurations that you want to replace with parameters.</span></span>  
  
 <span data-ttu-id="6f947-201">**Pacote**</span><span class="sxs-lookup"><span data-stu-id="6f947-201">**Package**</span></span>  
 <span data-ttu-id="6f947-202">Lista o arquivo do pacote.</span><span class="sxs-lookup"><span data-stu-id="6f947-202">Lists the package file.</span></span>  
  
 <span data-ttu-id="6f947-203">**Tipo**</span><span class="sxs-lookup"><span data-stu-id="6f947-203">**Type**</span></span>  
 <span data-ttu-id="6f947-204">Lista o tipo de configuração, como um arquivo de configuração XML.</span><span class="sxs-lookup"><span data-stu-id="6f947-204">Lists the type of configuration, such as an XML configuration file.</span></span>  
  
 <span data-ttu-id="6f947-205">**Cadeia de Caracteres de Configuração**</span><span class="sxs-lookup"><span data-stu-id="6f947-205">**Configuration String**</span></span>  
 <span data-ttu-id="6f947-206">Lista o caminho do arquivo de configuração.</span><span class="sxs-lookup"><span data-stu-id="6f947-206">Lists the path of the configuration file.</span></span>  
  
 <span data-ttu-id="6f947-207">**Status**</span><span class="sxs-lookup"><span data-stu-id="6f947-207">**Status**</span></span>  
 <span data-ttu-id="6f947-208">Exibe uma mensagem de status para a configuração.</span><span class="sxs-lookup"><span data-stu-id="6f947-208">Displays a status message for the configuration.</span></span> <span data-ttu-id="6f947-209">Clique na mensagem para exibir o texto inteiro da mensagem.</span><span class="sxs-lookup"><span data-stu-id="6f947-209">Click the message to view the entire message text.</span></span>  
  
 <span data-ttu-id="6f947-210">**Adicionar configurações**</span><span class="sxs-lookup"><span data-stu-id="6f947-210">**Add Configurations**</span></span>  
 <span data-ttu-id="6f947-211">Adicione configurações de pacote contidas em outros projetos à lista de configurações disponíveis que você deseja substituir por parâmetros.</span><span class="sxs-lookup"><span data-stu-id="6f947-211">Add package configurations contained in other projects to the list of available configurations that you want to replace with parameters.</span></span> <span data-ttu-id="6f947-212">Você pode selecionar configurações armazenadas em um sistema de arquivos ou armazenados no SQL Server.</span><span class="sxs-lookup"><span data-stu-id="6f947-212">You can select configurations stored in a file system or stored in SQL Server.</span></span>  
  
 <span data-ttu-id="6f947-213">**Atualizar**</span><span class="sxs-lookup"><span data-stu-id="6f947-213">**Refresh**</span></span>  
 <span data-ttu-id="6f947-214">Clique para atualizar a lista de configurações.</span><span class="sxs-lookup"><span data-stu-id="6f947-214">Click to refresh the list of configurations.</span></span>  
  
 <span data-ttu-id="6f947-215">**Remover configurações de todos os pacotes após a conversão**</span><span class="sxs-lookup"><span data-stu-id="6f947-215">**Remove configurations from all packages after conversion**</span></span>  
 <span data-ttu-id="6f947-216">É recomendável remover todas as configurações do projeto selecionando essa opção.</span><span class="sxs-lookup"><span data-stu-id="6f947-216">It is recommended that you remove all configurations from the project by selecting this option.</span></span>  
  
 <span data-ttu-id="6f947-217">Se você não selecionar essa opção, somente as configurações selecionadas para substituir por parâmetros serão removidas.</span><span class="sxs-lookup"><span data-stu-id="6f947-217">If you don't select this option, only the configurations that you selected to replace with parameters are removed.</span></span>  
  
##  <a name="set-options-on-the-create-parameters-page"></a><a name="createParameters"></a><span data-ttu-id="6f947-218">Definir opções na página criar parâmetros</span><span class="sxs-lookup"><span data-stu-id="6f947-218">Set Options on the Create Parameters Page</span></span>  
 <span data-ttu-id="6f947-219">Selecione o nome do parâmetro e o escopo para cada propriedade de configuração.</span><span class="sxs-lookup"><span data-stu-id="6f947-219">Select the parameter name and scope for each configuration property.</span></span>  
  
 <span data-ttu-id="6f947-220">**Pacote**</span><span class="sxs-lookup"><span data-stu-id="6f947-220">**Package**</span></span>  
 <span data-ttu-id="6f947-221">Lista o arquivo do pacote.</span><span class="sxs-lookup"><span data-stu-id="6f947-221">Lists the package file.</span></span>  
  
 <span data-ttu-id="6f947-222">**Nome do parâmetro**</span><span class="sxs-lookup"><span data-stu-id="6f947-222">**Parameter Name**</span></span>  
 <span data-ttu-id="6f947-223">Lista o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="6f947-223">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="6f947-224">**Escopo**</span><span class="sxs-lookup"><span data-stu-id="6f947-224">**Scope**</span></span>  
 <span data-ttu-id="6f947-225">Selecione o escopo do parâmetro, pacote ou projeto.</span><span class="sxs-lookup"><span data-stu-id="6f947-225">Select the scope of the parameter, either package or project.</span></span>  
  
##  <a name="set-options-on-the-configure-parameters-page"></a><a name="configureParameters"></a><span data-ttu-id="6f947-226">Definir opções na página configurar parâmetros</span><span class="sxs-lookup"><span data-stu-id="6f947-226">Set Options on the Configure Parameters Page</span></span>  
 <span data-ttu-id="6f947-227">**Nome**</span><span class="sxs-lookup"><span data-stu-id="6f947-227">**Name**</span></span>  
 <span data-ttu-id="6f947-228">Lista o nome do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="6f947-228">Lists the parameter name.</span></span>  
  
 <span data-ttu-id="6f947-229">**Escopo**</span><span class="sxs-lookup"><span data-stu-id="6f947-229">**Scope**</span></span>  
 <span data-ttu-id="6f947-230">Lista o escopo do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="6f947-230">Lists the scope of the parameter.</span></span>  
  
 <span data-ttu-id="6f947-231">**Valor**</span><span class="sxs-lookup"><span data-stu-id="6f947-231">**Value**</span></span>  
 <span data-ttu-id="6f947-232">Lista o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="6f947-232">Lists the parameter value.</span></span>  
  
 <span data-ttu-id="6f947-233">Clique no botão de reticências ao lado do campo de valor para configurar as propriedades do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="6f947-233">Click the ellipsis button next to the value field to configure the parameter properties.</span></span>  
  
 <span data-ttu-id="6f947-234">Na caixa de diálogo **Definir Detalhes de Parâmetros** , edite o valor do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="6f947-234">In the **Set Parameter Details** dialog box, you can edit the parameter value.</span></span> <span data-ttu-id="6f947-235">Você também pode especificar se o valor do parâmetro deve ser fornecido quando você executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="6f947-235">You can also specify whether the parameter value must be provided when you run the package.</span></span>  
  
 <span data-ttu-id="6f947-236">Você pode modificar o valor na página **Parâmetros** da caixa de diálogo **Configurar** no [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], clique no botão Procurar ao lado do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="6f947-236">You can modify value in the **Parameters** page of the **Configure** dialog box in [!INCLUDE[ssManStudio](../includes/ssmanstudio-md.md)], by clicking the browse button next to the parameter.</span></span> <span data-ttu-id="6f947-237">A caixa de diálogo **Definir Valor do Parâmetro** é exibida.</span><span class="sxs-lookup"><span data-stu-id="6f947-237">The **Set Parameter Value** dialog box appears.</span></span>  
  
 <span data-ttu-id="6f947-238">A caixa de diálogo **Definir Detalhes de Parâmetros** também lista o tipo de dados do valor de parâmetro e a origem do parâmetro.</span><span class="sxs-lookup"><span data-stu-id="6f947-238">The **Set Parameter Details** dialog box also lists the data type of the parameter value and the origin of the parameter.</span></span>  
  
##  <a name="set-the-options-on-the-review-page"></a><a name="review"></a><span data-ttu-id="6f947-239">Definir as opções na página revisão</span><span class="sxs-lookup"><span data-stu-id="6f947-239">Set the Options on the Review page</span></span>  
 <span data-ttu-id="6f947-240">Use a página **Revisão** para confirmar as opções selecionadas para a conversão do projeto.</span><span class="sxs-lookup"><span data-stu-id="6f947-240">Use the **Review** page to confirm the options that you've selected for the conversion of the project.</span></span>  
  
 <span data-ttu-id="6f947-241">**Anterior**</span><span class="sxs-lookup"><span data-stu-id="6f947-241">**Previous**</span></span>  
 <span data-ttu-id="6f947-242">Clique para alterar uma opção.</span><span class="sxs-lookup"><span data-stu-id="6f947-242">Click to change an option.</span></span>  
  
 <span data-ttu-id="6f947-243">**Converter**</span><span class="sxs-lookup"><span data-stu-id="6f947-243">**Convert**</span></span>  
 <span data-ttu-id="6f947-244">Clique para converter o projeto no modelo de implantação de projeto.</span><span class="sxs-lookup"><span data-stu-id="6f947-244">Click to convert the project to the project deployment model.</span></span>  
  
##  <a name="set-the-options-on-the-perform-conversion"></a><a name="conversion"></a><span data-ttu-id="6f947-245">Definir as opções na conversão executar</span><span class="sxs-lookup"><span data-stu-id="6f947-245">Set the Options on the Perform Conversion</span></span>  
 <span data-ttu-id="6f947-246">A página Executar Conversão mostra o status da conversão do projeto.</span><span class="sxs-lookup"><span data-stu-id="6f947-246">The Perform Conversion page shows status of the project conversion.</span></span>  
  
 <span data-ttu-id="6f947-247">**Ação**</span><span class="sxs-lookup"><span data-stu-id="6f947-247">**Action**</span></span>  
 <span data-ttu-id="6f947-248">Lista uma etapa de conversão específica.</span><span class="sxs-lookup"><span data-stu-id="6f947-248">Lists a specific conversion step.</span></span>  
  
 <span data-ttu-id="6f947-249">**Resultado**</span><span class="sxs-lookup"><span data-stu-id="6f947-249">**Result**</span></span>  
 <span data-ttu-id="6f947-250">Lista o status de cada etapa de conversão.</span><span class="sxs-lookup"><span data-stu-id="6f947-250">Lists the status of each conversion step.</span></span> <span data-ttu-id="6f947-251">Clique na mensagem de status para obter mais informações.</span><span class="sxs-lookup"><span data-stu-id="6f947-251">Click the status message for more information.</span></span>  
  
 <span data-ttu-id="6f947-252">A conversão de projeto não será salva até que o projeto seja salvo no [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span><span class="sxs-lookup"><span data-stu-id="6f947-252">The project conversion is not saved until the project is saved in [!INCLUDE[vsprvs](../includes/vsprvs-md.md)].</span></span>  
  
 <span data-ttu-id="6f947-253">**Salvar relatório**</span><span class="sxs-lookup"><span data-stu-id="6f947-253">**Save report**</span></span>  
 <span data-ttu-id="6f947-254">Clique para salvar um resumo da conversão de projeto em um arquivo .xml.</span><span class="sxs-lookup"><span data-stu-id="6f947-254">Click to save a summary of the project conversion in an .xml file.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6f947-255">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="6f947-255">See Also</span></span>  
 [<span data-ttu-id="6f947-256">Implantar projetos no servidor do Integration Services</span><span class="sxs-lookup"><span data-stu-id="6f947-256">Deploy Projects to Integration Services Server</span></span>](../../2014/integration-services/deploy-projects-to-integration-services-server.md)  
  
  
