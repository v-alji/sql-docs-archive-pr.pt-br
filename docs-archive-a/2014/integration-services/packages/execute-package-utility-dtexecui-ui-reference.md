---
title: Referência da interface do usuário do Utilitário de Execução de Pacotes (DtExecUI) | Microsoft Docs
ms.custom: ''
ms.date: 06/13/2017
ms.prod: sql-server-2014
ms.reviewer: ''
ms.technology: integration-services
ms.topic: conceptual
f1_keywords:
- sql12.dts.dtexecui.general.f1
- sql12.dts.dtexecui.executionoptions.f1
- sql12.dts.dtexecui.configuration.f1
- sql12.dts.dtexecui.setvalues.f1
- sql12.dts.dtexecui.commandline.f1
- sql12.dts.dtexecui.commandfiles.f1
- sql12.dts.dtexecui.verification.f1
- sql12.dts.dtexecui.datasources.f1
- sql12.dts.dtexecui.reporting.f1
- sql12.dts.dtexecui.logging.f1
helpviewer_keywords:
- DTExecUI utility
ms.assetid: 3d71df39-126b-4c8e-bd77-128bbd5b0887
author: chugugrace
ms.author: chugu
ms.openlocfilehash: 13601983a4ab841a2b64ff8e4fc722fcf5ae496c
ms.sourcegitcommit: ad4d92dce894592a259721a1571b1d8736abacdb
ms.translationtype: MT
ms.contentlocale: pt-BR
ms.lasthandoff: 08/04/2020
ms.locfileid: "87575202"
---
# <a name="execute-package-utility-dtexecui-ui-reference"></a><span data-ttu-id="718e1-102">Referência da interface do usuário do utilitário de Execução de Pacotes (DtExecUI)</span><span class="sxs-lookup"><span data-stu-id="718e1-102">Execute Package Utility (DtExecUI) UI Reference</span></span>
  <span data-ttu-id="718e1-103">Use o **Utilitário do Pacote de Execução** para executar pacotes do [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="718e1-103">Use the **Execute Package Utility** to run [!INCLUDE[ssISnoversion](../../includes/ssisnoversion-md.md)] packages.</span></span> <span data-ttu-id="718e1-104">O utilitário executa pacotes que estão armazenados em um dos três locais: o banco de dados do [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)], o Repositório de pacotes [!INCLUDE[ssIS](../../includes/ssis-md.md)] e o sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="718e1-104">The utility runs packages that are stored in one of three locations: [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] database, the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store, and the file system.</span></span> <span data-ttu-id="718e1-105">Essa interface do usuário, que pode ser aberta de [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] ou digitando `dtexecui` em um prompt de comando, é uma alternativa à execução de pacotes usando a ferramenta de prompt de comando **dtexec** .</span><span class="sxs-lookup"><span data-stu-id="718e1-105">This user interface, which can be opened from [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)] or by typing `dtexecui` at a command prompt, is an alternative to running packages by using the **DTExec** command prompt tool.</span></span>  
  
 <span data-ttu-id="718e1-106">Os pacotes são executados no mesmo processo que o utilitário **dtexecui.exe** .</span><span class="sxs-lookup"><span data-stu-id="718e1-106">Packages execute in the same process as the **dtexecui.exe** utility.</span></span> <span data-ttu-id="718e1-107">Como esse utilitário é uma ferramenta de 32 bits, os pacotes são executados por meio do **dtexecui.exe** em um ambiente de 64 bits no Windows on Win32 (WOW).</span><span class="sxs-lookup"><span data-stu-id="718e1-107">Because this utility is a 32-bit tool, packages run by using **dtexecui.exe** in a 64-bit environment run in Windows on Win32 (WOW).</span></span> <span data-ttu-id="718e1-108">Ao desenvolver e testar comandos por meio do utilitário dtexecui.exe em um computador de 64 bits, será necessário testar os comandos no modo de 64 bits com a versão de 64 bits do **dtexec.exe** antes de implantar ou agendar os comandos em um servidor de produção.</span><span class="sxs-lookup"><span data-stu-id="718e1-108">When developing and testing commands by using the dtexecui.exe utility on a 64-bit computer, you should test the commands in 64-bit mode by using the 64-bit version of **dtexec.exe** before deploying or scheduling the commands on a production server.</span></span>  
  
 <span data-ttu-id="718e1-109">O **Utilitário de Execução de Pacotes** é uma interface gráfica do usuário da ferramenta de prompt de comando do **DTExec** .</span><span class="sxs-lookup"><span data-stu-id="718e1-109">The **Execute Package Utility** is a graphical user interface for the **DTExec** command prompt tool.</span></span> <span data-ttu-id="718e1-110">A interface do usuário facilita a configuração de opções e monta automaticamente a linha de comando que é passada para a ferramenta de prompt de comando **DTExec** ao executar o pacote a partir das opções especificadas.</span><span class="sxs-lookup"><span data-stu-id="718e1-110">The user interface makes it easy to configure options and it automatically assembles the command line that is passed to the **DTExec** command prompt tool when you run the package from the specified options.</span></span>  
  
 <span data-ttu-id="718e1-111">O **Utilitário de Execução de Pacotes** também pode ser usado para montar as linhas de comando que você usa ao executar o **DTExec** diretamente.</span><span class="sxs-lookup"><span data-stu-id="718e1-111">The **Execute Package Utility** can also be used to assemble command lines that you use when running **DTExec** directly.</span></span>  
  
### <a name="to-open-execute-package-utility-in-sql-server-management-studio"></a><span data-ttu-id="718e1-112">Para abrir o utilitário Executar Pacote no SQL Server Management Studio</span><span class="sxs-lookup"><span data-stu-id="718e1-112">To open Execute Package Utility in SQL Server Management Studio</span></span>  
  
1.  <span data-ttu-id="718e1-113">No [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], no menu **Exibir** , clique em **Pesquisador de Objetos**.</span><span class="sxs-lookup"><span data-stu-id="718e1-113">In [!INCLUDE[ssManStudioFull](../../includes/ssmanstudiofull-md.md)], on the **View** menu, click **Object Explorer**.</span></span>  
  
2.  <span data-ttu-id="718e1-114">No Pesquisador de Objetos, clique em **Conectar**e em **Integration Services**.</span><span class="sxs-lookup"><span data-stu-id="718e1-114">In Object Explorer, click **Connect**, and then click **Integration Services**.</span></span>  
  
3.  <span data-ttu-id="718e1-115">Na caixa de diálogo **Conectar ao Servidor** , digite o nome do servidor na lista **Nome do servidor** e clique em **Conectar**.</span><span class="sxs-lookup"><span data-stu-id="718e1-115">In the **Connect to Server** dialog box, enter the server name in the **Server name** list, and then click **Connect**.</span></span>  
  
4.  <span data-ttu-id="718e1-116">Expanda a pasta e as subpastas do **Pacote Armazenado**, clique com o botão direito do mouse no pacote a ser executado e, em seguida, clique em **Executar Pacote**.</span><span class="sxs-lookup"><span data-stu-id="718e1-116">Expand the **Stored Package**s folder and subfolders, right-click the package you want to run, and then click **Run Package**.</span></span>  
  
### <a name="to-open-the-execute-package-utility-at-the-command-prompt"></a><span data-ttu-id="718e1-117">Para abrir o utilitário Executar Pacote no prompt de comando</span><span class="sxs-lookup"><span data-stu-id="718e1-117">To open the Execute Package Utility at the Command Prompt</span></span>  
  
-   <span data-ttu-id="718e1-118">Em uma janela do prompt de comando, execute `dtexecui`.</span><span class="sxs-lookup"><span data-stu-id="718e1-118">In a command prompt window, run `dtexecui`.</span></span>  
  
 <span data-ttu-id="718e1-119">As seções a seguir descrevem páginas da caixa de diálogo **Utilitário de Execução de Pacotes** .</span><span class="sxs-lookup"><span data-stu-id="718e1-119">The following sections describe pages of the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="general-page"></a><span data-ttu-id="718e1-120">Página Geral</span><span class="sxs-lookup"><span data-stu-id="718e1-120">General Page</span></span>  
 <span data-ttu-id="718e1-121">Use a página **Geral** da caixa de diálogo **Utilitário de Execução de Pacotes** para especificar um nome e um local para o pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-121">Use the **General** page of the **Execute Package Utility** dialog box to specify a package name and location.</span></span>  
  
 <span data-ttu-id="718e1-122">O Utilitário do Pacote de Execução (dtexecui.exe) sempre executa um pacote no computador local, mesmo que ele tenha sido salvo em um computador remoto.</span><span class="sxs-lookup"><span data-stu-id="718e1-122">The Execute Package utility (dtexecui.exe) always runs a package on the local computer, even if the package is saved on a remote server.</span></span> <span data-ttu-id="718e1-123">Se o pacote remoto usar arquivos de configuração que também tenham sido salvos no servidor remoto, pode ser que o Utilitário do Pacote de Execução não localize as configurações e ocorra uma falha no pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-123">If the remote package uses configuration files that also are saved on the remote server, then the Execute Package utility may not locate the configurations and the package fails.</span></span> <span data-ttu-id="718e1-124">Para evitar esse problema, as configurações devem ser consultadas usando um nome do compartilhamento UNC (Convenção de Nomenclatura Universal) como \\\myserver\myfile.</span><span class="sxs-lookup"><span data-stu-id="718e1-124">To avoid this problem, the configurations must be referenced by using a Universal Naming Convention (UNC) share name like \\\myserver\myfile.</span></span>  
  
### <a name="static-options"></a><span data-ttu-id="718e1-125">Opções estáticas</span><span class="sxs-lookup"><span data-stu-id="718e1-125">Static Options</span></span>  
 <span data-ttu-id="718e1-126">**Origem do pacote**</span><span class="sxs-lookup"><span data-stu-id="718e1-126">**Package source**</span></span>  
 <span data-ttu-id="718e1-127">Especifique o local do pacote a ser executado usando as seguintes opções:</span><span class="sxs-lookup"><span data-stu-id="718e1-127">Specify the location of the package to run, using the following options:</span></span>  
  
|||  
|-|-|  
|<span data-ttu-id="718e1-128">Valor</span><span class="sxs-lookup"><span data-stu-id="718e1-128">Value</span></span>|<span data-ttu-id="718e1-129">DESCRIÇÃO</span><span class="sxs-lookup"><span data-stu-id="718e1-129">Description</span></span>|  
|<span data-ttu-id="718e1-130">**SQL Server**</span><span class="sxs-lookup"><span data-stu-id="718e1-130">**SQL Server**</span></span>|<span data-ttu-id="718e1-131">Selecione esta opção quando o pacote estiver no [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="718e1-131">Select this option when the package resides in [!INCLUDE[msCoName](../../includes/msconame-md.md)] [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="718e1-132">Especifique uma instância do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e forneça um nome de usuário e senha para a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="718e1-132">Specify an instance of [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] and provide a user name and password for [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="718e1-133">Cada nome de usuário e senha adiciona as opções de **/USER** _nome de usuário_ e **/PASSWORD** _senha_ ao prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="718e1-133">Each user name and password adds the **/USER** _username_ and **/PASSWORD** _password_ options to the command prompt.</span></span>|  
|<span data-ttu-id="718e1-134">**Sistema de Arquivos**</span><span class="sxs-lookup"><span data-stu-id="718e1-134">**File system**</span></span>|<span data-ttu-id="718e1-135">Selecione esta opção quando o pacote estiver no sistema de arquivos.</span><span class="sxs-lookup"><span data-stu-id="718e1-135">Select this option when the package resides in the file system.</span></span>|  
|<span data-ttu-id="718e1-136">**Armazenamento de Pacotes SSIS**</span><span class="sxs-lookup"><span data-stu-id="718e1-136">**SSIS Package Store**</span></span>|<span data-ttu-id="718e1-137">Selecione esta opção quando o pacote estiver no Armazenamento de Pacotes [!INCLUDE[ssIS](../../includes/ssis-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="718e1-137">Select this option when the package resides in the [!INCLUDE[ssIS](../../includes/ssis-md.md)] Package Store.</span></span>|  
  
 <span data-ttu-id="718e1-138">Cada uma dessas seleções apresenta o seguinte conjunto de opções.</span><span class="sxs-lookup"><span data-stu-id="718e1-138">Each of these selections has the following set of options.</span></span>  
  
 <span data-ttu-id="718e1-139">**Executar**</span><span class="sxs-lookup"><span data-stu-id="718e1-139">**Execute**</span></span>  
 <span data-ttu-id="718e1-140">Clique para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-140">Click to run the package.</span></span>  
  
 <span data-ttu-id="718e1-141">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="718e1-141">**Close**</span></span>  
 <span data-ttu-id="718e1-142">Clique para fechar a caixa de diálogo **Utilitário do Pacote de Execução** .</span><span class="sxs-lookup"><span data-stu-id="718e1-142">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
### <a name="dynamic-options"></a><span data-ttu-id="718e1-143">Opções dinâmicas</span><span class="sxs-lookup"><span data-stu-id="718e1-143">Dynamic Options</span></span>  
  
#### <a name="package-source--sql-server"></a><span data-ttu-id="718e1-144">Origem do pacote = SQL Server</span><span class="sxs-lookup"><span data-stu-id="718e1-144">Package Source = SQL Server</span></span>  
 <span data-ttu-id="718e1-145">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="718e1-145">**Server**</span></span>  
 <span data-ttu-id="718e1-146">Digite o nome do servidor onde o pacote está ou selecione um servidor da lista.</span><span class="sxs-lookup"><span data-stu-id="718e1-146">Type the name of the server where the package resides, or select a server from the list.</span></span>  
  
 <span data-ttu-id="718e1-147">**Fazer login no servidor**</span><span class="sxs-lookup"><span data-stu-id="718e1-147">**Log on to the server**</span></span>  
 <span data-ttu-id="718e1-148">Especifique se o pacote deve usar a Autenticação do Windows ou a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] para estabelecer conexão com o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span><span class="sxs-lookup"><span data-stu-id="718e1-148">Specify whether the package should use Windows Authentication or [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication to connect to [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)].</span></span> <span data-ttu-id="718e1-149">A Autenticação do Windows é recomendada para obter melhor segurança.</span><span class="sxs-lookup"><span data-stu-id="718e1-149">Windows Authentication is recommended for better security.</span></span> <span data-ttu-id="718e1-150">Com a Autenticação do Windows você não precisa especificar um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="718e1-150">With Windows Authentication you do not have to specify a user name and password.</span></span>  
  
 <span data-ttu-id="718e1-151">**Usar Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="718e1-151">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="718e1-152">Selecione esta opção para usar a Autenticação do Windows e fazer logon usando uma conta de usuário do [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows.</span><span class="sxs-lookup"><span data-stu-id="718e1-152">Select this option to use Windows Authentication and log on using a [!INCLUDE[msCoName](../../includes/msconame-md.md)] Windows user account.</span></span>  
  
 <span data-ttu-id="718e1-153">**Usar Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="718e1-153">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="718e1-154">Selecione esta opção para usar a Autenticação do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] .</span><span class="sxs-lookup"><span data-stu-id="718e1-154">Select this option to use [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] Authentication.</span></span> <span data-ttu-id="718e1-155">Quando um usuário se conecta com um nome de logon e senha especificados em uma conexão não confiável, o próprio [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] efetua a autenticação verificando se foi definida uma conta de logon do [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] e se a senha especificada corresponde a uma senha registrada previamente.</span><span class="sxs-lookup"><span data-stu-id="718e1-155">When a user connects with a specified login name and password from a non-trusted connection, [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] performs the authentication by checking to see if a [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] login account has been set up and if the specified password matches the one previously recorded.</span></span> <span data-ttu-id="718e1-156">Se o [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] não localizar a conta de login, ocorrerá uma falha na autenticação e o usuário receberá uma mensagem de erro.</span><span class="sxs-lookup"><span data-stu-id="718e1-156">If [!INCLUDE[ssNoVersion](../../includes/ssnoversion-md.md)] cannot find the login account, authentication fails, and the user receives an error message.</span></span>  
  
> [!IMPORTANT]  
>  <span data-ttu-id="718e1-157">Quando possível, use a Autenticação do Windows.</span><span class="sxs-lookup"><span data-stu-id="718e1-157">When possible, use Windows Authentication.</span></span>  
  
 <span data-ttu-id="718e1-158">**Pacote**</span><span class="sxs-lookup"><span data-stu-id="718e1-158">**Package**</span></span>  
 <span data-ttu-id="718e1-159">Digite o nome do pacote ou clique no botão de reticências **(…)** para localizar um pacote usando a caixa de diálogo **Selecionar um Pacote do SSIS**.</span><span class="sxs-lookup"><span data-stu-id="718e1-159">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the **Select an SSIS Package** dialog box.</span></span>  
  
#### <a name="package-source--file-system"></a><span data-ttu-id="718e1-160">Origem do pacote = Sistema de arquivos</span><span class="sxs-lookup"><span data-stu-id="718e1-160">Package Source = File System</span></span>  
 <span data-ttu-id="718e1-161">**Pacote**</span><span class="sxs-lookup"><span data-stu-id="718e1-161">**Package**</span></span>  
 <span data-ttu-id="718e1-162">Digite o nome do pacote ou clique no botão de reticências **(…)** para localizar um pacote usando a caixa de diálogo Abrir.</span><span class="sxs-lookup"><span data-stu-id="718e1-162">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the Open dialog box.</span></span> <span data-ttu-id="718e1-163">Por padrão, a caixa de diálogo lista somente os arquivos com a extensão .dtsx.</span><span class="sxs-lookup"><span data-stu-id="718e1-163">By default, the dialog box lists only files that have the .dtsx extension.</span></span>  
  
#### <a name="package-source--ssis-package-store"></a><span data-ttu-id="718e1-164">Origem do pacote = Armazenamento de Pacotes SSIS</span><span class="sxs-lookup"><span data-stu-id="718e1-164">Package Source = SSIS Package Store</span></span>  
 <span data-ttu-id="718e1-165">**Servidor**</span><span class="sxs-lookup"><span data-stu-id="718e1-165">**Server**</span></span>  
 <span data-ttu-id="718e1-166">Digite o nome do computador onde o pacote está ou selecione um computador da lista.</span><span class="sxs-lookup"><span data-stu-id="718e1-166">Type the name of the computer where the package resides, or select a computer from the list.</span></span>  
  
 <span data-ttu-id="718e1-167">**Fazer login no servidor**</span><span class="sxs-lookup"><span data-stu-id="718e1-167">**Log on to the server**</span></span>  
 <span data-ttu-id="718e1-168">Especifique se o pacote deve usar a Autenticação do Microsoft Windows para estabelecer conexão com a origem do pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-168">Specify whether the package should use Microsoft Windows Authentication to connect to the package source.</span></span> <span data-ttu-id="718e1-169">A Autenticação do Windows é recomendada para obter melhor segurança.</span><span class="sxs-lookup"><span data-stu-id="718e1-169">Windows Authentication is recommended for better security.</span></span> <span data-ttu-id="718e1-170">Com a Autenticação do Windows você não precisa especificar um nome de usuário e senha.</span><span class="sxs-lookup"><span data-stu-id="718e1-170">With Windows Authentication you do not have to specify a user name and password.</span></span>  
  
 <span data-ttu-id="718e1-171">**Usar Autenticação do Windows**</span><span class="sxs-lookup"><span data-stu-id="718e1-171">**Use Windows Authentication**</span></span>  
 <span data-ttu-id="718e1-172">Selecione esta opção para usar a Autenticação do Windows e efetuar login usando uma conta de usuário do Microsoft Windows.</span><span class="sxs-lookup"><span data-stu-id="718e1-172">Select this option to use Windows Authentication and log on using a Microsoft Windows user account.</span></span>  
  
 <span data-ttu-id="718e1-173">**Usar Autenticação do SQL Server**</span><span class="sxs-lookup"><span data-stu-id="718e1-173">**Use SQL Server Authentication**</span></span>  
 <span data-ttu-id="718e1-174">Esta opção não estará disponível quando você executar um pacote armazenado no **Repositório de Pacotes SSIS**.</span><span class="sxs-lookup"><span data-stu-id="718e1-174">This option is not available when you run a package stored in the **SSIS Package Store**.</span></span>  
  
 <span data-ttu-id="718e1-175">**Pacote**</span><span class="sxs-lookup"><span data-stu-id="718e1-175">**Package**</span></span>  
 <span data-ttu-id="718e1-176">Digite o nome do pacote ou clique no botão de reticências **(…)** para localizar um pacote usando a caixa de diálogo **Selecionar um Pacote do SSIS**.</span><span class="sxs-lookup"><span data-stu-id="718e1-176">Type the name of the package, or click the ellipsis button **(...)** to locate a package using the **Select an SSIS Package** dialog box.</span></span>  
  
## <a name="configurations-page"></a><span data-ttu-id="718e1-177">Página Configurações</span><span class="sxs-lookup"><span data-stu-id="718e1-177">Configurations Page</span></span>  
 <span data-ttu-id="718e1-178">Use a página **Configurações** da caixa de diálogo **Utilitário de Execução de Pacotes** para selecionar os arquivos de configuração a serem carregados no momento da execução e para especificar a ordem em que serão carregados.</span><span class="sxs-lookup"><span data-stu-id="718e1-178">Use the **Configurations** page of the **Execute Package Utility** dialog box to select the configuration files to load at run time, and to specify the order in which they load.</span></span>  
  
### <a name="options"></a><span data-ttu-id="718e1-179">Opções</span><span class="sxs-lookup"><span data-stu-id="718e1-179">Options</span></span>  
 <span data-ttu-id="718e1-180">**Arquivos de configuração**</span><span class="sxs-lookup"><span data-stu-id="718e1-180">**Configuration files**</span></span>  
 <span data-ttu-id="718e1-181">Estes arquivos listam as configurações que o pacote usa.</span><span class="sxs-lookup"><span data-stu-id="718e1-181">Lists the configurations that the package uses.</span></span> <span data-ttu-id="718e1-182">Cada arquivo de configuração adiciona uma opção **/CONFIGFILE filename** ao prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="718e1-182">Each configuration file adds a **/CONFIGFILE filename** option to the command prompt.</span></span>  
  
 <span data-ttu-id="718e1-183">**Teclas de direção**</span><span class="sxs-lookup"><span data-stu-id="718e1-183">**Arrow keys**</span></span>  
 <span data-ttu-id="718e1-184">Selecione um arquivo de configuração na lista e use as teclas de direção à direita para alterar a ordem de carregamento.</span><span class="sxs-lookup"><span data-stu-id="718e1-184">Select a configuration file in the list, and use the arrow keys at right to change the loading order.</span></span> <span data-ttu-id="718e1-185">As configurações são carregadas em ordem a partir do início da lista.</span><span class="sxs-lookup"><span data-stu-id="718e1-185">Configurations load in order starting from the top of the list.</span></span>  
  
> [!NOTE]  
>  <span data-ttu-id="718e1-186">Caso várias configurações modifiquem a mesma propriedade, a última configuração carregada será usada.</span><span class="sxs-lookup"><span data-stu-id="718e1-186">If multiple configurations modify the same property, the configuration that loads last is used.</span></span>  
  
 <span data-ttu-id="718e1-187">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="718e1-187">**Add**</span></span>  
 <span data-ttu-id="718e1-188">Clique para adicionar configurações usando a caixa de diálogo **Abrir** .</span><span class="sxs-lookup"><span data-stu-id="718e1-188">Click to add configurations using the **Open** dialog box.</span></span> <span data-ttu-id="718e1-189">Por padrão, a caixa de diálogo lista somente os arquivos com a extensão .dtsconfig.</span><span class="sxs-lookup"><span data-stu-id="718e1-189">By default, the dialog box lists only files that have the .dtsconfig extension.</span></span>  
  
 <span data-ttu-id="718e1-190">**Remover**</span><span class="sxs-lookup"><span data-stu-id="718e1-190">**Remove**</span></span>  
 <span data-ttu-id="718e1-191">Selecione um arquivo de configuração na lista e clique em **Remover**.</span><span class="sxs-lookup"><span data-stu-id="718e1-191">Select a configuration file in the list and then click **Remove**.</span></span>  
  
 <span data-ttu-id="718e1-192">**Executar**</span><span class="sxs-lookup"><span data-stu-id="718e1-192">**Execute**</span></span>  
 <span data-ttu-id="718e1-193">Clique para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-193">Click to run the package.</span></span>  
  
 <span data-ttu-id="718e1-194">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="718e1-194">**Close**</span></span>  
 <span data-ttu-id="718e1-195">Clique para fechar a caixa de diálogo **Utilitário do Pacote de Execução** .</span><span class="sxs-lookup"><span data-stu-id="718e1-195">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="command-files-page"></a><span data-ttu-id="718e1-196">Página Arquivos de Comando</span><span class="sxs-lookup"><span data-stu-id="718e1-196">Command Files Page</span></span>  
 <span data-ttu-id="718e1-197">Use a página **Arquivos de Comando** da caixa de diálogo **Utilitário de Execução de Pacotes** para selecionar os arquivos de comando a serem carregados no momento da execução.</span><span class="sxs-lookup"><span data-stu-id="718e1-197">Use the **Command Files** page of the **Execute Package Utility** dialog box to select the command files to load at run time.</span></span>  
  
### <a name="options"></a><span data-ttu-id="718e1-198">Opções</span><span class="sxs-lookup"><span data-stu-id="718e1-198">Options</span></span>  
 <span data-ttu-id="718e1-199">**Arquivos de comando**</span><span class="sxs-lookup"><span data-stu-id="718e1-199">**Command files**</span></span>  
 <span data-ttu-id="718e1-200">Lista os arquivos de comando que o pacote usa.</span><span class="sxs-lookup"><span data-stu-id="718e1-200">Lists the command files that the package uses.</span></span> <span data-ttu-id="718e1-201">Um pacote pode usar vários arquivos para definir as opções de linha de comando.</span><span class="sxs-lookup"><span data-stu-id="718e1-201">A package can use multiple files to set command-line options.</span></span>  
  
 <span data-ttu-id="718e1-202">**Teclas de direção**</span><span class="sxs-lookup"><span data-stu-id="718e1-202">**Arrow keys**</span></span>  
 <span data-ttu-id="718e1-203">Selecione um arquivo de comando na lista e use as teclas de seta para a direita para alterar a ordem de carregamento.</span><span class="sxs-lookup"><span data-stu-id="718e1-203">Select a command file in the list, and use the arrow keys at right to change the loading order.</span></span> <span data-ttu-id="718e1-204">Os arquivos de comando são carregados em ordem a partir do início da lista.</span><span class="sxs-lookup"><span data-stu-id="718e1-204">Command files load in order, starting from the top of the list.</span></span>  
  
 <span data-ttu-id="718e1-205">**Adicionar**</span><span class="sxs-lookup"><span data-stu-id="718e1-205">**Add**</span></span>  
 <span data-ttu-id="718e1-206">Clique para adicionar um arquivo de comando, usando a caixa de diálogo **Abrir** .</span><span class="sxs-lookup"><span data-stu-id="718e1-206">Click to add a command file, using the **Open** dialog box.</span></span>  
  
 <span data-ttu-id="718e1-207">**Remover**</span><span class="sxs-lookup"><span data-stu-id="718e1-207">**Remove**</span></span>  
 <span data-ttu-id="718e1-208">Selecione um arquivo de comandos na caixa de texto e remova-o usando o botão **Remover** .</span><span class="sxs-lookup"><span data-stu-id="718e1-208">Select a command file in the text box, and then remove it using the **Remove** button.</span></span>  
  
 <span data-ttu-id="718e1-209">**Executar**</span><span class="sxs-lookup"><span data-stu-id="718e1-209">**Execute**</span></span>  
 <span data-ttu-id="718e1-210">Clique para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-210">Click to run the package.</span></span>  
  
 <span data-ttu-id="718e1-211">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="718e1-211">**Close**</span></span>  
 <span data-ttu-id="718e1-212">Clique para fechar a caixa de diálogo **Utilitário do Pacote de Execução** .</span><span class="sxs-lookup"><span data-stu-id="718e1-212">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="connection-managers-page"></a><span data-ttu-id="718e1-213">Página Gerenciadores de Conexões</span><span class="sxs-lookup"><span data-stu-id="718e1-213">Connection Managers Page</span></span>  
 <span data-ttu-id="718e1-214">Use a página **Gerenciadores de Conexões** da caixa de diálogo do **Utilitário de Execução de Pacotes** para editar as cadeias de conexão dos gerenciadores de conexões usados pelo pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-214">Use the **Connection Managers** page of the **Execute Package Utility** dialog box to edit the connection strings of the connection managers that the package uses.</span></span>  
  
### <a name="options"></a><span data-ttu-id="718e1-215">Opções</span><span class="sxs-lookup"><span data-stu-id="718e1-215">Options</span></span>  
 <span data-ttu-id="718e1-216">**Gerenciador de Conexões**</span><span class="sxs-lookup"><span data-stu-id="718e1-216">**Connection Manager**</span></span>  
 <span data-ttu-id="718e1-217">Marque a caixa de seleção para que a coluna **Cadeia de Conexão** possa ser editada.</span><span class="sxs-lookup"><span data-stu-id="718e1-217">Select its check box to make the **Connection String** column editable.</span></span>  
  
 <span data-ttu-id="718e1-218">**Descrição**</span><span class="sxs-lookup"><span data-stu-id="718e1-218">**Description**</span></span>  
 <span data-ttu-id="718e1-219">Exiba uma descrição para cada gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="718e1-219">View a description for each connection manager.</span></span> <span data-ttu-id="718e1-220">As descrições não podem ser editadas.</span><span class="sxs-lookup"><span data-stu-id="718e1-220">Descriptions cannot be edited.</span></span>  
  
 <span data-ttu-id="718e1-221">**Cadeia de Conexão**</span><span class="sxs-lookup"><span data-stu-id="718e1-221">**Connection String**</span></span>  
 <span data-ttu-id="718e1-222">Edite a cadeia de caracteres de conexão para um gerenciador de conexões.</span><span class="sxs-lookup"><span data-stu-id="718e1-222">Edit the connection string for a connection manager.</span></span> <span data-ttu-id="718e1-223">Este campo só permitirá edições quando a caixa de seleção **Gerenciador de Conexões** estiver marcada.</span><span class="sxs-lookup"><span data-stu-id="718e1-223">This field is editable only when the **Connection Manager** check box is selected.</span></span>  
  
 <span data-ttu-id="718e1-224">**Executar**</span><span class="sxs-lookup"><span data-stu-id="718e1-224">**Execute**</span></span>  
 <span data-ttu-id="718e1-225">Clique para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-225">Click to run the package.</span></span>  
  
 <span data-ttu-id="718e1-226">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="718e1-226">**Close**</span></span>  
 <span data-ttu-id="718e1-227">Clique para fechar a caixa de diálogo **Utilitário do Pacote de Execução** .</span><span class="sxs-lookup"><span data-stu-id="718e1-227">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="execution-options-page"></a><span data-ttu-id="718e1-228">Página Opções de Execução</span><span class="sxs-lookup"><span data-stu-id="718e1-228">Execution Options Page</span></span>  
 <span data-ttu-id="718e1-229">Use a página **Opções de Execução** da caixa de diálogo **Utilitário de Execução de Pacotes** para especificar as opções de tempo de execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-229">Use the **Execution Options** page of the **Execute Package Utility** dialog box to specify run-time options for the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="718e1-230">Opções</span><span class="sxs-lookup"><span data-stu-id="718e1-230">Options</span></span>  
 <span data-ttu-id="718e1-231">**Falha de pacote com avisos de validação**</span><span class="sxs-lookup"><span data-stu-id="718e1-231">**Fail package on validation warnings**</span></span>  
 <span data-ttu-id="718e1-232">Indique se o pacote falha quando ocorre um aviso de validação.</span><span class="sxs-lookup"><span data-stu-id="718e1-232">Indicate whether the package fails if a validation warning occurs.</span></span>  
  
 <span data-ttu-id="718e1-233">**Validar pacote sem executar**</span><span class="sxs-lookup"><span data-stu-id="718e1-233">**Validate package without executing**</span></span>  
 <span data-ttu-id="718e1-234">Indique se o pacote será apenas validado.</span><span class="sxs-lookup"><span data-stu-id="718e1-234">Indicate whether the package is validated only.</span></span>  
  
 <span data-ttu-id="718e1-235">**Executáveis máximos simultâneos**</span><span class="sxs-lookup"><span data-stu-id="718e1-235">**Maximum concurrent executables**</span></span>  
 <span data-ttu-id="718e1-236">Indique se você deseja especificar o número máximo de executáveis que poderá ser executado simultaneamente no pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-236">Indicate whether you want to specify the maximum number of executables that can run in the package at the same time.</span></span> <span data-ttu-id="718e1-237">Depois que você marcar esta caixa de seleção, use a caixa de rotação para especificar o número máximo de executáveis.</span><span class="sxs-lookup"><span data-stu-id="718e1-237">After you select this check box, use the spin box to specify the maximum number of executables.</span></span>  
  
 <span data-ttu-id="718e1-238">**Ativar pontos de verificação do pacote**</span><span class="sxs-lookup"><span data-stu-id="718e1-238">**Enable package checkpoints**</span></span>  
 <span data-ttu-id="718e1-239">Indique se deseja ativar os pontos de verificação do pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-239">Indicate whether to enable package checkpoints.</span></span>  
  
 <span data-ttu-id="718e1-240">**Arquivo de ponto de verificação**</span><span class="sxs-lookup"><span data-stu-id="718e1-240">**Checkpoint file**</span></span>  
 <span data-ttu-id="718e1-241">Liste o arquivo de ponto de verificação que será usado pelo pacote se você ativar os pontos de verificação do pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-241">List the checkpoint file the package uses, if you enable package checkpoints.</span></span>  
  
 <span data-ttu-id="718e1-242">**Procurar**</span><span class="sxs-lookup"><span data-stu-id="718e1-242">**Browse**</span></span>  
 <span data-ttu-id="718e1-243">Se você habilitar os pontos de verificação do pacote, clique no botão Procurar **(…)** para localizar o arquivo de ponto de verificação usando a caixa de diálogo **Abrir**.</span><span class="sxs-lookup"><span data-stu-id="718e1-243">Click the browse button **(...)** to locate the checkpoint file using the **Open** dialog box, if you enable package checkpoints.</span></span> <span data-ttu-id="718e1-244">Se algum arquivo de ponto de verificação já tiver sido especificado, ele será substituído pelo arquivo selecionado.</span><span class="sxs-lookup"><span data-stu-id="718e1-244">If a checkpoint file is already specified, it is replaced by the selected file.</span></span>  
  
 <span data-ttu-id="718e1-245">**Substituir opções de reinicialização**</span><span class="sxs-lookup"><span data-stu-id="718e1-245">**Override restart options**</span></span>  
 <span data-ttu-id="718e1-246">Indique se as opções de reinicialização serão substituídas se você ativar os pontos de verificação do pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-246">Indicate whether to override restart options, if you enable package checkpoints.</span></span>  
  
 <span data-ttu-id="718e1-247">**Opção de reinicialização**</span><span class="sxs-lookup"><span data-stu-id="718e1-247">**Restart option**</span></span>  
 <span data-ttu-id="718e1-248">Selecione como os pontos de verificação serão usados ao substituir as opções de reinicialização.</span><span class="sxs-lookup"><span data-stu-id="718e1-248">Select how to use checkpoints, if you override restart options.</span></span>  
  
 <span data-ttu-id="718e1-249">**Executar**</span><span class="sxs-lookup"><span data-stu-id="718e1-249">**Execute**</span></span>  
 <span data-ttu-id="718e1-250">Clique para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-250">Click to run the package.</span></span>  
  
 <span data-ttu-id="718e1-251">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="718e1-251">**Close**</span></span>  
 <span data-ttu-id="718e1-252">Clique para fechar a caixa de diálogo **Utilitário do Pacote de Execução** .</span><span class="sxs-lookup"><span data-stu-id="718e1-252">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="reporting-page"></a><span data-ttu-id="718e1-253">Página Relatório</span><span class="sxs-lookup"><span data-stu-id="718e1-253">Reporting Page</span></span>  
 <span data-ttu-id="718e1-254">Use a página **Relatório** da caixa de diálogo **Utilitário de Execução de Pacotes** para especificar eventos e informações sobre o pacote a ser registrado no console quando o pacote é executado.</span><span class="sxs-lookup"><span data-stu-id="718e1-254">Use the **Reporting** page of the **Execute Package Utility** dialog box to specify the events and information about the package to log to the console when the package runs.</span></span>  
  
### <a name="options"></a><span data-ttu-id="718e1-255">Opções</span><span class="sxs-lookup"><span data-stu-id="718e1-255">Options</span></span>  
 <span data-ttu-id="718e1-256">**Eventos do console**</span><span class="sxs-lookup"><span data-stu-id="718e1-256">**Console events**</span></span>  
 <span data-ttu-id="718e1-257">Indique os eventos e os tipos de mensagens a serem relatados.</span><span class="sxs-lookup"><span data-stu-id="718e1-257">Indicate the events and types of messages to report.</span></span>  
  
 <span data-ttu-id="718e1-258">**Nenhuma**</span><span class="sxs-lookup"><span data-stu-id="718e1-258">**None**</span></span>  
 <span data-ttu-id="718e1-259">Selecione para não gerar relatórios.</span><span class="sxs-lookup"><span data-stu-id="718e1-259">Select for no reporting.</span></span>  
  
 <span data-ttu-id="718e1-260">**Erros**</span><span class="sxs-lookup"><span data-stu-id="718e1-260">**Errors**</span></span>  
 <span data-ttu-id="718e1-261">Selecione para informar mensagens de erro.</span><span class="sxs-lookup"><span data-stu-id="718e1-261">Select to report error messages.</span></span>  
  
 <span data-ttu-id="718e1-262">**Warnings**</span><span class="sxs-lookup"><span data-stu-id="718e1-262">**Warnings**</span></span>  
 <span data-ttu-id="718e1-263">Selecione para informar mensagens de aviso.</span><span class="sxs-lookup"><span data-stu-id="718e1-263">Select to report warning messages.</span></span>  
  
 <span data-ttu-id="718e1-264">**Eventos personalizados**</span><span class="sxs-lookup"><span data-stu-id="718e1-264">**Custom Events**</span></span>  
 <span data-ttu-id="718e1-265">Selecione para informar mensagens de eventos personalizados.</span><span class="sxs-lookup"><span data-stu-id="718e1-265">Select to report custom event messages.</span></span>  
  
 <span data-ttu-id="718e1-266">**Eventos de Pipeline**</span><span class="sxs-lookup"><span data-stu-id="718e1-266">**Pipeline Events**</span></span>  
 <span data-ttu-id="718e1-267">Selecione para informar mensagens de eventos de fluxo de dados.</span><span class="sxs-lookup"><span data-stu-id="718e1-267">Select to report data flow events messages.</span></span>  
  
 <span data-ttu-id="718e1-268">**Informações**</span><span class="sxs-lookup"><span data-stu-id="718e1-268">**Information**</span></span>  
 <span data-ttu-id="718e1-269">Selecione para informar mensagens de informações.</span><span class="sxs-lookup"><span data-stu-id="718e1-269">Select to report information messages.</span></span>  
  
 <span data-ttu-id="718e1-270">**Detalhado**</span><span class="sxs-lookup"><span data-stu-id="718e1-270">**Verbose**</span></span>  
 <span data-ttu-id="718e1-271">Selecione para usar relatório verboso.</span><span class="sxs-lookup"><span data-stu-id="718e1-271">Select to use verbose reporting.</span></span>  
  
 <span data-ttu-id="718e1-272">**Log de console**</span><span class="sxs-lookup"><span data-stu-id="718e1-272">**Console logging**</span></span>  
 <span data-ttu-id="718e1-273">Especifique as informações que deseja gravar no log quando o evento selecionado ocorrer.</span><span class="sxs-lookup"><span data-stu-id="718e1-273">Specify the information that you want written to the log when the selected event occurs.</span></span>  
  
 <span data-ttu-id="718e1-274">**Nome**</span><span class="sxs-lookup"><span data-stu-id="718e1-274">**Name**</span></span>  
 <span data-ttu-id="718e1-275">Selecione para informar o nome da pessoa que criou o pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-275">Select to report the name of the person who created the package.</span></span>  
  
 <span data-ttu-id="718e1-276">**Computador**</span><span class="sxs-lookup"><span data-stu-id="718e1-276">**Computer**</span></span>  
 <span data-ttu-id="718e1-277">Selecione para informar o nome do computador em que o pacote está sendo executado.</span><span class="sxs-lookup"><span data-stu-id="718e1-277">Select to report the name of the computer the package is running on.</span></span>  
  
 <span data-ttu-id="718e1-278">**Operador**</span><span class="sxs-lookup"><span data-stu-id="718e1-278">**Operator**</span></span>  
 <span data-ttu-id="718e1-279">Selecione para informar o nome da pessoa que iniciou o pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-279">Select to report the name of the person who started the package.</span></span>  
  
 <span data-ttu-id="718e1-280">**Nome de origem**</span><span class="sxs-lookup"><span data-stu-id="718e1-280">**Source name**</span></span>  
 <span data-ttu-id="718e1-281">Selecione para informar o nome do pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-281">Select to report the package name.</span></span>  
  
 <span data-ttu-id="718e1-282">**GUID de Origem**</span><span class="sxs-lookup"><span data-stu-id="718e1-282">**Source GUID**</span></span>  
 <span data-ttu-id="718e1-283">Selecione para informar a GUID do pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-283">Select to report the package GUID.</span></span>  
  
 <span data-ttu-id="718e1-284">**GUID de Execução**</span><span class="sxs-lookup"><span data-stu-id="718e1-284">**Execution GUID**</span></span>  
 <span data-ttu-id="718e1-285">Selecione para informar a GUID da instância de execução do pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-285">Select to report the GUID of the package execution instance.</span></span>  
  
 <span data-ttu-id="718e1-286">**Mensagem**</span><span class="sxs-lookup"><span data-stu-id="718e1-286">**Message**</span></span>  
 <span data-ttu-id="718e1-287">Selecione para informar mensagens.</span><span class="sxs-lookup"><span data-stu-id="718e1-287">Select to report messages.</span></span>  
  
 <span data-ttu-id="718e1-288">**Hora de início e Hora de término**</span><span class="sxs-lookup"><span data-stu-id="718e1-288">**Start time and end time**</span></span>  
 <span data-ttu-id="718e1-289">Selecione para informar quando o pacote começou e quando terminou.</span><span class="sxs-lookup"><span data-stu-id="718e1-289">Select to report when the package began and finished.</span></span>  
  
 <span data-ttu-id="718e1-290">**Executar**</span><span class="sxs-lookup"><span data-stu-id="718e1-290">**Execute**</span></span>  
 <span data-ttu-id="718e1-291">Clique para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-291">Click to run the package.</span></span>  
  
 <span data-ttu-id="718e1-292">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="718e1-292">**Close**</span></span>  
 <span data-ttu-id="718e1-293">Clique para fechar a caixa de diálogo **Utilitário do Pacote de Execução** .</span><span class="sxs-lookup"><span data-stu-id="718e1-293">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="logging-page"></a><span data-ttu-id="718e1-294">Página Log</span><span class="sxs-lookup"><span data-stu-id="718e1-294">Logging Page</span></span>  
 <span data-ttu-id="718e1-295">Use a página **Log** da caixa de diálogo **Utilitário de Execução de Pacotes** para que os provedores de log sejam disponibilizados para o pacote no momento da execução.</span><span class="sxs-lookup"><span data-stu-id="718e1-295">Use the **Logging** page of the **Execute Package Utility** dialog box to make log providers available to the package at run time.</span></span> <span data-ttu-id="718e1-296">Forneça o tipo de provedor de log e a cadeia de conexão do pacote para estabelecer conexão com o log.</span><span class="sxs-lookup"><span data-stu-id="718e1-296">Provide the package log provider type and the connection string for connecting to the log.</span></span> <span data-ttu-id="718e1-297">Cada entrada de provedor de log adiciona uma opção **/LOGGER**_classid_ ao prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="718e1-297">Each log provider entry adds a **/LOGGER**_classid_ option to the command prompt.</span></span>  
  
### <a name="options"></a><span data-ttu-id="718e1-298">Opções</span><span class="sxs-lookup"><span data-stu-id="718e1-298">Options</span></span>  
 <span data-ttu-id="718e1-299">**Provedor de Log**</span><span class="sxs-lookup"><span data-stu-id="718e1-299">**Log Provider**</span></span>  
 <span data-ttu-id="718e1-300">Selecione um provedor de log da lista.</span><span class="sxs-lookup"><span data-stu-id="718e1-300">Select a log provider from the list.</span></span>  
  
 <span data-ttu-id="718e1-301">**Cadeia de Caracteres de Configuração**</span><span class="sxs-lookup"><span data-stu-id="718e1-301">**Configuration String**</span></span>  
 <span data-ttu-id="718e1-302">Selecione o nome do gerenciador de conexões do pacote que aponta para o local do log ou digite a cadeia de caracteres de conexão para estabelecer conexão com o provedor de log.</span><span class="sxs-lookup"><span data-stu-id="718e1-302">Select the name of the connection manager from the package that points to the log location, or type the connection string for connecting to the log provider.</span></span>  
  
 <span data-ttu-id="718e1-303">**Remover**</span><span class="sxs-lookup"><span data-stu-id="718e1-303">**Remove**</span></span>  
 <span data-ttu-id="718e1-304">Selecione um provedor de log e clique para removê-lo.</span><span class="sxs-lookup"><span data-stu-id="718e1-304">Select a log provider and click to remove it.</span></span>  
  
 <span data-ttu-id="718e1-305">**Executar**</span><span class="sxs-lookup"><span data-stu-id="718e1-305">**Execute**</span></span>  
 <span data-ttu-id="718e1-306">Clique para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-306">Click to run the package.</span></span>  
  
 <span data-ttu-id="718e1-307">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="718e1-307">**Close**</span></span>  
 <span data-ttu-id="718e1-308">Clique para fechar a caixa de diálogo **Utilitário do Pacote de Execução** .</span><span class="sxs-lookup"><span data-stu-id="718e1-308">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="set-values-page"></a><span data-ttu-id="718e1-309">Página Definir Valores</span><span class="sxs-lookup"><span data-stu-id="718e1-309">Set Values Page</span></span>  
 <span data-ttu-id="718e1-310">Use a página **Definir Valores** da caixa de diálogo **Utilitário de Execução de Pacotes** para definir os valores de propriedade, executáveis, conexões, variáveis e provedores de log dos pacotes digitando os caminhos e os valores das propriedades.</span><span class="sxs-lookup"><span data-stu-id="718e1-310">Use the **Set Values** page of the **Execute Package Utility** dialog box to set the property values of packages, executables, connections, variables, and log providers by typing the paths of properties and the property values.</span></span> <span data-ttu-id="718e1-311">Cada entrada de caminho adiciona uma opção **/SET**_propertypath;value_ ao prompt de comando.</span><span class="sxs-lookup"><span data-stu-id="718e1-311">Each path entry adds a **/SET**_propertypath;value_ option to the command prompt.</span></span>  
  
### <a name="options"></a><span data-ttu-id="718e1-312">Opções</span><span class="sxs-lookup"><span data-stu-id="718e1-312">Options</span></span>  
 <span data-ttu-id="718e1-313">**Caminho da propriedade**</span><span class="sxs-lookup"><span data-stu-id="718e1-313">**Property Path**</span></span>  
 <span data-ttu-id="718e1-314">Digite o caminho da propriedade.</span><span class="sxs-lookup"><span data-stu-id="718e1-314">Type the path of the property.</span></span> <span data-ttu-id="718e1-315">A sintaxe do caminho usa uma barra invertida (\\) para indicar que o item a seguir é um contêiner, usa um ponto (.) para indicar que o item a seguir é uma propriedade e usa colchetes para indicar um membro da coleção.</span><span class="sxs-lookup"><span data-stu-id="718e1-315">The path syntax uses a backslash (\\) to indicate that the following item is a container, the period (.) to indicate the following item is a property, and brackets to indicate a collection member.</span></span> <span data-ttu-id="718e1-316">O membro pode ser identificado pelo índice ou pelo nome.</span><span class="sxs-lookup"><span data-stu-id="718e1-316">The member can be identified by its index or its name.</span></span> <span data-ttu-id="718e1-317">Por exemplo, o caminho da propriedade de uma variável de pacote é \Package.Variables[MyVariable].Value.</span><span class="sxs-lookup"><span data-stu-id="718e1-317">For example, the property path of a package variable is \Package.Variables[MyVariable].Value.</span></span>  
  
 <span data-ttu-id="718e1-318">**Valor**</span><span class="sxs-lookup"><span data-stu-id="718e1-318">**Value**</span></span>  
 <span data-ttu-id="718e1-319">Digite o valor da propriedade.</span><span class="sxs-lookup"><span data-stu-id="718e1-319">Type the value of the property.</span></span>  
  
 <span data-ttu-id="718e1-320">**Remover**</span><span class="sxs-lookup"><span data-stu-id="718e1-320">**Remove**</span></span>  
 <span data-ttu-id="718e1-321">Selecione o caminho da propriedade e clique para removê-lo.</span><span class="sxs-lookup"><span data-stu-id="718e1-321">Select a property path and click to remove it.</span></span>  
  
 <span data-ttu-id="718e1-322">**Executar**</span><span class="sxs-lookup"><span data-stu-id="718e1-322">**Execute**</span></span>  
 <span data-ttu-id="718e1-323">Clique para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-323">Click to run the package.</span></span>  
  
 <span data-ttu-id="718e1-324">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="718e1-324">**Close**</span></span>  
 <span data-ttu-id="718e1-325">Clique para fechar a caixa de diálogo **Utilitário do Pacote de Execução** .</span><span class="sxs-lookup"><span data-stu-id="718e1-325">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="verification-page"></a><span data-ttu-id="718e1-326">Página Verificação</span><span class="sxs-lookup"><span data-stu-id="718e1-326">Verification Page</span></span>  
 <span data-ttu-id="718e1-327">Use a página **Verificação** da caixa de diálogo **Executar Pacote** para definir os critérios de verificação do pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-327">Use the **Verification** page of the **Execute Package** dialog box to set criteria for verifying the package.</span></span>  
  
### <a name="options"></a><span data-ttu-id="718e1-328">Opções</span><span class="sxs-lookup"><span data-stu-id="718e1-328">Options</span></span>  
 <span data-ttu-id="718e1-329">**Executar apenas pacotes assinados**</span><span class="sxs-lookup"><span data-stu-id="718e1-329">**Execute only signed packages**</span></span>  
 <span data-ttu-id="718e1-330">Selecione para executar apenas os pacotes que foram assinados.</span><span class="sxs-lookup"><span data-stu-id="718e1-330">Select to execute only packages that have been signed.</span></span>  
  
 <span data-ttu-id="718e1-331">**Verificar construção de pacote**</span><span class="sxs-lookup"><span data-stu-id="718e1-331">**Verify package build**</span></span>  
 <span data-ttu-id="718e1-332">Selecione para verificar a construção do pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-332">Select to verify the package build.</span></span>  
  
 <span data-ttu-id="718e1-333">Build</span><span class="sxs-lookup"><span data-stu-id="718e1-333">Build</span></span>  
 <span data-ttu-id="718e1-334">Especifique o número de compilação (build) sequencial associado à criação.</span><span class="sxs-lookup"><span data-stu-id="718e1-334">Specify the sequential Build number associated with the build.</span></span>  
  
 <span data-ttu-id="718e1-335">**Verificar ID do pacote**</span><span class="sxs-lookup"><span data-stu-id="718e1-335">**Verify package ID**</span></span>  
 <span data-ttu-id="718e1-336">Selecione para verificar a ID do pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-336">Select to verify the package ID.</span></span>  
  
 <span data-ttu-id="718e1-337">ID do Pacote</span><span class="sxs-lookup"><span data-stu-id="718e1-337">Package ID</span></span>  
 <span data-ttu-id="718e1-338">Especifique o número de identificação do pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-338">Specify the package identification number.</span></span>  
  
 <span data-ttu-id="718e1-339">**Verificar ID da versão**</span><span class="sxs-lookup"><span data-stu-id="718e1-339">**Verify version ID**</span></span>  
 <span data-ttu-id="718e1-340">Selecione para verificar a ID da versão.</span><span class="sxs-lookup"><span data-stu-id="718e1-340">Select to verify the version ID.</span></span>  
  
 <span data-ttu-id="718e1-341">ID da versão</span><span class="sxs-lookup"><span data-stu-id="718e1-341">Version ID</span></span>  
 <span data-ttu-id="718e1-342">Especifique o número de identificação da versão.</span><span class="sxs-lookup"><span data-stu-id="718e1-342">Specify the version identification number.</span></span>  
  
 <span data-ttu-id="718e1-343">**Executar**</span><span class="sxs-lookup"><span data-stu-id="718e1-343">**Execute**</span></span>  
 <span data-ttu-id="718e1-344">Clique para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-344">Click to run the package.</span></span>  
  
 <span data-ttu-id="718e1-345">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="718e1-345">**Close**</span></span>  
 <span data-ttu-id="718e1-346">Clique para fechar a caixa de diálogo **Utilitário do Pacote de Execução** .</span><span class="sxs-lookup"><span data-stu-id="718e1-346">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="command-line-page"></a><span data-ttu-id="718e1-347">Página Linha de Comando</span><span class="sxs-lookup"><span data-stu-id="718e1-347">Command Line Page</span></span>  
 <span data-ttu-id="718e1-348">Use o nó **Linha de Comando** da caixa de diálogo **Utilitário de Execução de Pacotes** para editar a linha de comando que foi gerada pelas opções criadas por vários diálogos.</span><span class="sxs-lookup"><span data-stu-id="718e1-348">Use the **Command Line** node of the **Execute Package Utility** dialog box to edit the command line that has been generated by the options created by the various dialogs.</span></span>  
  
### <a name="options"></a><span data-ttu-id="718e1-349">Opções</span><span class="sxs-lookup"><span data-stu-id="718e1-349">Options</span></span>  
 <span data-ttu-id="718e1-350">**Restaurar as opções originais**</span><span class="sxs-lookup"><span data-stu-id="718e1-350">**Restore the original options**</span></span>  
 <span data-ttu-id="718e1-351">Clique para restaurar a linha de comando para seu estado original.</span><span class="sxs-lookup"><span data-stu-id="718e1-351">Click to restore the command line to its original state.</span></span> <span data-ttu-id="718e1-352">Use esta opção se tiver feito modificações usando a opção **Editar a linha de comando manualmente** e quiser restaurar as opções originais da linha de comando.</span><span class="sxs-lookup"><span data-stu-id="718e1-352">Use this option if you have made modifications using the **Edit the command line manually** option and want to restore the original command-line options.</span></span>  
  
 <span data-ttu-id="718e1-353">**Editar a linha de comando manualmente**</span><span class="sxs-lookup"><span data-stu-id="718e1-353">**Edit the command line manually**</span></span>  
 <span data-ttu-id="718e1-354">Clique para editar a linha de comando na caixa de texto **Linha de comando** .</span><span class="sxs-lookup"><span data-stu-id="718e1-354">Click to edit the command line in the **Command line** text box.</span></span>  
  
 <span data-ttu-id="718e1-355">**Linha de comando**</span><span class="sxs-lookup"><span data-stu-id="718e1-355">**Command line**</span></span>  
 <span data-ttu-id="718e1-356">Exibe a linha de comando atual.</span><span class="sxs-lookup"><span data-stu-id="718e1-356">Displays the current command line.</span></span> <span data-ttu-id="718e1-357">Se você selecionou a opção para editar a linha de comando manualmente, ela será editável.</span><span class="sxs-lookup"><span data-stu-id="718e1-357">Editable if you selected the option to edit the command line manually.</span></span>  
  
 <span data-ttu-id="718e1-358">**Executar**</span><span class="sxs-lookup"><span data-stu-id="718e1-358">**Execute**</span></span>  
 <span data-ttu-id="718e1-359">Clique para executar o pacote.</span><span class="sxs-lookup"><span data-stu-id="718e1-359">Click to run the package.</span></span>  
  
 <span data-ttu-id="718e1-360">**Fechar**</span><span class="sxs-lookup"><span data-stu-id="718e1-360">**Close**</span></span>  
 <span data-ttu-id="718e1-361">Clique para fechar a caixa de diálogo **Utilitário do Pacote de Execução** .</span><span class="sxs-lookup"><span data-stu-id="718e1-361">Click to close the **Execute Package Utility** dialog box.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="718e1-362">Consulte Também</span><span class="sxs-lookup"><span data-stu-id="718e1-362">See Also</span></span>  
 [<span data-ttu-id="718e1-363">Utilitário dtexec</span><span class="sxs-lookup"><span data-stu-id="718e1-363">dtexec Utility</span></span>](dtexec-utility.md)  
  
  
